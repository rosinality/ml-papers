https://arxiv.org/abs/2106.05931

Score-based Generative Modeling in Latent Space (Arash Vahdat, Karsten Kreis, Jan Kautz)

vae에서 prior를 가우시안 분포와 latent space 사이를 매핑하는 diffusion process를 사용해 모델링. 이전에 flow를 활용해 나왔던 비슷한 작업들이 생각나네요. latent space 위에서 동작하면 샘플링 과정의 iteration이 줄어드는 것도 기대할 수 있고 무엇보다 diffusion model의 한계인 discrete space에서 작동하지 못한다는 문제를 우아하게 해결할 가능성이 생기겠죠.

#ddpm