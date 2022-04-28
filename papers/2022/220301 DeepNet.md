https://arxiv.org/abs/2203.00555

DeepNet: Scaling Transformers to 1,000 Layers (Hongyu Wang, Shuming Ma, Li Dong, Shaohan Huang, Dongdong Zhang, Furu Wei)

pre norm의 안정성과 post norm의 성능. post norm을 사용하는 경우 학습 초반에 큰 크기의 업데이트가 발생하고 이 업데이트가 layer norm과 맞물려 gradient vanishing이 발생한다는 분석. 사실 학습 초반에 너무 큰 업데이트가 발생하는 것이 문제라는 게 warmup의 문제의식이기도 했죠.

그래서 학습 초반의 업데이트가 폭발하지 않도록 그 크기를 제한하도록 했는데...결과적으로 layernorm(x * a + f(x) * b) 형태에서 a를 키우고 b의 크기를 줄이는, 즉 skip connection의 크기를 키우는 형태가 됩니다. zero init 같은 걸 생각해보면 친숙한 결과네요.

이걸 써서 모델을 1000 레이어까지 확장할 수 있다는 것을 보였습니다. 겸사겸사 width를 키우는 것보다는 depth를 키우는 것이 더 나은 scaling을 보여준다는 것까지 보였네요.

#transformer #normalization 