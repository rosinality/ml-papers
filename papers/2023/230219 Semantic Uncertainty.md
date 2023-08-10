https://arxiv.org/abs/2302.09664

Semantic Uncertainty: Linguistic Invariances for Uncertainty Estimation in Natural Language Generation (Lorenz Kuhn, Yarin Gal, Sebastian Farquhar)

llm이 모른다고 할 수 있는 방법이 있는가 보니 (늘 뉴럴넷의 문제에 답이 된다고 여겨지는) uncertainty가 있었네요. 여기서 해결하고 싶은 것은 단순히 생성된 시퀀스의 불확실성이 아니라 의미적 불확실성입니다.

일단 M개 시퀀스를 생성한 다음 NLI로 entailment를 체크해서 entail이 되는지를 확인한 다음 entail 되는 시퀀스들을 클러스터링해서 이 클러스터들로 엔트로피를 계산하는 방식입니다. 역시나 uncertainty가 흔히 그렇듯 하나의 샘플을 위해 M개 (여기서는 10개 정도) 샘플링을 해야 한다는 것이 문제인데...요즘 서비스들을 고려하면 쓸 수 있는 방법도 있지 않을까요.

#llm #uncertainty 