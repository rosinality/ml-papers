https://arxiv.org/abs/2307.08621

딱 세 포인트로 그린 것이긴 하지만 transformer보다 나은 scaling curve를 보여준 극히 드문 결과라 아무래도 뭔가 잠재성이 있지 않을지 생각해보게 된다. 그래서 기존의 linear attention이나 recurrent network와는 어떻게 다른지 한 번 봤다.

일단 기본적인 접근은 다음과 같다.

S(n) = γS(n - 1) + K(n)^T·V(n)
O(n) = Q(n)S(n)

전형적인 linear recurrent network 혹은 state space model처럼 생겼다. S4 같은 모델과 정말 흡사하다고 할 수 있겠는데, 차이가 있다면 Q(n)과 K(n)이 S4 같은 경우에는 고정된 행렬이라면 Retentive Network에서는 토큰에 대한 linear mapping으로 계산되는 값이기에 각 스텝의 토큰에 따라 변화하는 값이라는 것과 과거 state에 대해서 간단한 감쇄 γ를 사용하고 있다는 것.

이렇게 보면 흥미로운 변형으로 보인다. 그런데 recurrent한 형태가 아니라 parallel한 형태로 보면 모양새가 묘하다.

O = (QK^T⊙D)V

linear attention처럼 softmax가 제외되었는데...흔히 linear attention에 등장하는 것처럼 kernel을 사용해서 softmax를 근사하는 대신 D 행렬과 hadamard product를 하는 방식으로 변형되어 있다. D 행렬은 토큰 사이의 거리에 따른 감쇄 γ를 원소로 갖는 행렬이다.

그러니까...softmax를 빼버리고 거리에 따라 attention weight에 가중치를 곱해주는 것으로 충분하다는 것이 된다. 정말로? 물론 swiglu 형태의 gating이나 attention head별 normalization이 들어가 있긴 하지만, 이게 맞다면 애초에 softmax와 혹은 softmax를 근사하기 위한 nonlinearity가 없어도 된다는 의미를 시사하는 것이 아닐까... (물론 hadamard product가 들어가기 때문에 결합 순서를 바꿔 연산 비용을 줄이는 트릭을 쓸 수는 없다.)

이상하다 싶긴 하지만, 많은 사람들이 지적한 것처럼 RWKV와 유사한 것이라고 하면 RWKV도 어느 정도 동작한다는 것이 알려져 있으니 또 가능하지 않으리라는 법도 없는 듯 싶다.

별개로 recurrent한 구조를 다시 가져오려는 시도들에 대해서는 대체로 부정적으로 보기는 했었다. 간단히 그 수많은 토큰에 대한 정보를 하나의 상태 벡터에 밀어넣을 수 없다고 봤기 때문이다. You can't cram the meaning of a whole_ %&!$# sentence into a single $&!# 라는 교훈이 있지 않았던가. 애초에 attention 자체가 한 문장의 의미를 하나의 벡터에 인코딩하는 것이 어려웠기에 등장한 것이다.

그렇지만 이건 2~3층 정도의 256~512 차원 LSTM을 쓰던 시절의 이야기이긴 하고, 수K 레벨의 차원을 수십~수백 층 쌓는 현재의 모델들은 규모 자체가 다르긴 하다. 예를 들어 LLaMA 65B를 생각해보면 8192 차원에 80 레이어 모델이니, 256 차원 단어 벡터를 우겨넣는다고 하면 2560 단어를 그대로 집어넣을 수도 있겠다. 모델이 이렇게 돌아가지는 않지만, 의미적 압축 등도 고려하면 state에 밀어넣을 수 있는 토큰은 여하간 꽤 많을 것이다.

거기다 S4나 retentive network 같은 경우엔 차원의 크기가 Value 차원이 아니라 Key * Value 차원이기에 state의 capacity는 넉넉할 것 같긴 하다. 실제로 문제가 되는 것은 state의 capacity가 아니라 (RWKV에서도 이야기가 많이 나왔듯) 실제로 이러한 recurrent한 구조에서 long range context를 모델링하는 것이 가능한가 하는 쪽일 수도 있지 않을까 싶다.

논문의 결과가 과연 transformer에 대해 공정한 것이었는가 하는 의심이 들긴 하지만...애초에 잘 되는 것이 거의 불가능하다고 생각했던 것이 prior라면 잘 하면 좋은 결과가 가능할 수도 있겠다 하는 생각이 현재 posterior이긴 하다.

여담

논문 실험에 (512개를 쓰긴 했지만) AMD MI200(!)을 사용했다. xPos, Kosmos-1, 2에서 V100을 쓴 것도 그렇고 이쪽을 쓰고 싶어서 쓴 것은 아닐 듯 한데. GPU 자원 경쟁에서 밀린 것인가 싶다.