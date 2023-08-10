https://arxiv.org/abs/2305.16264

Scaling Data-Constrained Language Models (Niklas Muennighoff, Alexander M. Rush, Boaz Barak, Teven Le Scao, Aleksandra Piktus, Nouamane Tazi, Sampo Pyysalo, Thomas Wolf, Colin Raffel)

아주 중요한 scaling law 결과가 나왔네요. 데이터 반복이 있을 때(multi epoch)에 대한 scaling law 입니다. 일단 4 epoch 정도까지는 데이터 반복도 새 데이터 정도의 가치가 있다는 것을 발견했고, 데이터 반복이 있을 때 chinchilla scaling law에 비해 모델 크기를 줄이고 학습 토큰을 늘리는 것이 더 optimal 하다는 것을 발견했습니다.

그리고 추가로 natural language의 부족한 부분을 코드 데이터로 채우는 것이 좋은 전략이라는 것 또한 발견했네요.

이제 2T 이상의 토큰이 학습에 필요해지는 시점에서 multi epoch가 의미가 생기는 시점이 가까워져 오고 있고...그에 대비하기 위해서는 반드시 체크해야 하는 결과인 듯 싶습니다.

#llm #scaling 