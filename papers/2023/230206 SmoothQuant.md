안녕하세요 NAVER Efficient AI 팀의 권세중입니다. 저번에 달아놓은 논문리뷰 글을 남기려고 합니다.

저의 올해 가장 큰 관심사는 Large Language Model (LLM)의 압축과 가속이었습니다. 연초만 해도 LLM을 압축한 논문에 대한 리포트가 없었기 때문에 BERT/T5등과 달리 GPT-like LLM에 대해서는 저희 내부 결과로밖에 확인을 못하고 있었습니다.

그러다가 ZeroQuant와 LLM.int8이 Neurips 2022에 Accept되면서 처음으로 제대로된 GPT + int8 압축/가속 논문이 나오기 시작했고, 동시에 int8 기술로 LLM을 가속하는 것의 한계가 드러났다고 생각합니다. ZeroQuant와 LLM.int8 논문은 Fine-grained하게 Quantization을 하고, Activation은 Dynamic하게 Quantization해야한다고 공통적으로 말합니다. ZeroQuant는 group-wise로 64/128개 row마다 Scaling Factor를 뽑았고, LLM.int8은 한술 더 떠서 Vector-wise로 Scaling Factor를 뽑았습니다. 그것도 모자라서 일부 outlier를 걸러내서 FP 연산을 추가로 돌렸습니다.  
  
Layer-wise로 Scale을 뽑으면 당연히 가속 측면에서 좋고, Activation에 대한 scaling을 미리 정해놓으면 (Static Quant.) 너무 좋겠으나, Transformer 특히 GPT-like autoregressive 모델의 터져나오는 outlier는 동일 scale로 묶어서 integer precision을 쓰는 것에 큰 방해물이었습니다. Fine-grained하고 Dynamic한 Quantization은 당연히 GPU 개수를 반으로 줄인다 하더라도 각종 overhead들로 가속성능이 오히려 느려지는 모습을 보이기도 했습니다.

그리고 오늘 말씀 드릴 것은, 이 모든 것을 한방에 날려버린 딥러닝 압축/가속/하드웨어 계의 선구자(?) MIT Song Han 교수님의 SmoothQuant입니다. 아주 적절한 타이밍에 논문을 Neurips와 EMNLP workshop에 던지시고 다른 곳에는 투고를 안하신것 같습니다. 재미있는 논문이기는 한데, 사실 그리 대단한 방법은 아니라서 그런 것 같습니다.

SmoothQuant는 LLM.int8()논문의 핵심 observation에서 출발합니다. LLM.int8은 아주 흥미롭게도 모델의 크기가 커지면(>13B) 특정 hidden dimension에서만 outlier가 발생하기 때문에 batch, token 번호와 관계 없이 정해진 dimension만 골라내어 fp연산을 할 수 있다고 주장합니다.

SmoothQuant는 이것에 착안하여 y=XW 연산에서 X의 outlier가 많이 발생하는 dimension의 값을 W로 migration해버립니다. 어차피 W는 압축이 잘되니까 약간 X를 평탄화 시키고, W를 조금 혼란스럽게 해도 적절하게 둘다 잘 될것이라고 생각하는 것이죠 (그림을 보시면 이해가 잘 가실겁니다). 이것을 dynamic하게 migration하는 것은 말이 안되지만, LLM.int8이 말하듯이 정해진 dim.에서만 나오니까 calibration dataset으로 미리 알아서 압축 해버릴수 있겠죠. (사실 Quantization 좀만 해보신 분들은 Qualcomm의 DFQ 논문의 Layer Equalization이 생각나실겁니다. 아마 송한교수도 이것때문에 Contribution이 부족하다고 생각하지 않았을까요.)

이렇게 압축하면 layer-wise로도 잘됩니다. dynamic quant.를 안해도 됩니다. 즉, overhead를 확실히 줄일수 있을겁니다. 논문에서는 tensor-wise라고도 하는데, 통짜로 scaling factor를 뽑아도, OPT/BLOOM/GLM 모두 압축이 잘됩니다. 그리고 ZeroQuant는 밟혀버렸군요.

가속 성능은 여전히 아쉽습니다. 2x Throughput, 잘해야 1.x배 가속이 결과입니다. 실제 FasterTransformer에서 Baseline과 LLM.int8과 Smoothquant 결과를 같이 보여준 것은 이쪽 연구/개발하시는 분들께 좋은 reference가 될것 같네요.

문제점을 지적해보라면, 175B보다 작은 모델 결과가 궁금합니다. 사실 175B 모델 같은거 서비스에 쓰기 어렵거든요. SmoothQuant도 가속 결과는 작은 모델에서 보여주는데, 압축 결과는 안보여줍니다. 과연 LLM.int8의 observation이 얼마나 어디까지 먹히는 걸까요? 저는 여전히 의문을 가지고 있습니다.

제가 말씀드린 논문들은 아래와 같구요.

