오랜만이 이번 주에 눈에 띈 논문들을 페북에도 공유. 이거 써놓고 사방팔방에 공유하는 느낌이 있긴 한데...

https://arxiv.org/abs/2007.01758
Collaborative Learning for Faster StyleGAN Embedding (Shanyan Guan, Ying Tai, Bingbing Ni, Feida Zhu, Feiyue Huang, Xiaokang Yang)
gan 뒤집기. 인코더와 임베딩 최적화를 동시에 활용. 인코더로 임베딩을 생성하고 이 임베딩을 시드로 임베딩에 대한 최적화를 수행. 최적화된 임베딩을 인코더에 대한 supervision으로 활용. gan 뒤집기가 이렇게 어렵다. 최적화 자체가 까다롭다는 점하고 gan 모델이 커버하는 분포가 제한적이라는 것도 있고 ffhq 같은 데이터셋 자체도 충분히 다양하지 않은 것 같고. 어떤 사람들은 애초에 다른 생성 모델을 두고 gan을 써서 그런 고생을 사서 하는가 하기도 하지만. (밑의 nvae를 보자!) 
​
​https://arxiv.org/abs/2007.01852
Language-agnostic BERT Sentence Embedding (Fangxiaoyu Feng, Yinfei Yang, Daniel Cer, Naveen Arivazhagan, Wei Wang)
MLM과 Translational LM을 사용해 109개 언어에 대한 문장 임베딩 모형을 학습. bilingual 데이터셋 구축에 어노테이션 작업을 하기도 해서 상당한 공을 들였을 듯. 
​​​
https://arxiv.org/abs/2007.01476
Interactive Knowledge Distillation (Shipeng Fu, Zhen Li, Jun Xu, Ming-Ming Cheng, Gwanggil Jeon, Xiaomin Yang)
feature matching 대신 student 블록을 teacher 블록으로 대체해서 학습시키는 방식으로 KD. teacher가 내가 된다! imagenet에서 충분히 큰 모델에서도 잘 될지가 궁금하긴 하다. 잘 된다고 하면 블럭을 갈아끼우는 식으로 심플하게 구현할 수 있어서 꽤 장점이 될 듯. 

https://arxiv.org/abs/2007.02933
Meta-Learning Symmetries by Reparameterization (Allan Zhou, Tom Knowles, Chelsea Finn)

대칭 구조에 따라 weight sharing이 발생하도록 weight를 reparameterize한 다음 이 대칭 구조를 메타 러닝으로 학습. 우리가 이미지 데이터에 대해서 가장 쉽게 생각할 수 있는 prior가 이런 대칭성이기 때문에 이 대칭성을 모델에 주입하기 위한 작업들이 꽤 있었다. 모델 구조에 이런 prior를 주입하기 위한 노력은 중요하다고 생각한다. translation equivariance를 좀 더 개선해준 antialiased cnn이 image classification에서 곧바로 성능 개선을 가져오는 것을 보면. 다만 메타러닝이 본래 그런 것이긴 하지만 이걸 다시 데이터에서 학습했다는 게 좀 아이러니하긴 하다. 

https://arxiv.org/abs/2007.00810
On Linear Identifiability of Learned Representations (Geoffrey Roeder, Luke Metz, Diederik P. Kingma)

레이블이 충분히 다양한 상황(diversity condition)에서는 representation function이 표현하는 probability distribution이 같으면 linear transform에 대해 동일한 함수가 된다(linear identifiability)는 것을 증명. 재현성에는 정말 온갖 문제가 다 생겨서 identifiability는 오히려 작은 부분처럼 느껴지긴 하지만...어쨌든 같은 결과를 낸다면 (거의) 동일한 모델을 만들 수 있는 것이다. 

https://arxiv.org/abs/2007.03282
LabelEnc: A New Intermediate Supervision Method for Object Detection (Miao Hao, Yitao Liu, Xiangyu Zhang, Jian Sun)

