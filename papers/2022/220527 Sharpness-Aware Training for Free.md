https://arxiv.org/abs/2205.14083

Sharpness-Aware Training for Free (Jiawei Du, Daquan Zhou, Jiashi Feng, Vincent Y. F. Tan, Joey Tianyi Zhou)

sam이 꽤 의미있는 결과들을 보여주고 있지만 학습 시간 증가 때문에 부담스럽죠. 몇 에폭 전의 모델 출력 결과와 현 시점 모델 출력 결과 사이의 kl divergence를 패널티로 주거나 혹은 ema weight를 가지고 모델 결과를 뽑아서 패널티를 주는 방식으로 sharpness aware training을 구현했습니다. 메모리를 쓰거나 연산을 쓰거나 둘 중 하나네요.

#regularization