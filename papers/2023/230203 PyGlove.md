https://arxiv.org/abs/2302.01918

PyGlove: Efficiently Exchanging ML Ideas as Code (Daiyi Peng, Xuanyi Dong, Esteban Real, Yifeng Lu, Quoc V. Le)

머신 러닝 모델 개발에서 발생하는 수많은 변경과 실험에 대해 대응할 수 있는 코드를 어떻게 만들 것인가군요. 예를 들어 resnet의 conv를 전부 dw conv로 바꾸고 싶다면 어떻게 할 것인가? 같은 문제를 생각해볼 수 있겠습니다. 여기서 제안하는 것은 symbolic programming과 패치 기반 수정이군요.

여기에 대한 대안이 있는가? 라고 하면 전 dependency injection과 강력한 configuration system 기반 설계가 아닐까 합니다. 서로 장단이 있을 것 같은데 좀 더 생각해봐야겠네요. 여하간 ML 실험과 개발에 맞는 프레임워크의 확립이 요청되는 시점이라고 생각합니다.

파이토치 쪽에서는 torch.fx로 그래프를 패치하는 방법을 생각해볼 수 있겠네요.

#mlops 