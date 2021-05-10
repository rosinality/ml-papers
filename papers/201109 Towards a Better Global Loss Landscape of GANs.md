https://arxiv.org/abs/2011.04926

Towards a Better Global Loss Landscape of GANs (Ruoyu Sun, Tiantian Fang, Alex Schwing)

일반적인 gan loss formulation에서는 loss landscape에 bad basin/suboptimal minima가 많다고. 문제에 대한 답은 relativistic gan의 재발견.


https://proceedings.neurips.cc/paper/2020/file/f885a14eaf260d7d9f93c750e1174228-Paper.pdf

gan에서 semantic한 feature들을 disentangle하기 위한 개선. 핵심은 convolution에서 group structure를 학습으로 추출해내고 이 group 정보를 활용해 adaptive instance/group normalization 혹은 modulation을 수행하는 것. 더 나은 성능과 함께 local한 semantic한 특징들을 다른 특징들은 고정한 채로 조작할 수 있게 됨. stylegan2의 뒤를 이을 모델의 탄생일지도!