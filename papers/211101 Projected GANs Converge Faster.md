https://arxiv.org/abs/2111.01007

Projected GANs Converge Faster (Axel Sauer, Kashyap Chitta, Jens Müller, Andreas Geiger)

더 빠르게 더 좋은 지점에 수렴하는 gan. pretrained feature extractor를 써서 각 scale마다 feature를 뽑아서 discriminator를 다는 방식입니다. 흥미로운 것은 pretrained feature extractor를 학습시키지 않고, 또 feature extractor와 discriminator를 잇는 linear projection도 random initialization한 다음에 학습시키지 않는다는 점이네요. 흥미롭습니다.

#gan