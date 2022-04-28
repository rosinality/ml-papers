https://arxiv.org/abs/2111.06377

Masked Autoencoders Are Scalable Vision Learners (Kaiming He, Xinlei Chen, Saining Xie, Yanghao Li, Piotr Dollár, Ross Girshick)

masked patch prediction인데 quantization 없이 pixel 단위 디코딩 loss를 걸었네요. 마스킹한 패치는 아예 제외한 상태로 인코더에 입력하고 디코더에 입력에 마스크 토큰을 결합하는 방식이군요. quantization이 없어지니 학습이 심플해지긴 하는데 이건 vit에서만 가능한 접근이 아닐까 싶긴 하네요.

#vit #pretraining 