https://arxiv.org/abs/1904.11486

Image classification에서는 확실히 도움이 되는 것 같지만 (imagenet 1%p) object detection에서는 도움이 되는지 애매하다. 오히려 해로운 것 같기도 하다. shift invariance가 도움이 될 것 같은데 안 되는 것인지도 모르겠다 - 물체가 이동했을 때 feature map도 차이가 발생하는 것이 오히려 도움이 되는가?

덧붙이자면 one stage detection (retinanet/fcos)과 2 stage detection (faster r-cnn)에서의 패턴이 다르다. 전자에서는 떨어지고 후자에서는 향상된다. 왜?

[[200122 StyleGAN 2]]

#invariance #backbone