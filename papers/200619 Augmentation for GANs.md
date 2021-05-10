https://arxiv.org/abs/2006.02595
https://arxiv.org/abs/2006.05338
https://arxiv.org/abs/2006.06676
https://arxiv.org/abs/2006.10738
이번 달에 gan 학습에 augmentation을 한 결과들이 쏟아졌다. 가끔 정말 비슷한 아이디어들이 짧은 기간 내에 연달아 튀어나오는 경우가 있는데 (anchor free detection 같은) 이번에도 비슷한 사례인 듯.
gan 학습에는 지금까지 augmentation이 잘 쓰이진 않았다. 이유는 여러가지 있긴 하겠다. 수렴을 안정화하기 위한 regularization이나 loss의 개선이 관심을 많이 받아온 것도 있고 (wasserstein gan이 수학적으로 아주 우아한 사례를 남겼고, spectral normalization 같은 방법들이 놀라운 결과를 보여주기도 했고.) 다들 안 쓰고 하니까 안 쓴 면도 있겠고.
또한 그냥 적용해보는 정도로는 잘 안 됐다는 것도 이유가 됐을 것이다. 왜냐면 위의 연구들의 공통적인 핵심 아이디어인데 real 이미지 뿐만 아니라 fake 이미지에도 augmentation을 해주는 것이 필요하기 때문이다. 거기에 invertible할 것 같은 조건도 중요한 포착이라고 할 수 있겠다.
약간 거슬러 올라가면 이 아이디어들은 consistency regularization의 형태로 좀 이전에 등장했다. (https://arxiv.org/abs/1910.12027) real 뿐만 아니라 fake 이미지에도 augmentation을 도입해야 한다는 아이디어 또한 consistency regularization에 대한 개선으로 얼마 전에 (https://arxiv.org/abs/2002.04724) 등장했다. 위 연구들은 이 아이디어를 남기고 consistency regularization은 빠진 형태의 모습이 됐다. consistency regularization은 discriminator에 대한 추가적인 forward가 필요하기 때문에 연산량의 측면에서도 위의 방법들이 더 효율적이다 - 결과도 더 효과적이고.
이 연구들을 보면서 좀 아쉽긴 하다. gan 작업을 할 때 왜 gan에는 augmentation을 제한적으로 사용하냐는 말을 몇 번 들었었는데 생각을 발전시키지 못했다는 것이 안타까워서. 그래도 뭐 지금이라도 augmentation에 대해서 좀 더 생각해보게 됐으니 대충 만족한다.