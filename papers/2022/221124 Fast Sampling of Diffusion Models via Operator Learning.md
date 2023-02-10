https://arxiv.org/abs/2211.13449

Fast Sampling of Diffusion Models via Operator Learning (Hongkai Zheng, Weili Nie, Arash Vahdat, Kamyar Azizzadenesheli, Anima Anandkumar)

initial condition인 noise input에 대해서 diffusion의 trajectory를 매핑하는 operator 함수를 학습하는 식으로 구성된 diffusion model이네요. 결과적으로 noise 입력에 대해 각 time step에서의 모든 출력을 예측하는 모델이 됩니다. 모델 구성에는 이 trajectory를 frequency domain에서 보면 low frequency에 집중되어 있다는 것에 착안해서 fft를 사용한 temporal convolution을 사용했습니다. sampling step 한 번으로 cifar-10에서 sota급 성능을 보이는데 성공했네요. 물론 문제는 더 큰 데이터셋들에 대한 결과겠지만요.

#ddpm 