어제 나온 EvoNorm(https://arxiv.org/abs/2004.02967)에 대한 간단한 생각.
접근 자체는 구글이 자주 하는 (아마도 더 정확하게는 구글 내 특정인들이 계속 해오고 있는) 뉴럴넷 모델에서 광범위하게 쓰이는 모듈들을 서치해보는 연구들의 연장선이다.
(레딧에 누군가가 You can tell it's computationally intensive by just looking at the authors라고 썼던데... https://www.reddit.com/.../r_evolving.../fmswj8h...)
이번에는 normalization과 activation을 묶어서 서치했다. 이게 normalization 혹은 activation을 분리해서 탐색하는 것보다 흥미로운 부분인 것 같다. 당장 normalization을 먼저 하는 게 나은가 activation을 먼저 하는 게 나은가라는 것도 알 수 있으니까...(더 흥미로운 건 둘 다 아니라는 결과가 나왔다는 것이다.)
서치 논문은 서치 방법이 메인이라고 봐야할텐데 난 탐색의 결과로 나온 것이 어떠한 형태인가에 더 관심을 갖게 된다. 일단 내가 NAS 연구에 관심이 좀 적어서 그런 것도 있고 관심을 가져도 어쩐지 computational power에 여유가 없어서 쓸 일이 적을 것 같아서 그런 것도 있고.
여튼 그러니 서치의 결과물들을 좀 살펴보면 이렇다.
1. EvoNorm-B0
이 친구는 batch statistics를 활용하는 방법으로 나온 결과다. 흥미로운 건 batch norm에서 mean centering이 빠졌다는 것. batch norm에서 mean centering의 의미가 무엇인가에 대한 연구가 batch norm에 대해 분석한 논문 중에 있을 것 같고 있었던 것 같은데 당장 떠오르는 건 없다. 다만 최근 연구 중 filter response normalization (https://arxiv.org/abs/1911.09737)이 mean centering을 빼고 흥미로운 결과를 보여주긴 했다.
또 하나 보이는 것은 instance norm처럼 statistics를 활용한다는 것. 이 둘을 결합하는 것이 의미가 있다는 것은 Batch-Instance Normalization(https://arxiv.org/abs/1805.07925)이나 IBN-Net(https://arxiv.org/abs/1807.09441)에서 보여진 적이 있다. 혹은 Switchable Normalization(https://arxiv.org/abs/1907.10473) 같은 케이스를 생각할 수도 있겠고. 특이한 것은 채널을 나눈다거나 가중치를 줘서 결합한다거나 하는 방식은 아니고 feature map의 값과 결합해서 max로 결합하는 방식이라는 것. 물론 이건 search space의 영향이겠지만.
그리고 feature map의 값이 분모로 들어간 영향 등이 있는지 activation에 해당하는 부분이 눈에 띄지 않는다.
2. EvoNorm-S0
이쪽은 batch statistics가 빠진 버전. batch stat를 활용하면 성능이 일반적으로 더 낫긴 한데 최소 배치 크기 제약이 생기고 moving average 같은 걸 추적해서 반영하기도 해야하고 귀찮은 점이 많이 생기니까. 이 의존성이 없는 버전은 늘 유용하다.
특징적으로는 EvoNorm-B0처럼 mean centering이 없고 group norm처럼 group std를 활용해 normalize 한다는 것. group norm과 비슷하게 보이는데 activation과 normalization이 희한하게 결합되어 있다. 누가 먼저인가를 아예 뛰어넘어 activation은 normalization을 하지 않은 feature map에 적용하고 normalization은 activation을 통과하지 않은 feature map에 대해서 한다. 이건 무슨 둘 다 아닌 동시에 둘 다 하면 된다 이런 결과가 나온 것 같은데...
activation이라고 볼 수 있는 부분은 swish와 같은 형태. swish가 이렇게 재발견됐다.
종합해서 보면 꽤 흥미롭고 이해해보려고 하면 좀 이해가 가는 것도 같은 결과물이 나왔다. classification, instance segmentation, gan 셋에 모두 적용해서 괜찮은 결과가 나왔다는 것도 눈에 띄고. fused kernel을 만들어서 쓸 수 있으면 꽤 재미있을 것 같다.