https://arxiv.org/abs/2003.04887

ReZero is All You Need: Fast Convergence at Large Depth (Thomas Bachlechner, Bodhisattwa Prasad Majumder, Huanru Henry Mao, Garrison W. Cottrell, Julian McAuley)

트랜스포머의 각 residual block에서 layer norm을 제거하고 마지막 레이어에 0으로 초기화된 학습 가능한 multiplier를 달아줘서 학습 초기에 identity처럼 동작하게 만드는 방법. 학습이 더 빠르다는 것이 장점. fixup이나 skipinit와 동일한 선상.