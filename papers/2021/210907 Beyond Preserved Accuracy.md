https://arxiv.org/abs/2109.03228

Beyond Preserved Accuracy: Evaluating Loyalty and Robustness of BERT Compression (Canwen Xu, Wangchunshu Zhou, Tao Ge, Ke Xu, Julian McAuley, Furu Wei)

bert compression에서 accuracy 같은 메트릭 뿐만 아니라 teacher와 student 사이의 예측 레이블의 차이, 예측 확률 분포의 차이 등을 고려해보자 이런 아이디어군요. 예측 레이블은 비슷비슷한데 예측 확률은 차이가 꽤 있어보이네요. distillation이 들어가면 예측 확률의 차이가 줄어든다는 결과. 추가로 post training quantization을 하면 adversarial attack에 대한 robustness가 꽤 향상되는군요.

#bert #lightweight #distillation 