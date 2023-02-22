# 201126 최근 논문들에 대한 생각 2

neural radiance field처럼 생성 모델(gan) 업계에서 인기있는 주제. latent code를 조작했을 때 다른 이미지 영역에는 영향을 미치지 않고 local하게 이미지를 편집할 수 있는 latent code 변형 방법 찾기, 혹은 그런 특성을 갖게 만들기.

CAFE-GAN: Arbitrary Face Attribute Editing with Complementary Attention Feature(https://arxiv.org/abs/2011.11900)

Style Intervention: How to Achieve Spatial Disentanglement with Style-based Generators? (https://arxiv.org/abs/2011.09699)

StyleSpace Analysis: Disentangled Controls for StyleGAN Image Generation (https://arxiv.org/abs/2011.12799)

내가 흥미롭다고 생각하는 접근들을 덧붙이자면,

A StyleMap-Based Generator for Real-Time Image Projection and Local Editing(https://openreview.net/forum?id=QcjTNc_afvH)

이쪽은 latent code에 spatial한 차원을 추가하는 방식으로 접근.

Learning Semantic-aware Normalization for Generative Adversarial Networks(https://proceedings.neurips.cc/.../f885a14eaf260d7d9f93c7...)

이쪽은 convolution kernel의 채널에 group 구조를 발견/부여하는 방향으로 접근.

한쪽은 spatial dimension이고 한쪽은 channel dimension이라 어떻게 보면 반대 방향이라고 할 수도 있겠는데...여튼 cnn의 구조 측면에서도 시사하는 바가 있는 흥미로운 결과라고 생각한다.

(Semantic-aware Normalization을 재현을 할 수 있었으면 좋겠는데...뭘 빠뜨렸는지 아직 못 하고 있다. 😕)

나머지 큰 유행은 contrastive learning과 detr이 떠오르는데...이것도 좀 모아볼 수 있을지도.



#review