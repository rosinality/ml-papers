# 200717 최근 논문들에 대한 생각

이번 주 분량.

https://arxiv.org/abs/2007.05471

Geometric Style Transfer (Xiao-Chang Liu, Xuan-Yi Li, Ming-Ming Cheng, Peter Hall)

기하학적 변형을 결합한 style transfer. 랜덤하게 기하학적으로 변형한 이미지에 style transfer를 수행해 style의 texture가 반영된 동시에 기하학적 변형(affine/tps)의 파라미터 또한 알고 있는 이미지 데이터셋을 구축하는 것이 핵심.

사실 artistic 스타일에는 텍스처 뿐만 아니라 기하학적인 특징들도 포함된다고 봐야하기 때문에 자연스러운 발전 방향일지도 모르겠다. 얼마 전 나온 Deformable Style Transfer(https://arxiv.org/abs/2003.11038)에서는 키포인트를 사용했는데 더 진전된 접근이라고 할 수 있을지도.

https://arxiv.org/abs/2007.05181

Sample-based Regularization: A Transfer Learning Strategy Toward Better Generalization (Yunho Jeon, Yongseok Choi, Jaesun Park, Subin Yi, Dongyeon Cho, Jiwon Kim)

트랜스퍼 러닝 상황에서 원 모델과 파인튜닝된 모델 사이의 차이에 대한 regularizer를 사용하는 대신 같은 클래스의 파인튜닝 샘플에 대한 파인튜닝된 모델의 차이를 감소시키는 regularizer를 적용. 바로 생각나는 건 라플라시안 regularization? (https://arxiv.org/abs/2006.15486)

요즘 레이블 사이의 관계를 사용하는 semi-supervised learning 혹은 fewshot 계통 방법이 많이 나오고 있다. 사실 이게 기존의 semi-supervised learning에서 이미 확립된 방법이었다는 것을 생각하면 이런 방법에서 시작하는 것이 맞는 순서일 수도 있다. (좀 덜 재미있게 여겨져서 그렇지.)

https://arxiv.org/abs/2007.05290

Learn to Use Future Information in Simultaneous Translation (Xueqing Wu, Yingce Xia, Lijun Wu, Shufang Xie, Weiqing Liu, Jiang Bian, Tao Qin, Tie-Yan Liu)

simultaneous translation, 즉 문장이 진행됨과 동시에 번역하는 모델에 대한 연구. 문장의 미래 k개 토큰을 활용하는데 학습 과정에서 사용할 k를 결정하는 모델을 reinforce로 학습. 그런데 랜덤하게 k를 부여하는 베이스라인도 괜찮은 듯.

말 그대로 말하는 것과 동시에 번역하는 모형. 사실 이 과제에 대해서는 몰랐는데 재미있는 것 같다. streaming asr 같은 것이 떠오르는데 어순 문제 때문에 훨씬 어려운 과제일 듯.

https://arxiv.org/abs/2007.06191

PSConv: Squeezing Feature Pyramid into One Compact Poly-Scale Convolutional Layer (Duo Li, Anbang Yao, Qifeng Chen)

각 채널의 커널마다 dilation을 다르게 주는 멀티스케일 컨볼루션. 멀티스케일 구조를 컨볼루션 블럭에 도입하는 것이 유용하다는 것은 지속적으로 증명되고 있음. 구현의 속도가 문제인데 저자들이 일반적인 컨볼루션의 1.4배 정도로 최적화하는데 성공한 듯. 

(다만 근시일에 공개되지는 않을 것으로...https://github.com/d-li14/PSConv/issues/2)

사실 컨볼루션을 여러 개 쌓으면 그것 자체가 멀티스케일이라고 볼 수 있을 테니 멀티스케일 구조라는 것이 약간 어폐가 있는지도 모르겠다. 그래서인지 실제로 3x3 컨볼루션의 캐퍼시티를 올려주며 멀티스케일 구조의 효과가 좀 줄어드는 것 같이 보이기도 한다. 어쨌든 ELASTIC(https://arxiv.org/abs/1812.05262), Octave Conv(https://arxiv.org/abs/1904.05049), MixConv(https://arxiv.org/abs/1907.09595), VoVNet(https://arxiv.org/abs/1904.09730), bLNet(https://arxiv.org/abs/1807.03848), Res2Net(https://arxiv.org/abs/1904.01169) 모두 이러한 멀티스케일 구조를 통해 백본을 강화해서 흥미롭고 실제 과제에도 유용한 구조를 설계하는데 성공했다.

프레임워크가 지원하는 오퍼레이션들로 구현이 가능하긴 하지만 역시 이런 구조들은 직접 커널을 만들어서 최대한의 효율을 뽑아낼 필요가 있긴 하다. 그 부분이 좀 아쉽긴 한데 다만 TVM 같은 도구로 괜찮게 구현하는 것이 가능하지 않을까. 요즘 TVM을 보고 있어서 하는 소리.

https://arxiv.org/abs/2007.05549

Meta-Learning Requires Meta-Augmentation (Janarthanan Rajendran, Alex Irpan, Eric Jang)

메타러닝 상황에서의 오버피팅을 막기 위한 augmentation. 일반적인 augmentation과는 달리 같은 과제에 대한 다양한 샘플이 아니라 같은 샘플에 대한 다양한 과제를 만들어주는 것이 목적. 다만 결과적으로 도출한 세팅이 mini imagenet에서 기본적으로 채택하는 세팅인 듯.

https://arxiv.org/abs/2007.07867

Transformation Consistency Regularization- A Semi-Supervised Paradigm for Image-to-Image Translation (Aamir Mustafa, Rafal K. Mantiuk)

요즘 generation 업계에 augmentation이 도입되고 있는데...이쪽은 img2img에 consistency regularization을 달아서 semi supervision을 하는 작업.



augmentation! augmentation이 답이다! 딥 러닝 판에서 발견한 가장 성공적인 전략이라고 할 수 있을지도 모르겠다. augmentation을 쓰지 않고 있는 문제가 있다면 그 문제에 대해 augmentation을 적용하는 작업 자체가 이제 중요해졌다.

https://arxiv.org/abs/2007.05667

To filter prune, or to layer prune, that is the question (Sara Elkerdawy, Mostafa Elhoushi, Abhineet Singh, Hong Zhang, Nilanjan Ray)

채널 프루닝 대신 레이어 프루닝! 채널을 깎는 게 아니라 레이어를 깎는 것이 더 단순하고 성능 감소를 줄이면서 레이턴시를 줄일 수 있는 방향이라는 제안.

https://arxiv.org/abs/2007.06181

Learning to Learn Parameterized Classification Networks for Scalable Input Images (Duo Li, Anbang Yao, Qifeng Chen)

여러 스케일의 이미지 입력에 대해 동작하는 분류 모델 만들기. 컨볼루션의 weight 전부(!)를 생성하는 fc 레이어를 도입하고 스케일마다 bn을 따로 관리. multiscale training과의 비교가 궁금하긴 함.

컨볼루션 weight를 전부 생성한다는 게 좀 충격적이었는데 fc 레이어의 입력 차원이 1이라 어떻게 가능한 것 같긴 하다.

https://arxiv.org/abs/2007.06162

Do You Have the Right Scissors? Tailoring Pre-trained Language Models via Monte-Carlo Methods (Ning Miao, Yuxuan Song, Hao Zhou, Lei Li)

lm을 파인튜닝하면 데이터셋이 제한적이기 때문에 분포 추정에 왜곡이 있음. 이에 대해 모델 분포와 실제 분포의 비율을 추정하고 샘플링 과정에 사용. 샘플링을 효율적으로 만들기 위해 시퀀스의 prefix에 대해 계산이 가능하도록 설계. 요즘 생성 과제에 많이 쓰이는 필터링의 개량?

autoregressive 모델은 현재 가장 성공적인 생성 모형이긴 하지만 아직 autoregressive 모델에서 어떻게 샘플링하는 것이 가장 효과적인지에 대해서는 풀어야 할 문제가 많은 것 같다. 특히 단어 분포처럼 카테고리의 수가 많고 롱테일인 분포에 대해서는 문제가 더 커지는 듯.

https://arxiv.org/abs/2007.06059

It Is Likely That Your Loss Should be a Likelihood (Mark Hamilton, Evan Shelhamer, William T. Freeman)

종종 나오는 역시 분포의 모든 파라미터(normal likelihood의 분산 파라미터 같은)를 최적화하는 것이 좋지 않을까!? 하는 아이디어. 저자들이 제안하는 장점은 robustness와 calibration. 최근 사례로 기억나는 건...gaussian yolo? https://arxiv.org/abs/1904.04620 

https://arxiv.org/abs/2007.06778

An Empirical Study on Robustness to Spurious Correlations using Pre-trained Language Models (Lifu Tu, Garima Lalwani, Spandana Gella, He He)

nlp 프리트레이닝의 효과가 무엇인가? 데이터셋에 없는 패턴으로 외삽을 가능하게 한다기보다는 데이터셋 내의 드물게 나타나는 패턴을 더 잘 활용하기 때문이라는 제안. 그리고 역시 더 큰 모델! 더 많은 데이터! 더 강력한 계산능력! 이 더 나은 특성을 보여줌.

중요한 문제이긴 한데 엄밀하고 정확하게 말하기는 어려운 문제인 것 같다. 외삽과 데이터셋 내의 패턴을 잘 활용한다를 정확히 구분해서 말하기가 쉽지는 않을 것 같다. 그렇지만 여전히 생각해볼만한 지점을 제안한다고 본다. 또한 프리트레이닝을 잘 하는 방법과 파인튜닝을 잘 하는 방법 모두 탐색할 여지가 많지 않은가 생각되기도 하고.

https://arxiv.org/abs/2007.06919

AQD: Towards Accurate Quantized Object Detection (Jing Liu, Bohan Zhuang, Peng Chen, Mingkui Tan, Chunhua Shen)

fcos/retinanet에 대한 quantization. 늘 그렇듯(?) 배치놈과 씨름을 좀 하고 quantized 모델의 파인튜닝 과정을 개선. 공개되어있는 레포가 흥미로움. (https://github.com/blueardour/model-quantization)

https://arxiv.org/abs/2007.06600

Closed-Form Factorization of Latent Semantics in GANs (Yujun Shen, Bolei Zhou)

gan에서 semantic factor를 추출하기. Unsupervised Discovery of Interpretable Directions in the GAN Latent Space(https://arxiv.org/abs/2002.03754)와 GANSpace: Discovering Interpretable GAN Controls(https://arxiv.org/abs/2004.02546)가 떠오르는데...여기서는 더 화끈하게 noise를 latent로 매핑하는 fc의 weight의 eigenvector로 factor들을 찾아낸다! 멋진 접근.

Unsupervised Discovery of Interpretable Directions in the GAN Latent Space에서는 infogan스럽게 latent space에서 이동한 방향과 크기를 출력하는 모델을 만들어서 학습시키고, 동시에 이 모델이 검출하기 가장 쉬운 방향, 즉 salient한 방향을 학습하는 방식으로 움직였다. GANSpace: Discovering Interpretable GAN Controls에서는 latent space에서 샘플을 뽑아 그 샘플들을 pca하는 방법을 사용했고...이 논문은 그냥 latent space로 매핑하는 fc의 eigenvector를 사용한다. 방법이 더 산뜻하고 심플해지고 있다.

https://arxiv.org/abs/2007.07431

COCO-FUNIT: Few-Shot Unsupervised Image Translation with a Content Conditioned Style Encoder (Kuniaki Saito, Kate Saenko, Ming-Yu Liu)

funit에서 컨텐츠가 출력 이미지에서 손실되는 문제를 수정. 스타일 인코더에서 스타일 이미지 뿐만 아니라 컨텐츠 이미지도 인코딩해서 결합하는 방법으로 문제 해소.

스타일 임베딩과 컨텐츠 임베딩을 비교적 shallow하게 결합하는 모듈이 핵심인데...이 결합이 디코더에서 adaptive normalization으로 발생하는 스타일과 컨텐츠의 결합을 크게 향상시킨다는 점이 흥미로워 보인다. 좀 더 생각해볼 가치가 있을 듯. 스타일 임베딩의 표현력을 컨텐츠와 결합해서 좀 확장해야 하지 않는가 하는 생각을 했었는데 비슷한 결론으로 생각할 수 있을 듯 하다.

https://arxiv.org/abs/2007.07834

InfoXLM: An Information-Theoretic Framework for Cross-Lingual Language Model Pre-Training (Zewen Chi, Li Dong, Furu Wei, Nan Yang, Saksham Singhal, Wenhui Wang, Xia Song, Xian-Ling Mao, Heyan Huang, Ming Zhou)

cross-lingual lm. mlm + translation lm에 moco를 사용해 문장 단위의 constrastive learnin objective를 결합.

https://arxiv.org/abs/2007.07779

AdapterHub: A Framework for Adapting Transformers (Jonas Pfeiffer, Andreas Rücklé, Clifton Poth, Aishwarya Kamath, Ivan Vulić, Sebastian Ruder, Kyunghyun Cho, Iryna Gurevych)

트랜스포머를 통째로 파인튜닝하는 대신 어댑터를 사용하는 접근을 위한 프레임워크. 어댑터는 작아서 공유하기 쉽고, 어댑터를 사용하면 다양한 과제나 데이터를 결합하는 작업이 용이해짐. 학습된 어댑터를 공유하는 AdapterHub도 공개. https://adapterhub.ml/

상당히 흥미로운 방향인 것 같다. 가볍고 쉽게 사용할 수 있고 모듈러하고 조합 가능한 컴포넌트! 프로그래머들이 이보더 더 좋아할 것이 있을까.

https://arxiv.org/abs/2007.08103

Probabilistic Anchor Assignment with IoU Prediction for Object Detection (Kang Kim, Hee Seok Lee)

앵커 부여 문제. 확률적이고, 모델의 학습 과정에 adaptive하고 특별한 threshold가 없는 방법을 추구. cls/loc loss를 사용해 앵커에 스코어를 부여하고 그 스코어들에 gmm(!)을 피팅해서 pos/neg를 분리함. 앵커 부여가 이렇게 어렵습니다.

ATSS(https://arxiv.org/abs/1912.02424), FreeAnchor(https://arxiv.org/abs/1909.02466), Guided Anchoring(https://arxiv.org/abs/1901.03278) 등등...디텍션 모델의 학습 과정에서 어떻게 앵커를 부여할 것인지는 중요한 문제였다. 앵커 프리 방법을 쓴다고 하더라도 결국 어떻게 feature map에 gt 타겟을 부여해서 loss를 계산할 것인가라는 문제가 남기 때문에 여전히 비슷한 문제가 있다고 할 수 있겠다. End-to-End Object Detection with Transformers(https://arxiv.org/abs/2005.12872)처럼 아예 그런 것 없이 end2end에 더 가깝게 나아가는 것이 맞을지도 모른다. 아직은 충분하지는 않아 보이지만 딥 러닝판이라면 곧 많은 진전이 등장할지도.

https://arxiv.org/abs/2007.08508

RepPoints V2: Verification Meets Regression for Object Detection (Yihong Chen, Zheng Zhang, Yue Cao, Liwei Wang, Stephen Lin, Han Hu)

verification, 즉 object인지 아닌지에 대한 분류 문제를 regression과 결합. 코너 포인트와 박스 안/밖 분류를 regression과 결합하는 방법. objects as points에서 pose detection을 키포인트와 regression의 결합으로 풀었던 것이 생각남.

https://arxiv.org/abs/2007.05869

Adversarially-Trained Deep Nets Transfer Better (Francisco Utrera, Evan Kravitz, N. Benjamin Erichson, Rajiv Khanna, Michael W. Mahoney)

adversarial training이 된 모델이 다른 데이터셋에 더 잘 trasfer되고 학습이 빠르다는 결과. 그런데 테스트 데이터셋을 패치에 가까운 데이터셋들만 선정했는지 약간 의문.

https://arxiv.org/abs/2007.08489

Do Adversarially Robust ImageNet Models Transfer Better? (Hadi Salman, Andrew Ilyas, Logan Engstrom, Ashish Kapoor, Aleksander Madry)

robust 모델이 더 잘 transfer 되는가? 얼마 전 나온 https://arxiv.org/abs/2007.05869와 비슷한 아이디어지만 실험이 더 다양함. imagenet accuracy와 robustness, 모델 width와 transfer performance에 상호작용이 있음을 밝힘. https://arxiv.org/abs/2006.14536 같은 결과로 robust 모델의 성능을 개선했을 때의 결과가 궁금해짐.

adversarial training으로 학습된 모델의 feature가 인간의 지각과 더 align 되어있는 것 같다는 이야기는 꾸준히 있었다. 이 두 사례들이 이렇게 학습된 feature가 더 일반적이라는 것을 증명해주는 듯 싶다. non robust한 feature들이 버그라기보다는 실제로 학습된 데이터셋에 대해서는 유용한 feature일 수 있다고 했던 제안(https://arxiv.org/abs/1905.02175)과 연관지어 생각하면 더 흥미롭다.

https://arxiv.org/abs/2007.08100

Towards Debiasing Sentence Representations (Paul Pu Liang, Irene Mengze Li, Emily Zheng, Yao Chong Lim, Ruslan Salakhutdinov, Louis-Philippe Morency)

문장 representation에 대한 debiasing. 일단 bias가 반영될 수 있는 단어들을 선정한 다음 코퍼스에서 이 단어들을 서로 대체한 데이터를 생성. 이 코퍼스의 representation에 대해 pca로 bias를 반영하는 컴포넌트를 찾아냄.

이 문제는 Pearl이 꾸준히 강조하는 것처럼 인과추론의 관점이 필요한 것이 아닌가 하는 생각이 든다. 이 연구에서도 간단한 형태로 다른 변수들을 통제하고 한 단어를 쌍을 이루는 동등한 단어로 교체했을 때 변화하는 것이 bias라는 가정이 쓰였다.



#review