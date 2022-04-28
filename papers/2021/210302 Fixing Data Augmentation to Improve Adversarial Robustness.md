https://arxiv.org/abs/2103.01946

Fixing Data Augmentation to Improve Adversarial Robustness (Sylvestre-Alvise Rebuffi, Sven Gowal, Dan A. Calian, Florian Stimberg, Olivia Wiles, Timothy Mann)

augmentation을 model ema와 결합하면 robustness가 향상된다는 결과. 거기에 ddpm으로 생성한 이미지까지 투입해 성능을 대폭 향상시킴. cutmix-ema-ddpm이라는 뉴럴넷 업계의 빛3가 모여 만든 인상적인 결과

사실 biggan이 cifar-10에 좀 약해서. stylegan2-ada나 biggan-cr의 결과를 썼다면 gan도 좀 더 경쟁력이 있는 결과가 나왔을지도.

[[200211 Improved Consistency Regularization for GANs]] [[200611 Training Generative Adversarial Networks with Limited Data]]

[[200619 Denoising Diffusion Probabilistic Models]]

#ddpm #augmentation #generative_model 