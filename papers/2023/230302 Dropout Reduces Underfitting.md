https://arxiv.org/abs/2303.01500

Dropout Reduces Underfitting (Zhuang Liu, Zhiqiu Xu, Joseph Jin, Zhiqiang Shen, Trevor Darrell)

학습 초기의 dropout은 학습을 쉽게 만들어주고(underfit 감소) 학습 후기의 dropout은 일반화 성능을 높여준다는(overfit 감소) 연구. 그러니 overfit 하는 모델은 학습 후기 dropout이 좋고 underfit하는 모델은 학습 초기 dropout을 쓰는 것이 좋다는 아이디어군요.

underfit/overfit은 어떻게 구분할 것인가? 일반적인 dropout을 사용한다고 가정했을 때 dropout을 쓴 모델이 나으면 overfit이고 안 쓴 모델이 나으면 underfit이라는 가정으로 시도했습니다.

#dropout #regularization 