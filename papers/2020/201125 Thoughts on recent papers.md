요즘 재미있는 논문이 많아서 좀 유쾌하다.
아래 논문들은 (많이) 흥미롭거나 꼭 체크해볼 가치가 있다고 생각하는 논문들.
Very Deep VAEs Generalize Autoregressive Models and Can Outperform Them on Images
https://arxiv.org/abs/2011.10650
얼마 전 나왔던 very deep vaes의 arxiv 버전. openai의 단독 저자였다니 좀 신기. 코드에 쓰인 트릭들이 의미가 있어서 체크해볼만 함.
Dual Contradistinctive Generative Autoencoder
https://arxiv.org/abs/2011.10063
모델 구조 변화 없이 vae의 퀄리티 개선. 이미지셋에 속하는 이미지인지를 구분하는 adversarial loss에 reconstruction loss를 사용. reconstruction loss를 exact match가 아니라 다른 이미지들에 비해서 더 비슷한가를 묻는 loss로 완화시켜준 것이 핵심적이라고 할 수 있을 듯.
Run Away From your Teacher: Understanding BYOL by a Novel Self-Supervised Approach
https://arxiv.org/abs/2011.10944
batch norm 덕분이라는 설명이 날아가고 나온 byol이 되는 이유 분석 2탄. view 사이의 consistency와 mean teacher로부터 멀어지는 loss로 결합된 직관적으로 이해가 가는 framework (raft)를 만들고, byol이 특정 조건 하에서 이 프레임워크와 동등하다는 것을 보임.
Adversarial Generation of Continuous Images
https://arxiv.org/abs/2011.12026
coordinate -> rgb mlp와 latent code를 입력으로 받는 hypernetwork를 연결시킨 형태의 generator. 아주 흥미로움!
아래 논문들은 흥미로운 실험 및 튜닝이 메인인 결과들.
Rethinking Transformer-based Set Prediction for Object Detection
https://arxiv.org/abs/2011.10881
다들 detr 학습 속도 개선에 관심이 많은 듯. 이 논문에선 fcos/rpn으로 proposal을 뽑은 다음에 트랜스포머 인코더를 붙이고 set prediction을 하는 식으로 접근했는데...이건 좀 second stage에 트랜스포머를 붙인 쪽에 가깝지 않나요?
An Effective Anti-Aliasing Approach for Residual Networks
https://arxiv.org/abs/2011.10675
antialiasing을 위한 blur를 온갖 방법으로 사용해서 테스트. blur는 image classification에서는 성능 확실한데 다른 과제에 대해서는 모델에 따라 특성이 달라지는 감이 있어서...여러모로 개선을 시도해볼 가치가 있는 방향이라고 생각.
MicroNet: Towards Image Recognition with Extremely Low FLOPs
https://arxiv.org/abs/2011.12289
경량 백본. factorize된 convolution과 새로운 activation 사용.
Scaling Wide Residual Networks for Panoptic Segmentation
https://arxiv.org/abs/2011.11675
wide resnet을 scaling해서 panoptic segmentation에 적용. (제목이 정확하게 내용을 요약...) axial deeplab 저자들이 resnet으로 이렇게 놀고 있는 걸 보니 좀 재미있음.
아래 논문들은 흥미로운 문제 및 과제에 대한 결과들.
Ranking Neural Checkpoints
https://arxiv.org/abs/2011.11200
여러 모델/체크포인트가 transfer 상황에서 어떤 성능을 보이는지 파인튜닝 없이 ranking을 매길 수 있는 metric를 만들고 체크포인트들을 테스트.
Stable Weight Decay Regularization
https://arxiv.org/abs/2011.11152
weight decay rate가 decoupled weight decay에서도 일정하지 않다는 문제 의식에서 개선 방법을 제안. adamw는 결과적으로 광범위하게 채택되고 있는데 이쪽은 어떨지.
Is a Green Screen Really Necessary for Real-Time Human Matting?
https://arxiv.org/abs/2011.11961
human image matting 과제. 이런 모델들이 실제로 누끼를 얼마나 잘 따는지 궁금.
Boosting Contrastive Self-Supervised Learning with False Negative Cancellation
https://arxiv.org/abs/2011.11765
contrastive learning에서 false negative를 찾아서 지우기. 결과적으로는 false negative를 어떻게 찾아내는가가 문제인데...휴리스틱이 팡팡 들어갈 수밖에 없는 문제이기는 함.
Dissecting Image Crops
https://arxiv.org/abs/2011.11831
주어진 이미지가 원 이미지의 어떤 영역에서 크롭된 것인지를 탐지하는 모델. 생각해보지도 못한 과제라서 재미있음.
HistoGAN: Controlling Colors of GAN-Generated and Real Images via Color Histograms
https://arxiv.org/abs/2011.11731
히스토그램을 입력으로 받아 색조를 조정할 수 있는 generator 만들기.
Cross-Camera Convolutional Color Constancy
https://arxiv.org/abs/2011.11890
학습때 사용하지 않은 카메라에서 대해서도 color constancy/white balance를 맞춰줄 수 있는 모델.
Energy-Based Models for Continual Learning
https://arxiv.org/abs/2011.12216
energy based model이 그 구조상 softmax 기반 분류보다 continual learning에 적합하다는 연구. https://arxiv.org/abs/1912.03263 이후 최근의 https://arxiv.org/abs/2010.03759 에 이 연구까지 energy based model이라는 관점에서의 해석이 인기가 있음. ebm 붐은 온다!

#review