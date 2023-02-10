https://arxiv.org/abs/2301.11093

simple diffusion: End-to-end diffusion for high resolution images (Emiel Hoogeboom, Jonathan Heek, Tim Salimans)

이쪽도 pixel level diffusion으로 high resolution 생성을 커버하는 시도군요. noise schedule를 64x64를 기준으로 snr을 유지하도록 잡는 방법 (이쪽이 좀 더 근본 있어 보이네요), high frequency detail에 대해 loss가 집중되는 것을 막기 위한 multiscale loss, 16x16 feature map을 집중적으로 scaling, dwt나 strided conv를 사용해서 입력을 바로 downsampling, low resolution feature map에만 dropout 적용 등을 결합했습니다. pixel 레벨로 생성하고 distillation을 사용해서 괜찮은 속도 (TPU에서 0.4초 정도)를 낼 수 있다는 제안이네요.

#ddpm 