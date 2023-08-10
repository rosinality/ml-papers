https://arxiv.org/abs/2305.13230

To Repeat or Not To Repeat: Insights from Scaling LLM under Token-Crisis (Fuzhao Xue, Yao Fu, Wangchunshu Zhou, Zangwei Zheng, Yang You)

LLM 시대에 데이터를 더 수급하기 어려우니 multi epoch training을 할만한가에 대한 탐색. 이쪽도 T5로 실험하긴 했는데...결과는 이렇습니다.

1. 일단 multi epoch training이 성능이 떨어지거나 overfit을 유발하는 것은 맞는 듯.
2. 데이터 자체가 많으면 multi epoch training의 문제도 완화되는 듯.
3. 아무래도 multi epoch로 가면 dropout을 써야할수도.

전반적으로 palm에서 실험했던 결과, 즉 아주 나쁘지는 않고 향상이 있을 수도 있는데 역시 one epoch에는 미치지 못하는 것 같다와 상통하는 결과가 아닐까 싶습니다.

#llm