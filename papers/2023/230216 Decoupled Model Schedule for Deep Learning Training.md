https://arxiv.org/abs/2302.08005

Decoupled Model Schedule for Deep Learning Training (Hongzheng Chen, Cody Hao Yu, Shuai Zheng, Zhen Zhang, Zhiru Zhang, Yida Wang)

AWS 쪽에서 나온 학습 최적화 프레임워크군요. torch.fx 기반으로 operator fusion, 커널 갈아끼우기, tensor parallelism, pipeline parallelism 등의 적용을 자동 최적화하기 위한 도구네요. https://github.com/awslabs/slapo 코드도 공개되어 있습니다. 이쪽 연구들은 코드량을 같이 기술하던데 3k 정도면 그래도 동종 업계에서는 가장 작은 편이군요.

그래프를 편집하는 방식의 최적화와 모듈을 갈아끼우는 방식의 최적화 중 어느 쪽이 더 효과적이고 편리한가의 문제는 중요한 디자인 결정인 것 같긴 합니다.

#efficient_training #distributed_training 