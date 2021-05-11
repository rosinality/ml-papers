좋은 논문이 또 쏟아지는 시점이지만...좀 더 들여다보고 있는 논문 두 편.
https://arxiv.org/abs/2101.03697
RepVGG: Making VGG-style ConvNets Great Again
make great again의 시대는 끝났으니 VGG is back이라고 하는 것이 적절할 듯 싶지만. vgg 스타일로 스킵 커넥션도 없고 dense connectivity도 없고 bottleneck도 없이 심플하게 3x3 conv와 bn, relu를 쌓아 만든 모델. 단순한 만큼 resnet보다 빠르면서도 성능도 더 좋다. 성능을 끌어올린 방법은 학습 시점에는 3x3 conv 뿐만 아니라 1x1 conv와 identity connection branch도 만들어서 이 branch의 합을 사용해 학습시키고 inference 시점에서는 이 branch들을 3x3 conv에 밀어넣는 것. 이런 생각을 어쩌다 했는지 좀 신박함.
지금은 약간 cnn의 황혼 같다는 느낌이 들긴 하지만 모델을 어떻게 더 잘 학습시킬 것인가가 여전히 중요하다는 것을 시사하는 것 같음. 실용적으로도 쓸모가 있을 수 있을 것 같고.
https://openreview.net/forum?id=1FvkSpWosOl
Is Attention Better Than Matrix Decomposition?
attention은 아닌데 attention 같고 attention이랑 바로 비교하면 안 될 것 같은데 어쨌든 attention을 대체하는 모듈. attention 대신 nmf 같은 matrix factorizaton을 수행하는 모듈을 끼워넣기. matrix factorization 특성상 n by n 행렬을 만드는 문제 같은 게 없기 때문에 특히 큰 길이의 입력에 대해 더 효율적. 각 샘플에 대해 iterative하게 code를 만들어나가는 과정이 사실 말이 되는 것 같기도 하고 그렇다. (물론 나온 성능이 이미 말이 된다.)
semantic segmentation하고 좀 niche하게 보이기도 하는 gan에 self attention 대신 끼워넣기를 실험했다. 이 밖에서도 효과가 나타날지가 가장 문제가 되긴 할 텐데. 어쨌든 efficient attention에서 곧잘 나오는 접근 뿐만 아니라 이런 방향도 있을 수 있다는 것. (attention하고 바로 비교하면 안 될 것 같은데 계속 이쪽 방향과 맞춰보게 되는 건 어쩔 수 없다.)