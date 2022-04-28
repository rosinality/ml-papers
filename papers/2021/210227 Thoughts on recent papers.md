IBRNet: Learning Multi-View Image-Based Rendering
https://arxiv.org/abs/2102.13090 https://ibrnet.github.io/ 매 scene마다 모델을 학습시켜야 한다는 제약이 풀리기 시작하는 중. nerf 스타일의 mlp와 transformer의 조합. cnn 와도 자리 없다.
Pyramid Vision Transformer: A Versatile Backbone for Dense Prediction without Convolutions
https://arxiv.org/abs/2102.12122
디텍션-퍼슨들의 트랜스포머 깎기. 각 scale별로 피라미드를 만들고 낮은 단계의 피라미드에선 key, value에 강한 spatial reduction을 걸어서 연산을 효율화. 물론 여전히 입력 크기가 증가하면 latency가 빠르게 증가하지만 경쟁력 있는 속도를 낼 수 있는 구간이 800px 이상으로 증가했다는 것은 확실히 장점.
비전 문제에 cnn보다 트랜스포머가 나은가? 솔직히 잘 모르겠다. 보통 resnet 혹은 좀 더 나아가 resnext와 비교하는데 비교가 충분하지는 않다고 본다. (res2net, vovnet, resnest 등 좀 더 나은 대안이 있다고 보이기 때문에.) 그래서 이참에 비교를 좀 해보려고는 한다.
그러나 이런 트랜스포머 기반 모델이 가져온 중요한 변화는 있다. 비전 문제에 attention을 끌어온 사례는 이전부터 많았는데, 기존에는 cnn을 attention으로 보강하는 정도에서 이런저런 시도들이 나왔었다. 그러나 ViT라는 마일스톤이 꽂힌 이후에는 비전 문제를 cnn을 기반으로 해서 풀어야 한다는 고정관념이 풀렸다는 느낌이다. (이 점에 대해서는 nerf도 마찬가지로 크게 기여했다고 할 수 있을 것이다.) 이전에 시퀀스 문제를 rnn으로 풀어야 한다는 고정관념이 깨지던 시기처럼.
물론 애초에 그 고정관념을 깨야하는 것이어야 했었냐라고 물으면 단정적으로 말하기는 좀 그렇다. 그렇지만 그런 고정관념이 깨진 이후에 더 많은 탐색이 가능해지고 그 탐색 중에 정말로 의미있는 진전을 발견할 수도 있을 테니.

#review