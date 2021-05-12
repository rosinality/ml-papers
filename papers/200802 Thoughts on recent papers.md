이번 주 분량. 이번에는 좀 간단하게.
https://arxiv.org/abs/2007.12684
MiCo: Mixup Co-Training for Semi-Supervised Domain Adaptation (Luyu Yang, Yan Wang, Mingfei Gao, Abhinav Shrivastava, Kilian Q. Weinberger, Wei-Lun Chao, Ser-Nam Lim)
semi supervised domain adaptation. semi supervised learning을 하는 모델과 unsupervised domain adaptation을 하는 모델을 두고 pseudo label을 만드는 과정에서 두 모델이 생성한 레이블을 서로 다른 모델에게 전달함. pseudo labeling이 약간 묘기의 영역(저글링?)으로 가는 듯. 
https://arxiv.org/abs/2007.12568
The Surprising Effectiveness of Linear Unsupervised Image-to-Image Translation (Eitan Richardson, Yair Weiss)
unsupervised img2img 모델들이 local한 구조에 민감하고 반대로 global한 구조를 반영하는 것에는 약점이 있음. 대안으로 이미지 영역 전체를 입력으로 받는 linear map을 pca를 사용해 학습시킴. 이 자체로는 변환에 한계가 있지만 다른 모델에 대한 가이드로 활용할 수 있을지도. 
https://arxiv.org/abs/2007.14062
Big Bird: Transformers for Longer Sequences (Manzil Zaheer, Guru Guruganesh, Avinava Dubey, Joshua Ainslie, Chris Alberti, Santiago Ontanon, Philip Pham, Anirudh Ravula, Qifan Wang, Li Yang, Amr Ahmed)
long range attention을 위한 sparse attention. longformer와 같은 local, global attention에 random attention이 추가된 형태. (와츠-스트로가츠 랜덤 그래프?) 사실 long range attention을 적절히 활용하도록 학습할 수 있다는 것도 좀 신기한 일이라고 생각. 
https://arxiv.org/abs/2007.13816
Corner Proposal Network for Anchor-free, Two-stage Object Detection (Kaiwen Duan, Lingxi Xie, Honggang Qi, Song Bai, Qingming Huang, Qi Tian)
anchor보다 anchor free 방법이, regression보다 키포인트가 recall이 높지만 precision은 낮다. 그래서 2 stage 방법을 도입해 proposal을 걸러버리는 방법. CenterNet (KeyPoint Triplet) 저자. 그런데 이 저자도 CenterNet (Objects as Points)과 구분하는 마땅한 방법을 찾지 못한 듯. 
https://arxiv.org/abs/2007.14966
Mirostat: A Perplexity-Controlled Neural Text Decoding Algorithm (Sourya Basu, Govardana Sachitanandam Ramachandran, Nitish Shirish Keskar, Lav R. Varshney)
lm에 대한 top-k/top-p sampling과 perplexity의 관계, perplexity와 repetition 문제의 관계를 실험. 그리고 길이와 관계 없이 주어진 perplexity 조건에 맞춰 샘플링할 수 있는 알고리즘을 제안. 
https://arxiv.org/abs/2007.15255
Instance Selection for GANs (Terrance DeVries, Michal Drozdzal, Graham W. Taylor)
확률이 낮은 영역의 데이터를 gan으로 모델링하기 어렵고 이에 따라 퍼포먼스가 낮아지니, 이미지 임베딩을 뽑고 여기서 밀도가 높은 영역의 샘플만 골라 쓰자는 아이디어. 정확히 하기 어려운 부분은 안 하는 것이 나을 수 있다는 교훈. 
https://arxiv.org/abs/2007.15256
VocGAN: A High-Fidelity Real-time Vocoder with a Hierarchically-nested Adversarial Network (Jinhyeok Yang, Junmo Lee, Youngik Kim, Hoonyoung Cho, Injung Kim)
gan vocoder. generator를 멀티스케일로 바꾸고 loss를 튜닝해서 성능 향상. 상당히 의미있는 수준의 결과가 나온 듯. gan vocoder가 대세가 되지 않을지. 
https://arxiv.org/abs/2007.15188
Developing RNN-T Models Surpassing High-Performance Hybrid Models with Customization Capability (Jinyu Li, Rui Zhao, Zhong Meng, Yanqing Liu, Wenning Wei, Sarangarajan Parthasarathy, Vadim Mazalov, Zhenghao Wang, Lei He, Sheng Zhao, Yifan Gong)
rnn-t를 튜닝하던 사람들이 다시 한 번 더 튜닝. asr 연구자들의 영원한 친구 ctc & rnn-t를 둘 다 개발한 새삼 Graves가 대단하게 느껴지는 것...이 저자들이 쓰는 메모리 효율적인 rnn-t 구현은 좀 갖고 싶음. 
https://arxiv.org/abs/2007.15068
Unselfie: Translating Selfies to Neutral-pose Portraits in the Wild (Liqian Ma, Zhe Lin, Connelly Barnes, Alexei A. Efros, Jingwan Lu)
셀피의 포즈를 일반적인 포즈로 바꿔주는 모델. 포즈를 뽑고 가장 가까운 포즈를 찾은 다음 포즈의 좌표를 활용해 인페인팅하는 방법. 과제가 재미있음. 
https://arxiv.org/abs/2007.15646
Rewriting a Deep Generative Model (David Bau, Steven Liu, Tongzhou Wang, Jun-Yan Zhu, Antonio Torralba)
gan 모델을 수정해 모델이 보이는 패턴이나 규칙을 바꾸기. 원하는 형태의 feature를 지정하고 그 feature에 부합하도록 네트워크의 weight를 최적화하는 방법. 이제 lsun에서 shutterstock 워터마크를 지울 수 있다! 
LevelSet R-CNN: A Deep Variational Method for Instance Segmentation (Namdar Homayounfar, Yuwen Xiong, Justin Liang, Wei-Chiu Ma, Raquel Urtasun)
Mumford-Sha (https://arxiv.org/abs/2007.11576) 에 이어 Chan-Vese가 instance segmentation에 등장! 이 경우에는 오브젝트의 안과 밖에 서로 다른 값을 부여하는 문제가 됨. 이렇게 보면 object vs non object 분류 문제처럼 보이지만 몇 가지 요소가 추가됨. 
Contrastive Learning for Unpaired Image-to-Image Translation (Taesung Park, Alexei A. Efros, Richard Zhang, Jun-Yan Zhu)
contrastive learning을 활용한 unsupervised img2img. 핵심 아이디어는 입력 이미지의 패치를 잘라내서 그 패치에 해당하는 출력 이미지의 패치는 positive로 두고 나머지는 negative로 활용하는 것. 패치를 활용할 수 있다는 게 이렇게 유용. 

#review