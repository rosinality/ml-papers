이번 주의 논문
연말이기도 하고 해서 논문 목록을 보다가 올해 딥 러닝 업계의 큰 혁신에는 무엇이 있었나 하는 생각을 해봤다. 나라면 대략 아래 같은 주제들을 꼽을 것 같다. 대충 뽑은 것이긴 하지만.
implicit neural representation
generative model (denoising diffusion, score based model, vae)
augmentation for gan
detr
self supervision & semi supervision
efficient attention
robustness
lm & bertology
이런 주제들을 가지고 연말 기념 이벤트(?) 비슷한 것을 해보면 어떨까 하는 생각을 하고 있다. 위의 주제들에 대해서 개괄적으로 다뤄본다든지, 아니면 위 주제들에 대한 주요 논문 목록을 정리한다든지, 몇 논문을 뽑아서 리뷰를 한다든지, 필수...는 무슨 권위가 있지도 않은 입장에서 너무 강제적인 것 같으니 권장 리딩 리스트 같은 걸 만든다든지 등등. 그런데 생각해보면 어차피 다들 읽어본 논문일 텐데 그런 게 필요한가 싶기도 하다. 그냥 이런 주제들에 대한 쓸데 없는 소리나 좀 하는 게 나을지도.
어쨌든! 이번 주의 논문에는 위의 주제들이 많이 등장한다.
1. implicit neural representation/nerf
nerf(https://arxiv.org/abs/2003.08934)가 3월에 나왔을 때는 nerf의 위력을 알아채질 못했다. 오 결과물 좋네! cnn 없이 mlp만으로 태클했다고? 신기하네. 이런 정도. 그러나 이제와서 보면 nerf는 뉴럴 렌더링 업계의 완벽한 대세가 되었다고 해도 좋을 것 같다. 역시 좋은 연구를 놓치지 않고 알아보는 것이 중요하다. 깊이 생각을 해봐야 하는데...좀 너무 대충 생각했었던 것 같다. 😕
Image Generators with Conditionally-Independent Pixel Synthesis (Ivan Anokhin, Kirill Demochkin, Taras Khakhulin, Gleb Sterkin, Victor Lempitsky, Denis Korzhenkov)
https://arxiv.org/abs/2011.13775
https://arxiv.org/abs/2011.12026 과 아주 아주 비슷한 아이디어. weight modulation으로 latent와 mlp를 연결하고 fourier feature에서 image로 변환. 여기서는 각 coordinate에 learnable weight를 추가로 부여하고 multiscale 구조는 빠짐. stylegan2와 비슷하거나 경우에 따라서는 더 나은 성능.
pi-GAN: Periodic Implicit Generative Adversarial Networks for 3D-Aware Image Synthesis (Eric R. Chan, Marco Monteiro, Petr Kellnhofer, Jiajun Wu, Gordon Wetzstein)
https://arxiv.org/abs/2012.00926
이번에도 implicit representation으로 gan의 generator를 교체. 이쪽은 nerf에 더 가깝게 hologan처럼 3d 공간에서의 변환/카메라 위치 변환에 초점이 맞춰져 있음. 결과적으로는 GRAF(https://arxiv.org/abs/2007.02442)와 유사하긴 함. GIRAFFE(https://arxiv.org/abs/2011.12100)도 그렇고 neural rendering 업계의 확실한 대세.
D-NeRF: Neural Radiance Fields for Dynamic Scenes (Albert Pumarola, Enric Corona, Gerard Pons-Moll, Francesc Moreno-Noguer)
https://arxiv.org/abs/2011.13961
시간축에 대한 interpolation이 가능한 nerf. (https://www.albertpumarola.com/research/D-NeRF/index.html)
Neural Scene Flow Fields for Space-Time View Synthesis of Dynamic Scenes (Zhengqi Li, Simon Niklaus, Noah Snavely, Oliver Wang)
https://arxiv.org/abs/2011.13084
위와 마찬가지로 시간축을 통합한 nerf. xyz는 이제 노잼 아니냐? http://www.cs.cornell.edu/~zl548/NSFF
pixelNeRF: Neural Radiance Fields from One or Few Images (Alex Yu, Vickie Ye, Matthew Tancik, Angjoo Kanazawa)
https://arxiv.org/abs/2012.02190
few shot nerf. 역시 이미지 인코더를 달아서 해결하는 방식. many shot nerf 수준의 강렬한 결과는 아직 나오지는 않지만 앞으로는?
Learned Initializations for Optimizing Coordinate-Based Neural Representations (Matthew Tancik, Ben Mildenhall, Terrance Wang, Divi Schmidt, Pratul P. Srinivasan, Jonathan T. Barron, Ren Ng)
https://arxiv.org/abs/2012.02189
implicit/coordinate representation이 테스트 시점에 학습해야 하는 시간이 기니까 메타러닝(maml/reptile)로 좋은 초기값을 미리 부여하고 시작하겠다는 발상.
2. neural rendering
뉴럴 렌더링 업계에서 재미있는 혹은 인상적인 결과들 몇 개.
Full-Resolution Correspondence Learning for Image Translation (Xingran Zhou, Bo Zhang, Ting Zhang, Pan Zhang, Jianmin Bao, Dong Chen, Zhongfei Zhang, Fang Wen)
https://arxiv.org/abs/2012.02047
포즈 같은 조건(exemplar)이 주어진 상황에서의 img2img. 조건과 소스 이미지 사이의 correspondence를 patchmatch로 계산하는 것이 핵심. 다른 형태의 문제로도 확장이 가능한 아이디어일지도?
Animating Pictures with Eulerian Motion Fields (Aleksander Holynski, Brian Curless, Steven M. Seitz, Richard Szeliski)
https://arxiv.org/abs/2011.15128
이미지 한 장으로 이미지 내 유체의 흐름을 생성해내는 모델. https://eulerian.cs.washington.edu/
Unpaired Image-to-Image Translation via Latent Energy Transport (Yang Zhao, Changyou Chen)
https://arxiv.org/abs/2012.00649
오토인코더를 사용해서 두 도메인을 latent code로 매핑한 다음 이 두 도메인의 code를 매핑하는 ebm을 학습시켜 두 도메인을 매핑/image translation. 결과는 재미있는데 역시 이런 종류의 img2img는 결과가 잘 나온 건지 판단하는 것이 좀 애매.
3. gan, generative models
2020년에는 gan에서도 괄목할 진전이 있었고, gan 외의 generative model들에서도 엄청난 진전이 있었다. denoising diffusion, score matching, vae, 이번에는 ebm까지! generative model이 보통 그렇듯 수학적으로도 흥미롭다. 물론 sde 정도가 나오면 좋아하는 나같은 뉴비 수준에서.
Navigating the GAN Parameter Space for Semantic Image Editing (Anton Cherepkov, Andrey Voynov, Artem Babenko)
https://arxiv.org/abs/2011.13786
gan 이미지 편집 방법인데...기존의 방법들을 사용하지만 가장 큰 차이는 latent code가 아니라 generator의 파라미터를 변환한다는 것. 코 길이 바꾸기나 뱀파이어화 같은 변환을 generator의 파라미터 공간에서 찾아낼 수 있다는 게 좀 기묘함. https://github.com/yandex-research/navigan
Self-labeled Conditional GANs (Mehdi Noroozi)
https://arxiv.org/abs/2012.02162
레이블 없이 conditional gan 트레이닝. 결과적으로 클러스터링 모듈이 붙어서 같이 학습되는 방식인데...tunit (https://arxiv.org/abs/2006.06500) 아녀!?
Omni-GAN: On the Secrets of cGANs and Beyond (Peng Zhou, Lingxi Xie, Bingbing Ni, Qi Tian)
https://arxiv.org/abs/2011.13074
auxillary classifier, projection discriminator를 대체할 수 있는 새로운 conditional gan. class label과 adversarial loss를 더 직접적으로 연결했다는 느낌인데...
Refining Deep Generative Models via Wasserstein Gradient Flows (Abdul Fatir Ansari, Ming Liang Ang, Harold Soh)
https://arxiv.org/abs/2012.00780
한동안 나왔던 discriminator를 사용한 샘플 개선. f-divergence의 gradient flow를 생각한 다음 sde와 연결해서 discriminator를 끼워넣는 방식으로 유도. 꽤 상큼하니 한 번 보셔도.
How to train your conditional GAN: An approach using geometrically structured latent manifolds (Sameera Ramasinghe, Moshiur Farazi, Salman Khan, Nick Barnes, Stephen Gould)
https://arxiv.org/abs/2011.13055
conditional gan에서 diversity가 떨어지는(mode collapse) 이유. latent mainfold의 큰 영역들을 singular point로 매핑하기 때문. generator가 latent manifold와 generator의 output image manifold 사이의 homeomorphism이 되도록 학습 과정을 개선하려는 아이디어. 상당히 흥미로운 개선인 듯. 리만 기하 맛 좀 볼래?
Score-Based Generative Modeling through Stochastic Differential Equations (Yang Song, Jascha Sohl-Dickstein, Diederik P. Kingma, Abhishek Kumar, Stefano Ermon, Ben Poole)
https://arxiv.org/abs/2011.13456
openreview에 올라왔었던 denoising diffusion과 score based model을 sde를 사용해 통합한 연구. 저자들이 짱짱했었네.
Improved Contrastive Divergence Training of Energy Based Models (Yilun Du, Shuang Li, Joshua Tenenbaum, Igor Mordatch)
https://arxiv.org/abs/2012.01316
IGEBM(https://arxiv.org/abs/1903.08689) 저자들이 다시 출동! contrastive-divergence에서 간과되어왔던 term를 다시 살리고 샘플링 과정 개선 & 멀티스케일화. generative model 업계의 경쟁이 매우 격렬.
SplitNet: Divide and Co-training (Shuai Zhao, Liguang Zhou, Wenxiao Wang, Deng Cai, Tin Lun Lam, Yangsheng Xu)
https://arxiv.org/abs/2011.14660
모델 scaling에는 깊이, 폭, 입력 크기 말고 모델의 수도 포함시킬 수 있지 않은가 하는 아이디어. 작은 모델 여러 개를 같이 학습시키고 앙상블.
4. self supervised learning
이러니 저러니 해도 올해의 가장 큰 진전을 단 하나만 꼽으라면 역시 contrastive learning을 위시한 self supervision일 것이다. 데이터 문제를 데이터를 더 투입하는 것으로 해결하는 것 같은 느낌이라 좀 꽁기꽁기하긴 하지만 어쨌든 한동안, 혹은 생각보다 오랫동안 중요한 도구가 될 듯 하다. 연구자가 아니라 엔지니어의 입장에서도 도구상자에 하나 장착해야 하지 않을지?
How Well Do Self-Supervised Models Transfer? (Linus Ericsson, Henry Gouk, Timothy M. Hospedales)
https://arxiv.org/abs/2011.13377
self supervised 알고리즘의 각종 과제에 대한 transfer 성능 벤치마크. 과제 종류마다 좋은 알고리즘이 다르긴 한데...전반적으로는 byol이 대체로 괜찮은 듯.
Beyond Single Instance Multi-view Unsupervised Representation Learning (Xiangxiang Chu, Xiaohang Zhan, Xiaolin Wei)
https://arxiv.org/abs/2011.13356
self supervised learning에서 이미지 샘플을 (cutmix 같이) 믹스해서 믹스에 사용한 이미지 샘플들을 spurious positive pair로 사용.
Can Temporal Information Help with Contrastive Self-Supervised Learning? (Yutong Bai, Haoqi Fan, Ishan Misra, Ganesh Venkatesh, Yongyi Lu, Yuyin Zhou, Qihang Yu, Vikas Chandra, Alan Yuille)
https://arxiv.org/abs/2011.13046
영상에 대한 self supervised learning. 시간에 대한 augmentation만으로는 도움이 안 되고 이 augmentation에 대해 추가적인 과제를 붙여줘야 한다는 결론. (영상을 거꾸로 돌리고 있다는 것을 맞추게 한다든지.)
Self-EMD: Self-Supervised Object Detection without ImageNet (Songtao Liu, Zeming Li, Jian Sun)
https://arxiv.org/abs/2011.13677
detection에 적합한 self supervision n탄. byol 기반으로 global pooling을 빼버리고 feature map 사이의 earth mover's distance를 similarity로 사용한다는 것이 핵심.
Towards Good Practices in Self-supervised Representation Learning (Srikar Appalaraju, Yi Zhu, Yusheng Xie, István Fehérvári)
https://arxiv.org/abs/2012.00868
self supervision에서 중요한 선택들에 대한 분석. 사실상 MoCo v2에 대한 ablation 및 분석. deep image prior로 mlp의 효과를 분석한 것이 꽤 재미있음.
SelfText Beyond Polygon: Unconstrained Text Detection with Box Supervision and Dynamic Self-Training (Weijia Wu, Enze Xie, Ruimao Zhang, Wenhai Wang, Guan Pang, Zhen Li, Hong Zhou, Ping Luo)
https://arxiv.org/abs/2011.13307
비교적 저렴한 박스 레이블을 리파인해서 폴리곤 레이블의 효과를 내보려는 시도. 요즘 같은 pseudo label의 시대에는 충분히 가능한 방법인 것 같기도 하고.
Weakly-Supervised Arbitrary-Shaped Text Detection with Expectation-Maximization Algorithm (Mengbiao Zhao, Wei Feng, Fei Yin, Xu-Yao Zhang, Cheng-Lin Liu)
https://arxiv.org/abs/2012.00424
이쪽도 박스 레이블을 사용해서 성능을 개선하려는 시도. 결과도 재미있고...실험에 사용한 centernet (keypoint triplet 아님 ㅎ)과 deep snake를 붙인 모델도 흥미로운 듯.
Unsupervised part representation by Flow Capsules (Sara Sabour, Andrea Tagliasacchi, Soroosh Yazdani, Geoffrey E. Hinton, David J. Fleet)
https://arxiv.org/abs/2011.13920
캡슐 네트워크를 사용해 이미지에서 이미지 주요 구성 요소들을 분해하도록 학습. 영상에서의 움직임을 이 self supervision의 주요한 단서로 활용. 인간은 고정된 영상을 보는 경우가 사실상 없기 때문에 영상을 활용하는 것이 좋은 방향이 될 수 있다고 생각.
5. transformer & vision
사실 이미지에 처리에 attention을 결합한 것은 하루 이틀 일이 아니긴 한데 ViT(https://arxiv.org/abs/2010.11929) 이후로 좀 더 관심을 받고 있지 않은지. 아직까지는 아주 효율적이라는 생각은 들지 않지만 앞으로는 또 어떨지.
General Multi-label Image Classification with Transformers (Jack Lanchantin, Tianlu Wang, Vicente Ordonez, Yanjun Qi)
https://arxiv.org/abs/2011.14027
트랜스포머를 사용한 이미지 multilabel classification. masked label을 예측하도록 하는 방식. 레이블이 부분적으로 주어졌을 때 혹은 추가적인 레이블이 주어졌을 때 이 레이블 정보를 사용해서 출력 결과를 개선할 수 있는 것을 목표로 설정. 흥미로운 과제인 듯.
Pre-Trained Image Processing Transformer (Hanting Chen, Yunhe Wang, Tianyu Guo, Chang Xu, Yiping Deng, Zhenhua Liu, Siwei Ma, Chunjing Xu, Chao Xu, Wen Gao)
https://arxiv.org/abs/2012.00364
트랜스포머를 이미지 denoising, deraining, superresolution, contrastive learning으로 프리트레이닝한 다음 파인튜닝. 이건 대체...뭔가...뭔가 일어나고 있음.
Multimodal Pretraining Unmasked: Unifying the Vision and Language BERTs (Emanuele Bugliarello, Ryan Cotterell, Naoaki Okazaki, Desmond Elliott)
https://arxiv.org/abs/2011.15124
vision & language bert 모델들을 통합적인 프레임워크 하에서 비교. 모델들의 성능이 비슷비슷하다는 것, initialization에 따른 결과의 분산이 크다는 것, 임베딩 레이어를 어떻게 세팅하는가가 중요하다는 것을 발견.
6. nlp
nlp 업계 출신(?)이라고 자처하는데 nlp에 대해서 할 말이 별로 없다. 사실 self supervision으로 재작년 ~ 작년에 이미 대박을 터뜨려서 그런 것 같기도 하고.
Learning from others' mistakes: Avoiding dataset biases without modeling them (Victor Sanh, Thomas Wolf, Yonatan Belinkov, Alexander M. Rush)
https://arxiv.org/abs/2012.01300
데이터셋의 bias를 보완하는 방법. weak learner가 bias를 활용한다는 점을 이용해 weak learner을 학습시키고, 메인 모델에 weak learner를 연결해 product of experts로 학습시켜서 메인 모델이 weak learner의 문제를 보완하도록 만듦.
How Can We Know When Language Models Know? (Zhengbao Jiang, Jun Araki, Haibo Ding, Graham Neubig)
https://arxiv.org/abs/2012.00955
lm 기반 qa 모델에서 나오는 답을 신뢰할 수 있는가? 결국 캘리브레이션 문제가 됨. 논문에서 제안한 방법과 여러 기존 방법들을 사용해 캘리브레이션을 적용.
StructFormer: Joint Unsupervised Induction of Dependency and Constituency Structure from Masked Language Modeling (Yikang Shen, Yi Tay, Che Zheng, Dara Bahri, Donald Metzler, Aaron Courville)
https://arxiv.org/abs/2012.00857
constituency와 dependency 구조를 모두 추출하는 unsupervised parsing. 파서 모듈로 dependency 구조를 추출한 다음 self attention에 주입하고 mlm으로 학습.
Progressively Stacking 2.0: A Multi-stage Layerwise Training Method for BERT Training Speedup (Cheng Yang, Shengnan Wang, Chao Yang, Yuechuan Li, Ru He, Jingqiao Zhang)
https://arxiv.org/abs/2011.13635
bert 프리트레이닝 속도 개선. 레이어를 하나씩 쌓아가면서 새로 추가한 레이어만 학습시키는 방식. 학습 시간을 절반으로 줄임. electra 같은 모델과 결합할 수는 없을까 싶기도 하고.
7. detr & image recognition
또한 올해의 큰 혁신, detr을 위시한 image recognition 문제의 end2end 학습. 사실 object detection이라는 문제 자체에서는 아주 큰 메리트가 있나 하는 생각도 하지만, 복잡한 문제로 넘어가면 이 end2end 학습의 강점과 우아함이 더 잘 드러나는 듯 싶다. loss를 어떻게 부여할 것인가 자체가 어려운 문제들에 대해서 좋은, 그리고 생각 이상으로 일반적인 해법을 제공하고 있다. 학습 어렵고 무겁고 같은 문제들이 있지만 무서운 디텍션-퍼슨들이 출동해서 이미 진전을 보여주고 있기 때문에 곧 큰 문제가 아니게 될지도.
그렇지만 좀 전통적(?)인 업계에도 재미있는 결과들은 많이 나왔다. BlendMask(https://arxiv.org/abs/2001.00309), CondInst(https://arxiv.org/abs/2003.05664), SOLOv2(https://arxiv.org/abs/2003.10152), Axial-DeepLab(https://arxiv.org/abs/2003.07853), DetectoRS(https://arxiv.org/abs/2006.02334), Sibling Head(https://arxiv.org/abs/2003.07540), See-Saw Loss(https://arxiv.org/abs/2008.10032) 등등등. COCO mAP 50을 넘기는 것이 디텍터의 기본 소양이 된 해이기도 하지 않나 싶다.
MaX-DeepLab: End-to-End Panoptic Segmentation with Mask Transformers (Huiyu Wang, Yukun Zhu, Hartwig Adam, Alan Yuille, Liang-Chieh Chen)
https://arxiv.org/abs/2012.00759
앵커도 중심점도 nms도 merge 스텝도 박스도 없다! 마스크의 클래스 레이블과 dice loss로 마스크를 매칭해서 학습. argmax 두 번만으로 클래스 레이블과 마스크 id를 뽑아낼 수 있음.
End-to-End Video Instance Segmentation with Transformers (Yuqing Wang, Zhaoliang Xu, Xinlong Wang, Chunhua Shen, Baoshan Cheng, Hao Shen, Huaxia Xia)
https://arxiv.org/abs/2011.14503
detr식의 영상 instance segmentation. instance sequence를 매칭하는 방식으로 end2end 학습. 따라서 instance segmentation과 tracking을 end2end로 깨끗하게 통합. 여기까지 오니 detr의 장점이 더 잘 드러나는 듯.
Fully Convolutional Networks for Panoptic Segmentation (Yanwei Li, Hengshuang Zhao, Xiaojuan Qi, Liwei Wang, Zeming Li, Jian Sun, Jiaya Jia)
https://arxiv.org/abs/2012.00720
dynamic convolution 기반 panoptic segmentation. kernel generation이 instance segmentation의 대세.
Single-shot Path Integrated Panoptic Segmentation (Sukjun Hwang, Seoung Wug Oh, Seon Joo Kim)
https://arxiv.org/abs/2012.01632
이쪽도 dynamic conv를 사용한 panoptic segmentation. 어쩌다보니 업계가 (dynamic conv 같은) 좀 전통적인 접근과 detr를 위시한 신흥 end2end 접근으로 한 판 붙는 것 같은 느낌인데...앞으로 어느쪽이 더 힘을 받게 될지?
The Devil is in the Boundary: Exploiting Boundary Representation for Basis-based Instance Segmentation (Myungchul Kim, Sanghyun Woo, Dahun Kim, In So Kweon)
https://arxiv.org/abs/2011.13241
basis 기반 instance segmentation에 boundary에 해당하는 basis를 추가. mAP 1 정도의 효과.
Sparse R-CNN: End-to-End Object Detection with Learnable Proposals (Peize Sun, Rufeng Zhang, Yi Jiang, Tao Kong, Chenfeng Xu, Wei Zhan, Masayoshi Tomizuka, Lei Li, Zehuan Yuan, Changhu Wang, Ping Luo)
https://arxiv.org/abs/2011.12450
rpn으로 이미지별 proposal을 추출하는 게 아니라 데이터셋 전체에 대해서 고정된 proposal의 집합을 만들고 이 proposal을 학습시키는 방법. 고정관념에 대한 신박한 타파이긴 한데 정말 이래도 괜찮은가 싶기는 함.
Dynamic Feature Pyramid Networks for Object Detection (Mingjian Zhu, Kai Han, Changbin Yu, Yunhe Wang)
https://arxiv.org/abs/2012.00779
fpn 개선 1. 약간 https://arxiv.org/abs/2005.03101 같은 fpn에 대한 multiscale aggregation에 게이트를 달아서 추론 과정에서 연산을 건너뛸 수 있게 만든 것 같은 fpn. 디텍터는 영원히 튜닝 떡밥을 제공하는 듯.
Dual Refinement Feature Pyramid Networks for Object Detection (Jialiang Ma, Bin Chen)
https://arxiv.org/abs/2012.01733
fpn 개선 2. 이쪽은 offset을 사용한 deformation과 channel attention으로 low res-high res 결합을 개선해보겠다는 발상.
Parallel Residual Bi-Fusion Feature Pyramid Network for Accurate Single-Shot Object Detection (Ping-Yang Chen, Ming-Ching Chang, Jun-Wei Hsieh, Yong-Sheng Chen)
https://arxiv.org/abs/2012.01724
fpn 개선 3. 이쪽도 bifpn 구조에 대한 개선.
Class-agnostic Object Detection (Ayush Jaiswal, Yue Wu, Pradeep Natarajan, Premkumar Natarajan)
https://arxiv.org/abs/2011.14204
클래스 상관 없이 객체 검출만 해보자는 발상. 그러니까 학습셋에 없는 클래스의 객체들도 검출해내는 것이 중요한 문제가 됨. 일단 객체를 검출해내고 봐야 하는 경우가 많이 있을 테니 실용적인 문제가 아닐까 하는 생각.
8. 그 외
Truly shift-invariant convolutional neural networks (Anadi Chaman (1), Ivan Dokmanić (2) ((1) University of Illinois at Urbana-Champaign, (2) University of Basel))
https://arxiv.org/abs/2011.14214
shift consistency를 부여하기 위한 신박한 방법. circular padding과 같이 사용하면 100% consistency가 찍힘.
Batch Normalization with Enhanced Linear Transformation (Yuhui Xu, Lingxi Xie, Cihang Xie, Jieru Mei, Siyuan Qiao, Wei Shen, Hongkai Xiong, Alan Yuille)
https://arxiv.org/abs/2011.14150
batch norm의 affine transform을 depthwise conv로 대체. 1x 스케쥴에서 2 mAP 정도의 향상. latency는 생각보다는 크지 않은 것 같은데 실제로 어떨지.
Image Quality Assessment for Perceptual Image Restoration: A New Dataset, Benchmark and Metric (Jinjin Gu, Haoming Cai, Haoyu Chen, Xiaoxing Ye, Jimmy Ren, Chao Dong)
https://arxiv.org/abs/2011.15002
이미지 품질 평가 데이터셋. 기존의 여러 왜곡들 뿐만 아니라 gan 기반 모델들에서 발생하는 왜곡들도 포함시켰다는 것이 특징. 데이터셋 만드는 사람들에게는 늘 경의를.
FBWave: Efficient and Scalable Neural Vocoders for Streaming Text-To-Speech on the Edge (Bichen Wu, Qing He, Peizhao Zhang, Thilo Koehler, Kurt Keutzer, Peter Vajda)
https://arxiv.org/abs/2011.12985
nonautoregressive flow와 autoregressive flow를 붙인 형태의 vocoder. quantization하고 갤럭시 S8에 올렸더니 real-time factor 0.7 정도가 나왔다고.
Field of Junctions (Dor Verbin, Todd Zickler)
https://arxiv.org/abs/2011.13866
경계선 검출 알고리즘. 흥미로운데...오래걸림. (250x250px 이미지에 대해 V100에서 2분.)
Streaming end-to-end multi-talker speech recognition (Liang Lu, Naoyuki Kanda, Jinyu Li, Yifan Gong)
https://arxiv.org/abs/2011.13148
역시나 rnn-t 기반. efficient rnn-t 구현이 필요하다...!

#review