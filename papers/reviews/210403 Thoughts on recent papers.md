# 210403 최근 논문들에 대한 생각

vision transformer 개선

이제 제목만 봐도 느낌이 오시죠?

CvT: Introducing Convolutions to Vision Transformers (https://arxiv.org/abs/2103.15808)

Multi-Scale Vision Longformer: A New Vision Transformer for High-Resolution Image Encoding (https://arxiv.org/abs/2103.15358)

CrossViT: Cross-Attention Multi-Scale Vision Transformer for Image Classification (https://arxiv.org/abs/2103.14899)

Going deeper with Image Transformers (https://arxiv.org/abs/2103.17239)

깊은 비전 트랜스포머. 0에 가까운 채널별 scale을 달아줘서 초기에 identity처럼 거동하게 만드는 것과 classification 토큰을 네트워크 후반에 추가하는 개선. 이미지넷 86.3%

nerf 개선

MVSNeRF: Fast Generalizable Radiance Field Reconstruction from Multi-View Stereo (https://arxiv.org/abs/2103.15595)

매 scene마다 학습시켜야 한다는 제약 풀기. ibrnet의 후속이 벌써 등장.

GNeRF: GAN-based Neural Radiance Field without Posed Camera (https://arxiv.org/abs/2103.15606)

정확한 카메라 포즈에 대한 제약 풀기

NeMI: Unifying Neural Radiance Fields with Multiplane Images for Novel View Synthesis (https://arxiv.org/abs/2103.14910)

사실 nerf 관련 논문은 이제 너무 많다. 내가 3d에 대한 전문성도 없어서 좀 더 힘들기도 하고. nerf 관련 논문만 파도 버거울 지경. 물론 그래야할 필요가 있는 것은 아니지만.

트랜스포머로 트래킹하기

트래킹 알못인데 트랜스포머로 트래킹을 하는 논문들이 쭈루룩 나온 게 신기해서 모아봤다.

Transformer Tracking (https://arxiv.org/abs/2103.15436)

TransCenter: Transformers with Dense Queries for Multiple-Object Tracking (https://arxiv.org/abs/2103.15145)

Looking Beyond Two Frames: End-to-End Multi-Object Tracking Using Spatial and Temporal Transformers (https://arxiv.org/abs/2103.14829)

Spatial-Temporal Graph Transformer for Multiple Object Tracking (https://arxiv.org/abs/2104.00194)

Learning Spatio-Temporal Transformer for Visual Tracking (https://arxiv.org/abs/2103.17154)

그 외 트랜스포머로 뭔가 해보기

TFPose: Direct Human Pose Estimation with Transformers (https://arxiv.org/abs/2103.15320)

HiT: Hierarchical Transformer with Momentum Contrast for Video-Text Retrieval (https://arxiv.org/abs/2103.15049)

ViViT: A Video Vision Transformer (https://arxiv.org/abs/2103.15691)

생성모델

Drop the GAN: In Defense of Patches Nearest Neighbors as Single Image Generative Models (https://arxiv.org/abs/2103.15545)

패치 기반 방법으로 single image generation. singan 어쩌지.

Few-shot Semantic Image Synthesis Using StyleGAN Prior (https://arxiv.org/abs/2103.14877)

Labels4Free: Unsupervised Segmentation using StyleGAN (https://arxiv.org/abs/2103.14968)

Dual Contrastive Loss and Attention for GANs (https://arxiv.org/abs/2103.16748)

contrastive loss로 gan loss를 구성하고 self attention과 real vs real/fake 이미지 사이의 attention을 첨가해 stylegan2를 개선.

StyleCLIP: Text-Driven Manipulation of StyleGAN Imagery (https://arxiv.org/abs/2103.17249)

요즘 자주 나오는 stylegan과 clip의 결합. clip은 이제 텍스트와 이미지를 이어주는 과제들에 대한 중요한 백본.

그 외

AlignMix: Improving representation by interpolating aligned features (https://arxiv.org/abs/2103.15375)

autoencoding으로 mix하기. resnet-50으로 81.17이 나온 건 흥미롭긴 하네요.



#review