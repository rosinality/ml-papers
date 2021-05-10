https://arxiv.org/abs/2002.03754

Unsupervised Discovery of Interpretable Directions in the GAN Latent
  Space (Andrey Voynov, Artem Babenko)

GAN에서 noise input을 의미 있게 이동시키는 방향을 찾아내는 방법. generator에 noise 1과 noise 1 + A * eps, 즉 이동된 노이즈를 입력으로 주어 생성한 이미지를 reconstructor에 입력해 이동 행렬과 eps를 예측하게 하는 방법. A 또한 학습되므로 구분하기 용이한 방향의 이동이 학습될 것이라고 가정할 수 있음.

#gan #semantic_factor 