https://arxiv.org/abs/2202.00512

Progressive Distillation for Fast Sampling of Diffusion Models (Tim Salimans, Jonathan Ho)

distillation으로 ddpm의 샘플링 스텝을 줄이기. student의 1 step 결과가 teacher의 2 step의 결과에 상응하도록 distillation을 해서 결과적으로 필요 스텝 수를 절반으로 줄여나가는 방식입니다. distillation으로 필요 스텝을 줄일 수 있다는 것, 반대로 scratch 학습에서는 그만큼 성능이 안 나온다는 것이 ddpm 학습 과정에서 autoregressive vs nonautoregressive model에서 나타나는 것과 같은 문제(multimodal 같은?)가 나타난다는 것을 의미하는 것은 아닌가 싶네요.

#ddpm #distillation 