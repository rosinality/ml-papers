https://arxiv.org/abs/2112.05682

Self-attention Does Not Need $O(n^2)$ Memory (Markus N. Rabe, Charles Staats)

메모리 소모량이 O(logn), 실용적으로는 O(sqrtn)인 attention 계산 방법. softmax normalize를 한 다음 attention을 계산하는 것이 아니라 unnormalized score에 대해 계산한 다음 normalize를 하는 식으로 순서를 바꿨습니다. 물론 unnormalized score에 대해 그냥 계산하면 값이 터지니 max 값 추적도 같이 들어갑니다.

시간 복잡도는 여전히 O(n^2)이지만...메모리에 들어가면 일단 돌아는 가겠네요.

#efficient_attention 