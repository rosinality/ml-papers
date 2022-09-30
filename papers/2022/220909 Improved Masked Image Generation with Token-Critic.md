https://arxiv.org/abs/2209.04439

Improved Masked Image Generation with Token-Critic (José Lezama, Huiwen Chang, Lu Jiang, Irfan Essa)

masked image generation에서 mask를 model prediction score를 사용해서 샘플링하는 것이 아니라 masked image에 대한 model prediction과 unmasked patch를 구분하는 모델(token-critic)의 예측 결과로 샘플링하는 방법. 더 적은 iteration으로 더 나은 샘플을 생성할 수 있습니다.

#mlm #non-autoregressive 