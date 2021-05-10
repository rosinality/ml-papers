https://arxiv.org/abs/2005.07093

Bayesian Bits: Unifying Quantization and Pruning (Mart van Baalen, Christos Louizos, Markus Nagel, Rana Ali Amjad, Ying Wang, Tijmen Blankevoort, Max Welling)

N 비트 양자화된 결과 x_N을 x_2와 k 비트 양자화에 대한 오차 r_k의 합으로 표현. (x_N = x_2 + r_4 + r_8 + ...) 이 term들에 모두 게이트를 붙여주면 양자화 수준을 학습할 수 있고 더 나아가 아예 0이 되게 만들 수도 있음. (프루닝) 이 게이트를 variational inference로 학습.