-   ZeroQuant: Efficient and Affordable Post-Training Quantization for Large-Scale Transformers, [https://arxiv.org/abs/2206.01861](https://l.facebook.com/l.php?u=https%3A%2F%2Farxiv.org%2Fabs%2F2206.01861%3Ffbclid%3DIwAR1YDiY_P7h6ztTPUSRoThe0gofHEmh4pqZPDOoDsg54NrFTxvq5DG4vbT0&h=AT2O4pTOP3PDSVhhok1DcJop1Wz0U5Gy4D7sSfH36HBtvvcxg0ji7nyzMJjlbVZVlZyCfbr6W_OaTjofC7iQdddkrPWXdWC1elNyjWpSjG1Anh20vjuyuEmyfkj1nzmtUpc-&__tn__=-UK-R&c[0]=AT1bcs1vL7XlP9H6XkMDRb2EreThnqt_S02AE4s4GEeno1IRpdHTRrbsicoFPW1gSvfpVt4Yb6YwUNVtlRuhP6TBUiZy5fhR55C4Gjv3_5KjS3KcoDJYtSYYkMqI6S5a1_iluAf43U8KtqeH1TQvxdECOhzcH6IwMZs-d6PqY5jmQ7QDxI6cvqxCEiI8lMBDgzCiDALB6viA8Q0v7S8FY9g), Neurips 2022.
    
-   LLM.int8(): 8-bit Matrix Multiplication for Transformers at Scale, [https://arxiv.org/abs/2208.07339](https://l.facebook.com/l.php?u=https%3A%2F%2Farxiv.org%2Fabs%2F2208.07339%3Ffbclid%3DIwAR2MDrD8VJ9x37XhmHq_cKQ-1eyGLHStqPY8pYoBoeLIJnKsmam72ZSHc-8&h=AT1qVywyF3vihBJ6GHFeXda1JxcOffCVpCAMxyGQc9e27JGiWNrxHzG01q7U1BvY_iv-TJblDLSfSu6FT_aWVWg5HCpIzCDX8LYuFd3Ryo0J_S5JQ9vMEZSP5KU6TZZZq3b2&__tn__=-UK-R&c[0]=AT1bcs1vL7XlP9H6XkMDRb2EreThnqt_S02AE4s4GEeno1IRpdHTRrbsicoFPW1gSvfpVt4Yb6YwUNVtlRuhP6TBUiZy5fhR55C4Gjv3_5KjS3KcoDJYtSYYkMqI6S5a1_iluAf43U8KtqeH1TQvxdECOhzcH6IwMZs-d6PqY5jmQ7QDxI6cvqxCEiI8lMBDgzCiDALB6viA8Q0v7S8FY9g)**,** Neurips 2022.
    
-   SmoothQuant: Accurate and Efficient Post-Training Quantization for Large Language Models, [https://arxiv.org/abs/2211.10438](https://l.facebook.com/l.php?u=https%3A%2F%2Farxiv.org%2Fabs%2F2211.10438%3Ffbclid%3DIwAR0isJ2cBLfaetAr_geIgdkjBlZSqy93I9joSeFvtl0ZxZBC7fz9r7X6szQ&h=AT0svAh2ROezaEgkm58OPcuxC5Vc26tRvXxwFLSYqoACA4CH8VPtsOwFaldAdNcovFM2fjJfzXLJTuhd1F20j39jPKiq1iwSRVmiAo-0wYQT8yHkULRNpZ0jPh0q52STFg-u&__tn__=-UK-R&c[0]=AT1bcs1vL7XlP9H6XkMDRb2EreThnqt_S02AE4s4GEeno1IRpdHTRrbsicoFPW1gSvfpVt4Yb6YwUNVtlRuhP6TBUiZy5fhR55C4Gjv3_5KjS3KcoDJYtSYYkMqI6S5a1_iluAf43U8KtqeH1TQvxdECOhzcH6IwMZs-d6PqY5jmQ7QDxI6cvqxCEiI8lMBDgzCiDALB6viA8Q0v7S8FY9g)
    

혹시 이에 대한 저희 팀의 관점이 궁금하시면 아래 논문을 참고해주세요.

-   nuQmm: Quantized MatMul for Efficient Inference of Large-Scale Generative Language Models, [https://arxiv.org/abs/2206.09557](https://arxiv.org/abs/2206.09557?fbclid=IwAR1qgUvi3UJAU6n-3I4-qHt54nJFUvMZPoAG-YO9TOwZ43M7yG2s2C-KhkA)
    
-   AlphaTuning: Quantization-Aware Parameter-Efficient Adaptation of Large-Scale Pre-Trained Language Models, [https://arxiv.org/abs/2210.03858](https://arxiv.org/abs/2210.03858?fbclid=IwAR2MDrD8VJ9x37XhmHq_cKQ-1eyGLHStqPY8pYoBoeLIJnKsmam72ZSHc-8)
    

읽어주셔서 감사합니다. 새해 복 많이 받으시고 더 행복하시고 꿈꾸는 바에 더 한발짝 다가가는 한해 되시기 바랍니다.