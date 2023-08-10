https://arxiv.org/abs/2305.02790

BranchNorm: Robustly Scaling Extremely Deep Transformers (Yijin Liu, Xianfeng Zeng, Fandong Meng, Jie Zhou)

트랜스포머 normalizatin 잔혹사. post ln 기반으로 y = LN(x + aF(x)), a는 학습 iteration에 따라 천천히 증가시키는 방법입니다. DeepNorm에서도 y = LN(ax + F(x)) 같은 식으로 접근했는데 residual branch의 비중이 높게 잡히는 부작용이 생기니 학습 진행에 따라 감소시키겠다는 아이디어군요.

post ln이 성능상 이점이 있지만 학습이 불안정한데, 일단 학습 초반만 넘기면 된다는 느낌이기도 하네요. 다만 대규모 모델에 대해서도 통할 것인가, 그리고 이런 학습 iteration에 대한 scheduling hyperparameter가 더 생기는 것이 귀찮다, 정도가 문제겠군요.

#normalization #transformer 