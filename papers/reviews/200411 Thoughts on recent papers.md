# 200411 최근 논문들에 대한 생각

이번 주도 좀 흥미로웠던 논문들 중 또 몇 편을 뽑아서 코멘트를 달아봤다.
#
https://arxiv.org/abs/2004.01655
Aligned Cross Entropy for Non-Autoregressive Machine Translation (Marjan Ghazvininejad, Vladimir Karpukhin, Luke Zettlemoyer, Omer Levy)
nonautoregressive mt 문제에서 cross entropy는 토큰의 위치가 어긋난 것에 대해 큰 패널티를 주기 때문에 학습을 어렵게 만듦. 이를 완화해서 모델 출력과 타겟 토큰 시퀀스 사이의 가능한 alignment들을 고려해서 loss를 계산하기.
mt 연구가 꽤 나왔다. 위는 nonautoregressive mt 문제. unsupervised 혹은 semisupervised mt 문제에서도 좀 나왔는데 주로 어떤 언어 쌍에 대해서는 paired data가 많을 때 이를 활용해서 성능을 개선하는 방법들.
#
https://arxiv.org/abs/2004.02178
FastBERT: a Self-distilling BERT with Adaptive Inference Time (Weijie Liu, Peng Zhou, Zhe Zhao, Zhiruo Wang, Haotang Deng, Qi Ju)
트랜스포머 마지막 레이어의 classifier를 teacher로 삼고 나머지 레이어들에 classifier를 달아 student로 만들어 self distillation을 수행. 그리고 각 레이어의 classifier의 결과로 uncertainty를 계산해서 uncertainty가 높으면 다음 레이어로 넘기고 낮으면 결과를 출력하는 방식.
https://arxiv.org/abs/2004.04037
DynaBERT: Dynamic BERT with Adaptive Width and Depth (Lu Hou, Lifeng Shang, Xin Jiang, Qun Liu)
bert 깎기. 일단 네트워크를 헤드/뉴런의 중요도 순으로 재배열한 다음 각 width/height에 해당하는 subnetwork에 대해서 distillation. bert 너무 괴롭히는 거 아님!?
nlp에서 흥미롭게 생각하는 주제 두 가지가 pretraining 방법 개선과 네트워크 구조 개선 혹은 최적화인데 이쪽은 후자에 속하는 논문들. 주로 실제 deploy를 위해서 모델을 경량화하는 방법들이다. 이외에도 여러 편 더 나왔는데 보통 핵심은 distillation의 힘을 활용해 depth/width를 줄이는 방법.
evolved transformer처럼 서치의 힘으로 문제를 풀어보는 것도 재미있을 듯 한데. 아니면 모바일넷처럼 손으로 깎은 모듈들이 등장하는 것도. (관련해서 mobilebert가 이번에 arxiv에 올라왔다. https://arxiv.org/abs/2004.02984)
#
https://arxiv.org/abs/2004.02222
Structural-analogy from a Single Image Pair (Sagie Benaim, Ron Mokady, Amit Bermano, Daniel Cohen-Or, Lior Wolf)
이미지의 구조적(공간적 배치 같은) 특징을 반영해 img2img translation을 수행하기. singan처럼 한 이미지 내에서 여러 스케일의 패치를 기반으로 학습하는 방식을 도입한 것이 핵심.
https://arxiv.org/abs/2004.04634
TuiGAN: Learning Versatile Image-to-Image Translation with Two Unpaired Images (Jianxin Lin, Yingxue Pang, Yingce Xia, Zhibo Chen, Jiebo Luo)
단 두 장의 이미지로 img2img translation. Structural-analogy(https://arxiv.org/abs/2004.02222)와 유사하게 singan + cycle consistency 기반. singan이 워낙 놀라운 결과를 보여줘서 이쪽 연구가 많이 나오고 있음. 나의 SinGAN 맛좀 쬐끔만 보거라!
이 두 논문은 비슷한 시기에 나와 아이디어도 흡사하다. singan 스타일의 프레임워크에 cycle consistency를 사용해 img2img translation을 수행한 것. singan 등의 패치 기반 gan이 단 한 장의 이미지로 흥미로운 생성이 가능한 것을 보여준 이상 이미지 두 장으로 img2img translation을 할 수 있다는 것도 당연한 것인지도 모르겠다. 새로운 방향의 접근을 여는 연구들이 있는데 singan도 그 중 하나라고 할 수 있지 않을까.
#
https://arxiv.org/abs/2004.01704
Discriminator Contrastive Divergence: Semi-Amortized Generative Modeling by Exploring Energy of the Discriminator (Yuxuan Song, Qiwei Ye, Minkai Xu, Tie-Yan Liu)
https://arxiv.org/abs/2003.06060 과 상당히 유사한 접근. gan을 ebm으로 해석해서 랑주뱅 역학으로 샘플링한다는 아이디어. 여기서는 discriminator 파인튜닝을 랑주뱅 역학으로 뽑은 샘플로 수행.
이쪽도 상당히 비슷한 아이디어가 나와서 놀랐던 연구. 어쨌든 discriminator를 활용해 gan 샘플링 과정을 향상시키는 방법들이 흥미로운 결과를 보여주고 있다.
#
https://arxiv.org/abs/2004.02546
GANSpace: Discovering Interpretable GAN Controls (Erik Härkönen, Aaron Hertzmann, Jaakko Lehtinen, Sylvain Paris)
gan latent space에서 의미 있는 방향 찾기. noise를 입력해서 나오는 중간 레이어의 activation(stylegan이라면 w space)에 PCA를 한다. 끝!
gan에서 유의미한 요인들을 찾아내는 것도 중요한 주제 중 하나인데 이 방법이 지금까지 내가 본 방법 중에서는 가장 단순한 방법인 듯. 생각해보면 지금까지 이걸 왜 안 했지 싶기도 한데, 아마 가장 핵심적인 아이디어인 noise space가 아니라 activation space에서 요인을 찾겠다 때문일 것이다.
#
https://arxiv.org/abs/2004.03355
Inclusive GAN: Improving Data and Minority Coverage in Generative Models (Ning Yu, Ke Li, Peng Zhou, Jitendra Malik, Larry Davis, Mario Fritz)
gan에서 데이터 혹은 마이너 클래스의 커버리지를 높이기.
기본적인 방법은 데이터셋의 각 이미지와 가장 가까운 이미지를 생성하는 latent code를 찾고, 그 다음 반대로 각 latent code에서 생성된 샘플을 해당 이미지를 reconstruction 하도록 학습시키는 것. 종종 등장한 계통의 방법이다.
좀 생각해보고 있는데 여러모로 중요한 사례이자 방법인 것 같다. 커버리지가 높아진다는 것은 모델에서 우리가 원하는 이미지와 가까운 샘플을 찾아낼 가능성이 높아진다는 의미이기 때문에. (뒤집어라 gan!)
#
https://arxiv.org/abs/2004.03805
State of the Art on Neural Rendering (Ayush Tewari, Ohad Fried, Justus Thies, Vincent Sitzmann, Stephen Lombardi, Kalyan Sunkavalli, Ricardo Martin-Brualla, Tomas Simon, Jason Saragih, Matthias Nießner, Rohit Pandey, Sean Fanello, Gordon Wetzstein, Jun-Yan Zhu, Christian Theobalt, Maneesh Agrawala, Eli Shechtman, Dan B Goldman, Michael Zollhöfer)
neural rendering, 즉 각종 입력에 대해 사실적인 이미지를 생성하는 과제들에 대한 리뷰.
상당히 다양한 과제들에 대해서 정리하고 있다. 중간에 (리뷰 논문에서 보면 괜히 마음에 드는) 근사한 표도 있다. 그런데 참 뉴럴넷 판이 워낙 속도가 빨라서 리뷰하고 정리하는 것도 쉽지 않을 듯 싶다. novel view synthesis 과제에서 NeRF (http://www.matthewtancik.com/nerf) 같은 게 한 달 전에 튀어나오고. 
#
https://arxiv.org/abs/2004.04690
Orthogonal Over-Parameterized Training (Weiyang Liu, Rongmei Lin, Zhen Liu, James M. Rehg, Li Xiong, Le Song)
random init weight는 고정시켜두고 이를 변환하는 orthogonal matrix를 학습시키는 방법. 이렇게 했을 때 낮은 hyperspherical energy - 높은 뉴런들의 diversity를 보장할 수 있다는 것을 제안. 흥미로움.
요즘 orthogonality에 대한 연구도 많이 나오고 있다. 최근 나온 것으로는 https://arxiv.org/abs/2004.00917 이런 쪽도 있고. 이 논문이 흥미로운 것은 뉴런의 diversity를 높인다는 아이디어를 직접적으로 명시한 것. 관련해서 https://arxiv.org/abs/2002.08473 이런 사례들을 연관지어 생각해볼 수 있지 않을까 싶은 생각도 든다.
#
https://arxiv.org/abs/2004.01849
Pixel Consensus Voting for Panoptic Segmentation (Haochen Wang, Ruotian Luo, Michael Maire, Greg Shakhnarovich)
픽셀 단위 voting 기반 panoptic segmentation. voting의 영역을 중심에서 멀어질수록 크게 잡는 것이 핵심. (peripheral vision?)
instance segmentation과 panoptic segmentation이 주요한 과제로 떠오르면서 bounding box를 경유하지 않고 이 문제를 돌파해보려는 연구들이 많이 등장하고 있다. 예를 들면 Panoptic DeepLab(https://arxiv.org/abs/1911.10194) 같은 방법들. 다양한 방법들이 시도되고 있다는 점에서 의미있는 것 같다.

#review