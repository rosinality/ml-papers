이번에는 좀 놀아서 분량이 적다.
https://arxiv.org/abs/2007.10909
SliceOut: Training Transformers and CNNs faster while using less memory (Pascal Notin, Aidan N. Gomez, Joanna Yoo, Yarin Gal)
채널이나 feature map의 일부만을 잘라내서 forward. regularization 효과와 함께 학습 속도 향상 및 메모리 소모 감소. 이걸 튜닝하는데 추가적은 자원을 쓰지만 않으면 CO2 배출량 감축에 기여할 수 있을 듯. 
pytorch 같은 경우에 이런 tensor slicing operation이 얼마나 효율적인지는 모르겠다. 물론 효율이 나쁘지는 않았던 것으로 기억하고 있는데.
https://arxiv.org/abs/2007.10396
NSGANetV2: Evolutionary Multi-Objective Surrogate-Assisted Neural Architecture Search (Zhichao Lu, Kalyanmoy Deb, Erik Goodman, Wolfgang Banzhaf, Vishnu Naresh Boddeti)
기존 nas 알고리즘들을 끌어와 조합하고 개선한 방향의 연구. 가장 중요한 선택은 performance prediction과 supernet을 weight 초기화에만 쓴다는 결정이 아닐까 싶음. 결과는 상당히 흥미로운 듯. 
사실 흥미로운 정도를 넘어 꽤 괜찮은 결과인 것 같다. 312 MAdds & 7.7 M 파라미터로 78.3%.
https://arxiv.org/abs/2007.10637
Distributed Memory based Self-Supervised Differentiable Neural Computer (Taewon Park, Inchul Choi, Minho Lee)
differentiable neural computer의 개선. 여러 개의 메모리 블럭을 사용하고 memorize를 촉진하는 loss를 사용. memo(https://arxiv.org/abs/2001.10913) 이후로 오랜만에 보는 이 계통의 연구인 듯. 
GPT-4가 나온다면 모델과 데이터의 규모를 더 키우는 것도 재미있겠지만 이런 식의 새로운 모듈을 도입하는 것도 의미있지 않을까? 물론 이런 모듈의 포텐셜을 충분히 활용하려면 데이터와 학습 objective가 그에 걸맞아야 하겠지만.
https://arxiv.org/abs/2007.11576
Deep Variational Instance Segmentation (Jialin Yuan, Chao Chen, Li Fuxin)
Mumford-Sha 모델 기반 instance segmentation. 이미지의 각 영역을 piecewise smooth하게 근사하는 방법. 결론적으로는 같은 인스턴스의 픽셀값끼리는 근접시키고 다른 인스턴스의 픽셀값끼리는 마진을 주는 메트릭 러닝스러운 permutation invariant loss가 핵심. 흥미로움. 
각 instance 영역에서 특정한 값의 스칼라를 갖도록 학습시키는 것. instance 사이에는 특정한 순서가 없으니 레이블을 정해서 주고 학습시킬 수는 없고 결과적으로 임베딩/메트릭 러닝과 비슷한 접근을 도입한다. 이런 아주 새로운 형태의 접근의 의미가 크다고 생각한다. End-to-End Object Detection with Transformers(https://arxiv.org/abs/2005.12872) 처럼. 이런 방법들 중 더 의미있는 방식으로 발전해가는 방법은 그렇게 많지는 않지만.
https://arxiv.org/abs/2007.11498
CrossTransformers: spatially-aware few-shot transfer (Carl Doersch, Ankush Gupta, Andrew Zisserman)
쿼리와 서포트 사이의 attention을 사용해 쿼리의 프로토타입을 생성하는 few shot learning. supervised training된 백본의 이미지 임베딩의 문제를 simclr을 사용해 극복했다는 것이 흥미로움. 
https://arxiv.org/abs/2007.11259
Adversarial Training Reduces Information and Improves Transferability (Matteo Terzi, Alessandro Achille, Marco Maggipinto, Gian Antonio Susto)
robustness와 transferability 3. adversarial training은 데이터셋에 대한 weight의 fisher information을 줄이는 효과가 있고 이것이 데이터셋에 대한 perturbation의 영향을 줄이는 효과가 있음. 그래서 분포가 많이 다른 경우에는 robust 모델이 더 낫다는 추정. (분포가 비슷하면 반대가 됨.) 
adversarial training은 데이터셋 perturbation의 영향을 줄이기 때문에 pretrain 데이터셋과 finetuning 데이터셋이 서로 많이 다른 경우에는 장점이 있고 비슷한 경우에는 (adversarial training으로 인한 정확도 감소가 작용해서) 성능이 떨어진다는 결론. 정말로 옳은 방향이라면 상당히 산뜻한 결론이다. 데이터셋의 변동에 대한 강건성 자체를 목표로 잡고 접근해나가는 것이 필요한 시점이 되었다고 생각할 수도 있고. (사실 딥 러닝 판의 가장 중요한 떡밥은 바로 이 데이터셋의 변동에 대한 강건성 혹은 도메인 문제라고 생각한다.)
https://arxiv.org/abs/2007.12072
TSIT: A Simple and Versatile Framework for Image-to-Image Translation (Liming Jiang, Changxu Zhang, Mingyang Huang, Chunxiao Liu, Jianping Shi, Chen Change Loy)
img2img 프레임워크. 컨텐츠/스타일 인코더를 두고 이 두 정보를 spade를 확장한 블럭으로 결합. discriminator/feature matching은 스타일 이미지에 대해 돌리고 perceptual loss는 컨텐츠에 대해 적용해서 unsupervised setting이 가능하게 만듦. 
컨텐츠는 perceptual loss에게 스타일은 discriminator와 feature matching에게. 아주 심플.
https://arxiv.org/abs/2007.11823
WeightNet: Revisiting the Design Space of Weight Networks (Ningning Ma, Xiangyu Zhang, Jiawei Huang, Jian Sun)
se와 condconv 합치기. 여타 채널 attention처럼 gap로 끌어모은 다음 grouped linear를 사용해 컨볼루션 커널을 생성. 우왕. 
이런 channel attention 계통의 방법이 일반적인 비전 과제에 대해서 어떤 의미가 있는가에 대해서는 요즘 좀 회의적이긴 한데...어쨌든 중요한 방법이다.
https://arxiv.org/abs/2007.12099
PP-YOLO: An Effective and Efficient Implementation of Object Detector (Xiang Long, Kaipeng Deng, Guanzhong Wang, Yang Zhang, Qingqing Dang, Yuan Gao, Hui Shen, Jianguo Ren, Shumin Han, Errui Ding, Shilei Wen)
욜로 깎기. 요즘 디텍터를 이런 식으로 깎는 연구들이 유행인 듯. 사실 디텍션을 이전부터 하던 사람들은 튜닝을 위한 레시피를 다들 갖고 있을 것 같음. 이미 정말 많은 조각칼들이 있으니. 
YOLOv4(https://arxiv.org/abs/2004.10934)도 그렇고. 이미 조각칼들이 많이 주어져 있으면 그것들을 조합해서 어떤 것이 의미가 있는지, 특히 다른 조각칼들과 조합했을 때에도 여전히 의미가 있는 것이 무엇인지를 정리할 필요가 있다. 여튼 디텍션 하시는 분들은 다들 자신만의 레시피가 있을 것이라 생각.
https://arxiv.org/abs/2007.11978
The Devil is in Classification: A Simple Framework for Long-tail Instance Segmentation (Tao Wang, Yu Li, Bingyi Kang, Junnan Li, Junhao Liew, Sheng Tang, Steven Hoi, Jiashi Feng)
lvis 같은 롱테일 디텍션에서 주요한 문제가 proposal에 대한 classification이라고 진단. 모든 클래스를 동등하게 샘플링해서 학습시키는 동시에 분포의 머리 부분과 꼬리 부분을 위한 헤드를 각각 부여함. 롱테일의 매운맛 좀 쬐끔만 보거라! 
롱테일 문제와 늘 씨름해왔던 nlp 사람들이 좀 생각나고 그렇다.
https://arxiv.org/abs/2007.08902
A Unifying Perspective on Neighbor Embeddings along the Attraction-Repulsion Spectrum (Jan Niklas Böhm, Philipp Berens, Dmitry Kobak)
다양한 시각화를 위한 임베딩 방법들이 근방의 점들끼리 끌어당기는 힘(attraction)과 모든 점들 사이의 미는 힘(repulsion)의 사이의 균형을 어디에 맞췄는가 정도의 차이라는 분석. umap이 보여주는 특성은 최적화에 도입한 네거티브 샘플링이 repulsion을 감소시킨 부산물이라고. 으악! 
어제 소개한 바로 그 논문!