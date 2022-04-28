https://arxiv.org/abs/2203.16527

Exploring Plain Vision Transformer Backbones for Object Detection (Yanghao Li, Hanzi Mao, Ross Girshick, Kaiming He)

1. multiscale 구조 없이 single scale 구조로 최상단의 feature만 뽑아도 충분하다는 것. 단 이 최상단의 feature를 upsampling 해서 각 scale 별 feature를 만들기는 합니다. yolof의 single in multi out과 비슷한 케이스라고 할 수 있겠네요.
2. local window를 채택하되 swin 같은 구조는 특별히 필요하지 않고 중간중간 conv나 global attention을 끼워넣어서 window 사이의 information propagation을 추가해주는 것으로 충분하다는 것.
3. imagenet 1k mae pretraining이 imagenet 22k supervised training보다 더 나은 성능을 보인다는 것.

이런 느낌이네요. 결과적으로 swin-l 이상의 규모의 모델에서 레이턴시-성능 이점이 보이긴 합니다만 반대로 그 이상의 규모에서는 성능 이점이 명백해보이네요.

#vit #object_detection #instance_segmentation 