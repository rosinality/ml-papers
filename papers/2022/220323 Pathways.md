https://arxiv.org/abs/2203.12533

Pathways: Asynchronous Distributed Dataflow for ML (Paul Barham, Aakanksha Chowdhery, Jeff Dean, Sanjay Ghemawat, Steven Hand, Dan Hurt, Michael Isard, Hyeontaek Lim, Ruoming Pang, Sudip Roy, Brennan Saeta, Parker Schuh, Ryan Sepassi, Laurent El Shafey, Chandramohan A. Thekkath, Yonghui Wu)

얼마 전 나왔던 Pathways (https://blog.google/technology/ai/introducing-pathways-next-generation-ai-architecture/) 와는 약간 포인트가 다릅니다. 이쪽은 TPU들에 대해 어떻게 분산 처리를 할 것인가에 대한 문제입니다.

파이토치 같은 경우에 각 GPU마다 같은 프로그램을 띄워서 필요할 때 각 프로그램이 collective operation을 수행하는 방식이죠(multi controller). 그런데 과거 TF 같은 경우는 하나의 프로그램에서 computation graph를 쪼개 각 worker들에 대해 나눠주는 방식이었습니다(single controller). multi controller가 기본적으로 더 효율적이긴 하지만 유연하지는 않습니다. 파이프라이닝을 한다거나 모델이 sparse한 task들로 구성되어 있어 서로 다른 worker에서 서로 다른 연산을 수행하는 것이 자연스럽다면 효율성이 떨어지죠.

Pathways는 single controller 모델의 유연성에 multi controller 모델의 효율성을 결합할 수 있는가를 태클하기 위한 제안이네요. 이걸 최적화하기 위해 많은 작업이 필요하지만...사용자 입장에서는 함수를 정의하고 각 함수에 할당할 디바이스의 수를 정의한 다음 이 함수들을 연결하는 것으로 끝납니다.

위의 Pathways와는 다르지만...결과적으로 위의 Pathways가 의도하는 multitask/multimodal sparse model을 구성하기 위한 최적의 도구를 만들었다는 느낌이네요.

다 좋은데...TPU를 잔뜩 가지고 있고 JAX를 쓰는 구글러들이나 쓸 수 있을만한 프레임워크이긴 하네요.