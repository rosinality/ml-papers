https://arxiv.org/abs/2306.12929

Quantizable Transformers: Removing Outliers by Helping Attention Heads Do Nothing (Yelysei Bondarenko, Markus Nagel, Tijmen Blankevoort)

transformer에서 quantization을 어렵게 하는 outlier들은 대체 왜 생기는 것일까? 이 논문의 제안은 attention이 residual path의 hidden representation을 업데이트 하지 않는 동작(no-op)을 수행하기 위해 만들어진다는 것이네요. 따라서 이런 no-op 동작을 수행할 수 있는 메커니즘(gating 등)을 추가하면 outlier가 상당히 억제된다고 합니다.

quantization을 위한 것이긴 하지만 transformer의 동작에 대해 알려주는 바가 있는 듯 하네요. 100M 수준의 작은 모델에 대한 결과라 더 큰 모델에서의 패턴이 어떨지는 탐색의 여지가 있을 듯 하지만 여하간 흥미롭습니다.

#transformer 