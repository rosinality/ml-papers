https://arxiv.org/abs/2105.07926

Rethinking the Design Principles of Robust Vision Transformer (Xiaofeng Mao, Gege Qi, Yuefeng Chen, Xiaodan Li, Shaokai Ye, Yuan He, Hui Xue)

이쪽과 같이 보면 더 재미있다. vit에서 robust한 모델을 만들기 위한 아키텍처와 학습 스킴을 탐색. 여러 가지가 있지만 (내가 보기에) 흥미로운 부분은 low level에 cnn을 채택하고 트랜스포머 레이어는 high level에 몰아넣은 것. 인간의 인지를 근사한다고 생각했을 때 cnn이 low level에 대해서는 꽤 좋은 근사이지만 high level에 대해서도 그렇지는 않을 수도 있지 않은가 하는 생각을 했었는데 약간의 근거가 제공되는 것 같기도 하다. nlp에서 시퀀스 간 모델링을 위해 attention이 적합하다면 high level의 시각 인지, 특히 여러 object들의 상호작용이 고려되어야 하는 작업이 필요한 문제에는 cnn보다 attention 같은 선택이 더 적합할 수도 있겠다. 물론 지금까지의 비전 과제에서는 이게 아주 강력한 장점으로 보이는 경우는 그렇게 많지 않다고 생각하는데…그건 과제의 특성일 가능성이 높고, 실제 인지 구조에는 이런 input dependent하고 representation 간의 자유로운 결합을 모델링하기 위한 메커니즘이 있지 않을까 싶네요.

[[210515 Are Convolutional Neural Networks or Transformers more like human vision]]

#vision_transformer #robustness 