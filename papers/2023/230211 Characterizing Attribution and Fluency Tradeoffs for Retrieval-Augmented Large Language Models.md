https://arxiv.org/abs/2302.05578

Characterizing Attribution and Fluency Tradeoffs for Retrieval-Augmented Large Language Models (Renat Aksitov, Chung-Ching Chang, David Reitter, Siamak Shakeri, Yunhsuan Sung)

retrieval augment가 lm의 hallucination 문제를 해소할 수 있는 수단으로 여겨지고 있지만 그냥 retrieve 해서 앞에 붙인다고 해서 되는 문제는 아니겠죠. fluency (그럴 듯하고 퀄리티 높은 텍스트 생성)과 accountability (근거 텍스트에 충실한 텍스트 생성) 에 trade off가 발생하리라고 생각하고 이 두 메트릭을 자동 측정할 수 있는 방법 개발, 그리고 여러 조건에서 이 스코어가 어떻게 변화하는지를 분석했네요.

take away 메시지를 보면 결과적으로 좋은 retriever를 사용해서 context length를 넘지 않을 정도로 사용해야 하고 작은 모델을 쓰는 경우는 샘플을 여러 개 뽑아서 re-ranking을 해야한다가 되는 군요.

#retrieval #llm 