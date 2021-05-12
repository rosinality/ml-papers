https://arxiv.org/abs/2006.06676

Training Generative Adversarial Networks with Limited Data (Tero Karras, Miika Aittala, Janne Hellsten, Samuli Laine, Jaakko Lehtinen, Timo Aila)

augmentation T와 분포 x, y에 대해서 x = y일 때에만 Tx = Ty여야 T가 적용된 분포에 대해 학습했을 때에도 결과적으로 분포 x, y를 학습할 수 있음. 이 조건을 만족하는 augmentation 파이프라인을 구축하고 adaptive하게 튜닝하는 방법을 사용. 샘플 수가 적은 경우 & 파인튜닝 상황에서 놀라운 결과. 그리고 GAN에는 역시 기하학적 변환이 가장 효과적인 듯.

#gan #augmentation 