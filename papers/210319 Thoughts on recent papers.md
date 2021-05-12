요즘 논문 정리를 잘 안 하는데...이번 주는 흥미로운 결과들이 꽤 있어서 공유하고 싶어졌음.
Involution: Inverting the Inherence of Convolution for Visual Recognition (https://arxiv.org/abs/2103.06255)
We additionally demystify the recent popular self-attention operator and subsume it into our involution family as an over-complicated instantiation. 앱스트랙이 아주 공격적.
Revisiting ResNets: Improved Training and Scaling Strategies (https://arxiv.org/abs/2103.07579)
resnet 약간 트윅하고 supervised pretraining으로 학습을 잘 시켜주니까 괜찮은데? 라는 결론. mixup/cutmix는 안 썼는데 이유는 궁금.
You Only Look One-level Feature (https://arxiv.org/abs/2103.09460)
디텍션에서 fpn을 없애고 stride 32 feature만 쓰기. 영감은 detr에서 받은 것 같음.
Training GANs with Stronger Augmentations via Contrastive Discriminator (https://arxiv.org/abs/2103.09742)
discriminator의 feature representation을 contrastive learning만으로 학습시켜버리기. 원래 gan training이 unsupervised training의 방법이기도 했는데 이젠 unsupervised training이 gan training을 대체해버린 형국.
Learning to Resize Images for Computer Vision Tasks (https://arxiv.org/abs/2103.09950)
resizing을 해주는 네트워크를 만들어 붙여서 성능을 향상시킨 시도인데...향상폭도 좀 있는 것 같음.
GPT Understands, Too (https://arxiv.org/abs/2103.10385)
프롬프트 입력 개선으로 gpt 파인튜닝 개선하기. 벤치마크에 따라 bert 수준의 결과도 나온다고 보고했는데 흥미로움.
FastNeRF: High-Fidelity Neural Rendering at 200FPS (https://arxiv.org/abs/2103.10380)
nerf는 이제 200 fps를 찍습니다.
All NLP Tasks Are Generation Tasks: A General Pretraining Framework (https://arxiv.org/abs/2103.10360)
span 기반 generative pretraining으로 nlu 모델 성능 끌어올리기. 위의 gpt 파인튜닝과 묘한 조화.
TrivialAugment: Tuning-free Yet State-of-the-Art Data Augmentation (https://arxiv.org/abs/2103.10158)
randaugment의 뒤를 잇는 심플한 augmentation 파이프라인. 수치는 좀 미묘해보이지만 autoaugment/randaugment가 트레이닝 파이프라인의 중요한 레시피라는 것을 생각해보면 의미가 있을 듯.
Using latent space regression to analyze and leverage compositionality in GANs (https://arxiv.org/abs/2103.10426)
masked reconstruction 모델에 gan을 합쳐서 image prior를 만듦. 사진 조각들을 콜라주한 다음에 generator로 consistent한 이미지를 생성하는데 흥미로움.

#review