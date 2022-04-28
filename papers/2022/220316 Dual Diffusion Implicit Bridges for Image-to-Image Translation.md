https://arxiv.org/abs/2203.08382

Dual Diffusion Implicit Bridges for Image-to-Image Translation (Xuan Su, Jiaming Song, Chenlin Meng, Stefano Ermon)

(원칙적으로는 독립적인) ddpm으로 source 이미지를 latent로 매핑한 다음에 latent에서 target으로 다시 매핑하는 식으로 img2img translation. source -> latent, latent -> target 사이의 optimal transport라는 설명이 있긴 한데 이게 왜 되는 건지는 여전히 의문스럽네요. 물론 이미지넷 같은 경우에는 class condition을 준 단일 모델이라서 가능한 부분이 있을 것 같긴 합니다.

#ddpm