https://arxiv.org/abs/2202.01169

Unified Scaling Laws for Routed Language Models (Aidan Clark, Diego de las Casas, Aurelia Guy, Arthur Mensch, Michela Paganini, Jordan Hoffmann, Bogdan Damoc, Blake Hechtman, Trevor Cai, Sebastian Borgeaud, George van den Driessche, Eliza Rutherford, Tom Hennigan, Matthew Johnson, Katie Millican, Albin Cassirer, Chris Jones, Elena Buchatskaya, David Budden, Laurent Sifre, Simon Osindero, Oriol Vinyals, Jack Rae, Erich Elsen, Koray Kavukcuoglu, Karen Simonyan)

routing networks (mixture of experts)에 대한 scaling law. dense 모델 (number of experts = 1 인 케이스) 크기와 number of experts를 사용해 scaling behavior를 기술할 수 있다는 것을 보였네요. 이를 사용해 moe 특유의 뻥 파라미터가 아닌 dense model에 상응하는 effective parameter count를 계산하고 이 파라미터 수에 대해 dense model과 일치하는 성능 곡선을 얻었습니다.

그 외에도...지금 쓰는 moe 세팅들(sparse moe, K = 1 등)이 가장 쓸만한 것 같다는 결과도 얻었네요.

#mixture_of_experts