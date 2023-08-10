https://arxiv.org/abs/2304.15004

Are Emergent Abilities of Large Language Models a Mirage? (Rylan Schaeffer, Brando Miranda, Sanmi Koyejo)

지금 화제가 되고 있는 논문이기도 하고, 내가 관심 있는 주제와도 관련이 있어서 공유. 간단하게 소개하면 LLM의 창발적인 특성, 즉 특정한 능력이 일정 규모를 넘어가는 시점 이후에만 나타나는 현상에 대한 논문이다. (물리학자들이 이런 현상을 창발적이라고 불러도 되는가에 대해서 문제를 삼기도 하지만...일단 그건 차치하고.)

위 논문의 요점은 이 현상이 불연속적이거나 비선형적인 메트릭을 쓰기 때문이라고 본다. 즉 Cross Entropy 같은 지표에 대해서는 모델이 점진적으로 계속 개선되고 있는데, 정확도 같은 메트릭은 그 지표가 일정 수준 이상으로 낮아지는 시점에서만 눈에 띄게 상승하기 때문에 창발적인 것처럼 보인다는 것이다. 그러니 선형적인 메트릭을 쓰면 Cross Entropy의 개선이 메트릭에 대해서도 나타나게 되고 창발적인 현상은 사라진다. 모델 규모나 혹은 학습 FLOPS에 대해 각 과제들에 대한 성능도 점진적으로 개선되는 것이다.

그런데...사실 이 가능성은 창발적 특성을 다룬 원 논문에서도 제기하고 있다. (https://arxiv.org/abs/2206.07682) Appendix A에 나오는 설명인데, 논문에서 나타난 창발적 특성이 사실 Cross Entropy는 계속해서 개선되고 있는데 사용한 메트릭 때문에 보이지 않는가 하는 가설을 테스트한다. 겹치는 내용인데 이 논문에서는 이 Appendix를 언급하고 있지 않은 것 같아 약간 이상하다 싶다.

어쨌든 원 논문의 Appendix에서도 실제로 Cross Entropy는 학습 FLOPS에 따라 점진적으로 개선되기는 하고, 메트릭에는 그 변화가 바로 반영되지 않는다는 것을 발견한다. 그런데 추가로 여기서 발견하는 것은 Cross Entropy가 점진적으로 감소하지만, 창발적인 특성이 나타나는 지점에서는 Cross Entropy가 급격하게 감소하는 현상이 나타나거나, 혹은 정답과 오답의 확률의 차이가 증가하기 시작하는 지점이 있다는 것이다. 이렇게 보면 창발적인 요소는 여전히 존재한다고 말할 수 있는 것처럼 보인다.

이전에 다룬 논문의 결과도 그렇고 (https://arxiv.org/abs/2303.13506) 나는 여전히 특정 능력은 특정 규모 이상에서만 현저히 나타난다고 볼 수 있는 증거가 좀 더 강력하지 않은가 싶다. 그리고 실용적인 관점에서도, 능력이 조금씩 개선되고 있다고 하더라도 그것이 유의미해지는가의 기준은 근본적으로 불연속적이거나 비선형적인 점이 있을 수 있다고 본다. 즉 정확도가 모델의 개선을 반영하는 것에는 별로 좋은 지표가 아닐 수 있지만, 실용적으로 모델이 의미 있는 수준이 되었는가 하는 점에 대해서는 괜찮은 지표일 수 있다.

그리고 여전히...지금 중요한 문제 하나에 대해서는 아직 증거가 부족한 듯 싶다. 그건 작은 모델을 더 많은 데이터에 학습하는 것으로 더 큰 모델을 더 적은 데이터에 학습한 것과 동등한 특성을 가질 수 있는가 하는 것이다.

Chinchilla Optimal, 그리고 LLaMA가 추가로 제공한 증거는 비교적 작은 LLM도 더 많은 데이터에 대한 학습으로 더 큰 모델의 학습 Loss를 따라잡을 수 있다는 것을 시사한다. 그렇다면 문제는 그렇게 만든 모델, 즉 학습 Loss가 동일한 작은 모델과 큰 모델은 그 모델이 보여주는 특성과 능력의 측면에서 동일한가 하는 것이다. 동일하다면 작은 모델을 더 오래 학습하는 것은 좋은 전략이면서 최선의 전략일 수 있다. 왜냐면 그만큼 추론 비용을 아낄 수 있으니까. 그렇지 않고, 작은 모델과 큰 모델은 학습 Loss가 비슷하더라도 질적으로 다르다면, 우리는 모델을 우리가 원하는 특성을 가질 수 있는 정도까지 키워야 한다.