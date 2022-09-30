https://arxiv.org/abs/2208.01864

Pyramidal Denoising Diffusion Probabilistic Models (Dohoon Ryu, Jong Chul Ye)

ddpm 모델은 보통 한 resolution에서 학습되고 그 resolution에서만 샘플링을 하는데, 한 모델을 여러 resolution에서 학습시키고 샘플링 시점에 가장 작은 resolution에서부터 시작해 super resolution을 하도록 한 방식. 샘플링 속도가 빨라지고 동시에 학습된 모델은 super resolution도 지원하게 되네요.

#ddpm