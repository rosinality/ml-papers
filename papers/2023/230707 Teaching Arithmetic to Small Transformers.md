https://arxiv.org/abs/2307.03381

Teaching Arithmetic to Small Transformers (Nayoung Lee, Kartik Sreenivasan, Jason D. Lee, Kangwook Lee, Dimitris Papailiopoulos)

transformer로 arithmetic을 어떻게 학습시켜야 generalizable한가에 대한 연구. 일반적으로 하는 것처럼 123 + 456 = 579 같이 학습시키는 것은 suboptimal하다고 보고 있네요. 결과 자릿수를 뒤집어 123+456 = 975와 같이 하는 것만으로도 성능이 갑자기 뛰어오릅니다. 덧셈 알고리즘 자체가 뒤에서부터 시작한다는 것을 생각하면 자연스럽죠.

그러나 이런 트릭을 모든 연산에 대해서 쓸 수는 없고...그래서 cot 기반의 scratchpad를 사용하는 방법을 고려합니다. 이걸로 곱셉 뿐만 아니라 sin이나 sqrt 계산까지 해냈네요.

계속 지적되어온 autoregressive 모델의 planning과 working memory 문제를 생각하게 되네요. 이 문제를 돌파할 수 있다면 많은 것이 풀릴 듯 한데...그럴 수 있는 방법을 상상하기가 쉽지 않네요.

#transformer 