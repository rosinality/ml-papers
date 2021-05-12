요즘 DDPM이나 Score matching 같은 방법이 생성 모델의 미래로서 꽤 유망하다고 생각한다. DDPM을 adversarial robustness를 위한 data augmentation으로 사용해서 흥미로운 결과를 얻은 연구를 참고해도 좋겠다.
Fixing Data Augmentation to Improve Adversarial Robustness (Sylvestre-Alvise Rebuffi, Sven Gowal, Dan A. Calian, Florian Stimberg, Olivia Wiles, Timothy Mann)
https://arxiv.org/abs/2103.01946
augmentation을 model ema와 결합하면 robustness가 향상된다는 결과. 거기에 ddpm으로 생성한 이미지까지 투입해 성능을 대폭 향상시킴. cutmix-ema-ddpm이라는 뉴럴넷 업계의 빛3가 모여 만든 인상적인 결과.

아, 그리고 Score-Based Generative Modeling through Stochastic Differential Equations (https://arxiv.org/abs/2011.13456)의 jax 기반 구현이 공개되었다. https://github.com/yang-song/score_sde 한 번 보시는 것도 좋겠다.

[[210302 Fixing Data Augmentation to Improve Adversarial Robustness]]

#robustness #augmentation #generative_model #ddpm