kd처럼 detection 모델에 feature 레벨에서 supervision을 주려는 것이 목적. 레이블을 입력으로 받는 모델을 teacher로 삼아 이미지를 입력으로 받는 모델에 distill 해주는 방식. privileged information을 사용하는 kd인 learning by cheating이 (https://arxiv.org/abs/1912.12294)가 떠오르는 방법. 상당히 흥미로운 종류의 접근이라고 봄.

https://arxiv.org/abs/2007.03349
RIFLE: Backpropagation in Depth for Deep Transfer Learning through Re-Initializing the Fully-connected LayEr (Xingjian Li, Haoyi Xiong, Haozhe An, Chengzhong Xu, Dejing Dou)

파인튜닝 시나리오에서 학습이 빠르기 때문에, 즉 fc가 빠르게 수렴해버리기 때문에 백본은 유의미하게 튜닝되지 않음. 그렇다고 백본을 팍팍 튜닝하면 overfit이 발생. 백본을 적절하게 튜닝하면서 동시에 overfit도 예방하는 방법이 뭐가 있을까? 방법: fc weight를 주기적으로 리셋해서 다시 학습시킴. fc가 리셋되니 백본이 계속 학습되어야 함. fc가 리셋되는 것이 트레이닝 과정에서 강력한 노이즈로 작용하니 regularization 효과가 있음. 원래 regularization 업계가 신박하게 모델을 괴롭히면 성능이 올라가는 식인 경우가 종종 있지만...그래도 아니 무슨 약을 하셨길래 이런 생각을 하셨어요? (그리고 저자들이 RIFLE이라는 이름이 아주 마음에 들었던 모양. RIFLE이 등장할 때마다 볼드로 써놨다.) 

https://arxiv.org/abs/2007.03496
AutoAssign: Differentiable Label Assignment for Dense Object Detection (Benjin Zhu, Jianfeng Wang, Zhengkai Jiang, Fuhang Zong, Songtao Liu, Zeming Li, Jian Sun)

fcos 같은 anchor-free 디텍터들은 center sampling과 박스 크기에 기반한 scale assign을 통해 레이블을 부여하는데 optimal한 방식이라고 보기는 어려움. 그래서 confidence map을 뽑아서 loss를 weighting하는 방식으로 레이블 부여를 학습하게 만듦. 직관적이고 좋은 아이디어지만 구현은...까다로울 듯. Sibling Head(https://arxiv.org/abs/2003.07540) 같이 예측값을 출력하기 위해 사용하는 feature의 위치에 대한 제약을 풀어주는 종류의 방법이라고 할 수 있겠는데 아무래도 two stage 방법에 비해 도입이 까다로운 점이 있을 것 같음. 

https://arxiv.org/abs/2007.03356
Do Transformers Need Deep Long-Range Memory (Jack W. Rae, Ali Razavi)

트랜스포머-XL에는 모든 레이어에 long range attention이 들어가는데 반드시 그럴 필요는 없지 않을까? 일부 레이어만 long range attention을 사용하면 속도가 빨라질 뿐 아니라 성능도 오히려 더 나아질 수 있음. 늘 long range attention이 그 attention span을 완전히 모델링할 수 있을 정도로 잘 학습될 수 있는지에 대한 의문이 좀 있었는데 약간 힌트가 되는 듯. 충분히 유용하게 학습될 수 있지만, 약간 제약을 주는 것이 오히려 나을 수도 있다. evolved transformer에서 convolution이 도입되는 것처럼. 

https://arxiv.org/abs/2007.03260
Lossless CNN Channel Pruning via Gradient Resetting and Convolutional Re-parameterization (Xiaohan Ding, Tianxiang Hao, Ji Liu, Jungong Han, Yuchen Guo, Guiguang Ding)

성능 하락 없는 채널 프루닝. 채널의 중요도를 학습하기 위한 linear weight를 컨볼루션에 붙이고 선택한 채널에만 프루닝을 위한 penalty를 집중시키는 방법. 약간 다른 이야기이긴 한데 나는 프루닝보다도 sparsity 자체가 흥미롭다는 생각을 좀 한다. A100에서 지원될 structured sparsity까지 결합되면 여러모로 더 재밌어지지 않을까. 

https://arxiv.org/abs/2007.03074
Kernel Stein Generative Modeling (Wei-Cheng Chang, Chun-Liang Li, Youssef Mroueh, Yiming Yang)

sgld가 날아오르는 동안 svgd는 여러 문제들로 인해 그러지 못했다. ncsn(https://arxiv.org/abs/1907.05600)에서 sgld에서 데이터 분포의 support들이 분리되어 있을 때 혹은 확률의 밀도가 낮은 영역들로 분리되어 있을 때 mixing이 느려지는 문제에 주목했다. 데이터가 적은 영약이니 score를 정확하게 추정하는 것 자체도 어렵고 disjoint한 support 위에서는 다른 mode와는 관계 없이 그 support 내부에서만 움직이기 때문이다. 이 문제를 ncsn은 노이즈를 도입해서 support를 전체 영역으로 늘리는 방법을 썼다. 그러고나서 노이즈를 점차 줄여나간다.

사실 이건 전형적인 고차원의 공간에서 저차원의 매니폴드에 데이터 분포가 집중되어 있을 때 나타나는 전형적인 문제들이기도 하고, 노이즈를 도입하는 것도 이 문제를 태클하는 일반적인 방법이라고 생각할 수 있겠다.

그런데 이 방법도 svgd에는 잘 통하지 않았다. 이 논문은 문제의 원인이 노이즈 수준에 따라 샘플의 거리의 분포가 달라지는데 커널은 고정되어 있다는 것에 기인한다고 봤다. 그러니 커널이 노이즈 수준에 따라 달라지면 된다. 이를 위해 노이즈 수준을 입력으로 받는 autoencoder로 feature를 뽑고 그 feature를 사용해 커널을 구성한다. 거기에 fidelity-diversity tradeoff를 조절하기 위한 entropic regularization을 도입. 흥미로운 결과가 나왔다. 최근 ncsn 저자들이 ncsn을 갈고 닦아 고해상도 이미지에서 인상적인 결과를 낸 것(https://arxiv.org/abs/2006.09011)을 고려하면 더 흥미로워질 듯. 

https://arxiv.org/abs/2007.03898
NVAE: A Deep Hierarchical Variational Autoencoder (Arash Vahdat, Jan Kautz)

vae로 sota & 고퀄 샘플 뽑기! BIVA(https://arxiv.org/abs/1902.02102)에 이어 vae에 큰 진전이 등장했다. 핵심은 hierarchical vae를 기반으로 모델을 튜닝하고 깎고 갈고 닦기. 모델을 탐색하고 튜닝하는 것이 얼마나 중요한지를 보여주는 것이 아닌가 싶다. 그런데 이제 gan은 어쩌냐! 라고 하기에는 모델이 좀 크다. 256px 이미지를 위해 V100 24개를 사용했다. gan은 이제 학습이 까다롭지만 비교적 저렴하게 가능하다라는 것을 장점으로 갖게 된 듯. 

https://arxiv.org/abs/2007.03943
Remix: Rebalanced Mixup (Hsin-Ping Chou, Shih-Chieh Chang, Jia-Yu Pan, Wei Wei, Da-Cheng Juan)

imblanced classification을 위한 mixup의 변형. 이미지와 동일하게 레이블을 믹스하는 대신 마이너 클래스에 대해서는 마이너 클래스로 레이블을 몰아준다. 그러니까 major 0.3 minor 0.7 같은 식이 아니라 minor 1으로 해주는 식. 레이블을 실질적으로 유지시킨다는 점에서 좀 더 augmentation스러운 방식이라고 생각할 수 있을지도 모르겠다. 

https://arxiv.org/abs/2007.04504
Learning Differential Equations that are Easy to Solve (Jacob Kelly, Jesse Bettencourt, Matthew James Johnson, David Duvenaud)

neural ode의 중요한 이슈 중 하나인 학습된 모델이 그리는 궤적을 어떻게 단순화할 수 있을 것인가 하는 문제에 대한 접근. 얼마 전 나와 좋은 결과를 보여준 How to train your neural ODE을 바로 생각할 수 있다. (https://arxiv.org/abs/2002.02798) 여기서는 고차 미분항의 놈을 통제하는 방식으로 접근했다. 함수 계산 횟수를 줄이는 것엔 성공. 다만 이 regularizer를 계산하느라 학습 속도 향상까지는 도달하지 못한 듯. 일단 고차 미분항을 계산하기 위한 작업 자체에 공이 많이 들었을 듯. 

https://arxiv.org/abs/2007.04964
Improving Style-Content Disentanglement in Image-to-Image Translation (Aviv Gabbay, Yedid Hoshen)

img2img에서 content와 style의 disentangle이 확실하게 일어나지 않는 것 같다는 문제. 간단하게 content 인코더를 mean only vae로 구성. vae 붐은 온다! 그런데 애초에 컨텐츠가 무엇이고 스타일이 무엇인가 하는 생각을 좀 많이 하게 된다. 

https://arxiv.org/abs/2007.04589
InfoMax-GAN: Improved Adversarial Image Generation via Information Maximization and Contrastive Learning (Kwot Sin Lee, Ngoc-Trung Tran, Ngai-Man Cheung)

discriminator의 local feature와 global feature 사이의 mutual info를 최대화시키는 regularization을 걸어서 결과적으로 특정 부분이 아닌 이미지 전반을 반영하는 그래디언트를 생성하도록 만들자는 아이디어. discriminator가 좀 더 generator을 학습시키기에 적절한 형태로 구조화하고 학습시키는 것은 계속 중요한 문제이긴 했다. dcgan에서 그래디언트의 전달이 효과적으로 일어나도록 설계한 것이나 r1 regularization에서 generator가 real 분포에 수렴했을 때 그래디언트를 억제하는 것도 discriminator가 혼자 놀지 말고 generator를 잘 가르치도록 만들어주는 작업이었다고 볼 수 있겠다. 

https://arxiv.org/abs/2007.04825
Fast Transformers with Clustered Attention (Apoorv Vyas, Angelos Katharopoulos, François Fleuret)

reformer, longformer 등 이후에 최근 long range attention을 효율적으로 만들기 위한 연구들이 좀 나왔다. 한 가지 큰 갈래가 linear attention. efficient attention이 (https://arxiv.org/abs/1812.01243) 좀 전에 나왔었고 linearly scalable transformer(https://arxiv.org/abs/2006.03555), transformer are rnns (https://arxiv.org/abs/2006.162360) 같은 연구들이 나왔다.

이쪽은 attention 쿼리들을 k-means로 클러스터링한 다음 같은 클러스터에 있는 쿼리들은 같은 attention weight를 사용하게 해서 연산량을 감소시킨다는 접근이다. 실질적으로 query 방향으로 길이를 축소한 것이라고 볼 수 있겠다. 길이를 축소했다는 점에서는 마찬가지로 최근에 나온 funnel transformer(https://arxiv.org/abs/2006.03236)나 linformer(https://arxiv.org/abs/2006.04768)가 떠오른다. 쿼리에 lsh를 적용하고 그 위에 hamming distance 기반 k-means를 돌린다는 게 거의 묘기 같이 느껴지는데 대단하다. 