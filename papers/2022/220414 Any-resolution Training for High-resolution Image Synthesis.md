https://arxiv.org/abs/2204.07156

Any-resolution Training for High-resolution Image Synthesis (Lucy Chai, Michael Gharbi, Eli Shechtman, Phillip Isola, Richard Zhang)

다양한 resolution의 이미지를 gan 학습에 쓸 수 있다는 아이디어. 낮은 resolution의 이미지로는 full size 이미지에 대해 학습시키고 높은 resolution의 이미지는 패치를 잘라다 학습시키는 방식을 사용했습니다. [0, 1] x [0, 1]의 continuous domain에 대해 generator가 정의되어 있고 stylegan3의 antialiasing 때문에 가능한 결과지 싶네요.

#gan