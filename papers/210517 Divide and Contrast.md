https://arxiv.org/abs/2105.08054

Divide and Contrast: Self-supervised Learning from Uncurated Data (Yonglong Tian, Olivier J. Henaff, Aaron van den Oord)

며칠 전에 [https://arxiv.org/abs/2105.05837](https://arxiv.org/abs/2105.05837) 을 끌어와서 unsupervised learning의 시대에도 데이터셋 큐레이션이 중요할 것이라는 이야기를 했었는데…민망하게 바로 uncharted 데이터셋을 사용했을 때 발생하는 curation gap을 팡팡 날려버린 연구가 튀어나왔다. 핵심적인 아이디어는 general 모델을 contrastive learning으로 학습시킨 다음, 클러스터링으로 데이터셋을 쪼개서 각 클러스터에 대한 expert를 만들고 이 class specific expert와 general 모델을 distillation하는 것.도메인 expert와 general 모델을 만들고 distill 한다는 전반적인 구조는 데이터셋 큐레이션 문제에 대해 여러 방향으로 응용 가능한 방법이 될지도 모르겠습니다. 단적으로 각 도메인 데이터셋의 비율을 설정하는 문제가 데이터셋 큐레이션에서 발생한다고 보면 이런 프레임워크로 접근해볼 수 있겠죠.

#self_supervised #dataset #distillation #contrastive_learning 