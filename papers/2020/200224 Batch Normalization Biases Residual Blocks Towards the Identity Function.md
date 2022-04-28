https://arxiv.org/abs/2002.10444

Batch Normalization Biases Residual Blocks Towards the Identity Function
  in Deep Networks (Soham De, Samuel L. Smith)

배치놈을 사용해서 깊은 네트워크를 학습시킬 수 있는 이유는 배치놈이 학습 초반에 skip connection path에 비해 residual block의 분산을 억제해서 실질적으로 얕은 네트워크처럼 학습되도록 만드는 효과가 있기 때문이라는 분석. 이를 이용해 FixUp을 단순화한 SkipInit를 제안.

#normalization #optimization #norm_free #initialization