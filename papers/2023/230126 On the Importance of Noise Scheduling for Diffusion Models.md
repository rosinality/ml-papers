https://arxiv.org/abs/2301.10972

On the Importance of Noise Scheduling for Diffusion Models (Ting Chen)

이미지 크기에 따라 optimal한 noise schedule이 다른 것을 고려하기 위한 방법. noise schedule은 1 - t 같은 schedule로 고정한 다음 input pixel value에 대해 적절한 scaling factor를 잡는 방법을 사용했군요. sr 1 stage 모델로 1024px 이미지 생성에 성공했군요.

#ddpm 