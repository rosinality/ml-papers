https://arxiv.org/abs/2202.06417

A Contrastive Framework for Neural Text Generation (Yixuan Su, Tian Lan, Yan Wang, Dani Yogatama, Lingpeng Kong, Nigel Collier)

autoregressive 모델에서 멀쩡한 텍스트 시퀀스를 샘플링하는 것도 까다로운 작업이죠. 디코딩을 잘못하면 반복적인 토큰을 생성한다거나. 여기서는 hidden state 사이의 similarity를 패널티로 줘서 contrastive loss를 학습에 적용하고 디코딩 시에도 hidden state 사이의 similarity를 패널티로 고려하는 방법을 적용했네요. 스코어가 mle + nucleus에 비해 유의미하게 잘 나오는 것 같은데 어느 정도의 의미가 있을지 궁금하네요.

#lm #decoding 