https://arxiv.org/abs/2211.09794

Null-text Inversion for Editing Real Images using Guided Diffusion Models (Ron Mokady, Amir Hertz, Kfir Aberman, Yael Pritch, Daniel Cohen-Or)

text2img에서 ddim inversion을 위한 방법. stable diffusion처럼 classifier guidance가 큰 상황에서는 inversion된 코드에서 이미지를 생성하면 원 이미지와 크게 달라진다는 문제가 있네요. classifier guidance를 1 정도로 작게 설정한 다음 나온 latent trajectory를 생성한 다음 이 trajectory에 대해 classifier guidance를 크게 설정한 결과로 나온 trajectory가 가까워지도록 null text embedding ("")을 학습시키는 식으로 inversion을 합니다.

#ddpm #image_editing 