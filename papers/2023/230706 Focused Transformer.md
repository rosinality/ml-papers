https://arxiv.org/abs/2307.03170

Focused Transformer: Contrastive Training for Context Scaling (Szymon Tworkowski, Konrad Staniszewski, Mikołaj Pacek, Yuhuai Wu, Henryk Michalewski, Piotr Miłoś)

knn + long context 상황에서 distractor에 영향을 받는 것을 방지하기 위한 학습 배치 구성이네요. 구체적으로는 배치에서 문서의 이전 context와 현 context를 임베딩하고, 나머지 다른 문서들도 임베딩한 다음 다른 문서들에서 나온 임베딩을 distractor로 쓰는 방식입니다. 배치 내에서 처리하므로 학습 가능해서 query-key가 distractor에 대해 강인해진다는 주장을 하네요.

정작 knn은 논문의 메인 모델인 longllama에는 안 썼으니 이 배치 구성이 요점이라고 할 수 있지 않을까 싶네요. pass key retrieval을 가뿐히 256k 까지 성공했는데...세팅 자체가 pass key retrieval에 좀 유리한 것은 아닐까 싶습니다.

#efficient_attention 