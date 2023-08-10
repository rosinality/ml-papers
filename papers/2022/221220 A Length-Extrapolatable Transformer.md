https://arxiv.org/abs/2212.10554

A Length-Extrapolatable Transformer (Yutao Sun, Li Dong, Barun Patra, Shuming Ma, Shaohan Huang, Alon Benhaim, Vishrav Chaudhary, Xia Song, Furu Wei)

나온지 좀 된 논문이긴 하지만 이번 LLaMA와 관련해서 흥미로운 부분이 있지 않은가 싶습니. LLaMA의 특이한 결정 중 하나가 RoPE를 매 레이어마다 더하는 방식을 썼다는 것인데, 이와 관련해서 ALiBi가 long range에 대해 attention weight를 감쇠시키는 방식으로 extrapolation에 대응했다면 오히려 학습 입력 길이 범위 내에 대해서는 해로울 수 있는 것이 아닌가 하는 아이디어였네요. 그런 점에서는 RoPE가 나은 것이 아닌가...하는 발상입니다. (이 논문에 국한하지 않더라도 이렇게 말하는 사람이 있는 것 같더군요.)

이 논문에서는 좀 더 나아가 RoPE의 개선 버전을 만들어서 사용했다고 할 수 있을 것 같습니다.

나머지 결정인 매 레이어에 더하는 방식은 과거 deep transformer 연구에서 input에 더해주는 것만으로는 레이어가 깊어질수록 positional embeding의 효과가 감소한다는 연구를 떠오르게 하는 점이 있습니다. (이 논문 제목이 기억이 안 나네요.) 그 이후로도 DETR 등에서 종종 등장하기도 했죠. 그런데 깊은 모델에 대해서 별 영향이 없지 않았나? 한다면 causal mask가 사용되면 attention이 토큰의 위치를 알 수 있다는 발견과 관련이 있지 않을까 싶습니다. https://arxiv.org/abs/2203.16634 positional embedding이 존재하는 경우에도 attention이 이런 식으로 학습되어 추가적인 정보를 제공하는 방식으로 작동할 가능성이 높지 않을까 싶네요.

#transformer #positional_encoding 