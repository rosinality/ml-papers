https://arxiv.org/abs/2207.00032

DeepSpeed Inference: Enabling Efficient Inference of Transformer Models at Unprecedented Scale (Reza Yazdani Aminabadi, Samyam Rajbhandari, Minjia Zhang, Ammar Ahmad Awan, Cheng Li, Du Li, Elton Zheng, Jeff Rasley, Shaden Smith, Olatunji Ruwase, Yuxiong He)

llm은 학습도 그렇지만 inference도 문제네요. deepspeed에서 자주 하는 것처럼 모델 weight를 램에 올려놓고 inference 하면서 필요한 weight만 불러와서 계산하는 접근입니다.