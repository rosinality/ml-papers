https://arxiv.org/abs/2002.04724

Improved Consistency Regularization for GANs (Zhengli Zhao, Sameer Singh, Honglak Lee, Zizhao Zhang, Augustus Odena, Han Zhang)

consistency regularization, 즉 mixmatch 같이 augmentation을 준 샘플에 대해서 prediction이 변화하지 않게 만드는 regularization을 GAN에 쓴 결과. 사실 기본이 되는 연구는 이미 이전에 있었는데 놓쳤다... (Consistency Regularization for Generative Adversarial Networks, https://arxiv.org/abs/1910.12027) 여기서는 real sample에만 augmentation을 먹여서 아티팩트가 발생하는 문제 (그림 2) 를 generated sample에도 augmentation을 적용하는 방식으로 해소하고 generator의 latent code에도 augmentation을 적용해보는 방식으로 개선.

[[200611 Training Generative Adversarial Networks with Limited Data]]

#gan #augmentation #consistency_regularization