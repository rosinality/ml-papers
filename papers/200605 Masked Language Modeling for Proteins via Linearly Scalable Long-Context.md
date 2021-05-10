https://arxiv.org/abs/2006.03555

Masked Language Modeling for Proteins via Linearly Scalable Long-Context
  Transformers (Krzysztof Choromanski, Valerii Likhosherstov, David Dohan, Xingyou Song, Andreea Gane, Tamas Sarlos, Peter Hawkins, Jared Davis, David Belanger, Lucy Colwell, Adrian Weller)

특정한 sparse attention 패턴 없이 효율적인 attention을 계산하기. (QK)V 대신 Q(KV)를 하는 것이 핵심. 이렇게 했을 때 Q, K를 특정한 함수로 매핑하면 attention 연산에서 등장하는 커널 행렬을 근사할 수 있다는 것을 보임.