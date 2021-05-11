트위터에 다 올리는 논문들이긴 하지만, 그래도 이번 주에 눈에 띄었던 논문들 중 몇 편에 대해서 (트위터에서는 쓰기 어려운) 조금 긴 코멘트를 달아보기.
https://arxiv.org/abs/2003.13659
Exploiting Deep Generative Prior for Versatile Image Restoration and Manipulation (Xingang Pan, Xiaohang Zhan, Bo Dai, Dahua Lin, Chen Change Loy, Ping Luo)
요즘 나오는 degradation된 이미지를 타겟으로 해서 gan의 weight와 latent 공간을 탐색하기. perceptual loss 대신 feature matching을 사용하고 점진적으로 학습하도록 튜닝했다는 것이 특징. PULSE(https://arxiv.org/abs/2003.03808)와 비슷.
https://arxiv.org/abs/2004.00049
In-Domain GAN Inversion for Real Image Editing (Jiapeng Zhu, Yujun Shen, Deli Zhao, Bolei Zhou)
gan 뒤집기의 늪 속으로. 인코더 기반 방법인데 특징은 생성 결과가 아니라 실제 이미지로 학습한다는 것과 discriminator를 활용한다는 것.
gan이 원래 좀 그렇긴 했다. 숫자로 따지면 generative model로서 장점보다 단점이 더 많은 게 아닌가 싶은데, 높은 퀄리티의 이미지를 생성할 수 있다는 것과 computation이 비교적 적게 필요한 모델이라는 장점이 워낙 커서 그런지 이 불안정한 모델을 좀 제대로 학습시켜보기 위해 정말 수많은 노력들이 들어갔다.  DCGAN(https://arxiv.org/abs/1511.06434), Improved Techinques(https://arxiv.org/abs/1606.03498), WGAN(https://arxiv.org/abs/1701.07875), WGAN-GP(https://arxiv.org/abs/1704.00028), Hinge Loss(https://arxiv.org/abs/1705.02894), TTUR(https://arxiv.org/abs/1706.08500), R1 Penalty(https://arxiv.org/abs/1801.04406), Spectral Normalization(https://arxiv.org/abs/1802.05957), Projection Discriminator(https://arxiv.org/abs/1802.05637), Self Attention(https://arxiv.org/abs/1805.08318), BigGAN(https://arxiv.org/abs/1809.11096) 등. 생각나는 주요한 방법들만 꼽아도 이렇고 그 외 수많은 연구들까지 생각하면...
일단 그래서 그럭저럭 안정적으로 괜찮은 샘플들을 뽑아낼 수 있게 되니 이제 gan의 문제 중 하나인 샘플의 확률/latent code를 추정하기 어렵다는 문제를 해결하기 위해 수많은 노력들이 투입되고 있다. 즉 다들 gan inversion의 매운 맛을 보고 있는 중이다. gan inversion을 해본 사람들은 알겠지만 생각보다 잘 안 된다. 결국 latent space에 대한 optimization으로 태클하게 되는데 이 부분에서 조심하지 않으면 이상한 이미지로 잘 튄다. objective가 non convex하다는 것에서 발생할 수 있는 문제를 잘 보여주는 사례라고 해야하지 않을까 싶을 정도.
그래서 이걸 되게 만드려고 상당히 많은 제약이나 시도가 계속되고 있다. 이러다 보니 실제로는 gan 모델의 노이즈 분포에서는 샘플링이 불가능한 latent code를 사용하는 것이 거의 국룰이 되었다. 예를 들어 stylegan을 inversion하는 경우 모델의 노이즈 입력인 R^512 벡터에 한정해서 inversion을 하면 이미지 퀄리티에 한계가 있다. 이 제약을 완화해서, stylegan의 특성상 매 conv layer마다 latent vector가 들어가게 되는데, 이 latent vector를 conv layer마다 다르게 주는 방법이 흔히 쓰인다. 원칙적으로는 모델에서 샘플링될 수 없는 방향으로 가버린 것이지만 그래야 잘 되니까. (그런데 또 모델이 학습할 때는 latent code가 제각각인 경우를 보지 못했기 때문에 너무 풀어주면 이상한 방향으로 가버린다. 이 미묘함...) 더 나아가서 모델 자체도 튜닝하는 경우도 많다.
이게 사실 맞는 방향인지는 잘 모르겠다. 잘 안 되는 것을 어떻게든 되게 만드려고 하는 것처럼 보이기도 해서. 그런데 일단 stylegan이나 biggan이 뽑아내는 샘플의 퀄리티를 한 번 보면 여전히 감탄 밖에 안 나오고 이걸 어떻게든 써봐야겠다는 생각이 드는 것도 사실이다. 대안이 될만한 maximum likelihood 모델들이 좀 더 그럴싸하다는 생각이 많이 드는데 이쪽은 보통 computational cost가 너무 비싸니까.
요즘 이 문제를 좀 해보려다 보니 말이 길어졌다...
여하튼 이번 주에 나온 논문들을 보면 좀 흥미로운 것은 discriminator를 적극적으로 사용했다는 것이다. 보통 inversion을 위한 loss로 mse 같은 pixelwise loss나 perceptual loss를 많이 활용했는데 이걸 넘어 discriminator를 활용한 것. gan을 학습하는 당시에 사용했던 게 disciminator이라는 것을 생각해보면 discriminator를 잘 활용하는 것이 자연스러운 방향인 것 같기도 하다.
https://arxiv.org/abs/2003.13630
TResNet: High Performance GPU-Dedicated Architecture (Tal Ridnik, Hussam Lawen, Asaf Noy, Itamar Friedman)
resnet 깎기. antialiasing은 요즘 classification 하는 사람들에게는 국룰. leaky relu가 다시 출동했다는 것과 stem 부분에서 conv 없이 그냥 width/height 방향을 channel로 접어버리는 방식으로 downsampling 했다는 것이 흥미로움. resnet 깎는 사람들 생각보다 많네.
https://arxiv.org/abs/2003.13678
Designing Network Design Spaces (Ilija Radosavovic, Raj Prateek Kosaraju, Ross Girshick, Kaiming He, Piotr Dollár)
모델 서치에서 모델 구조에 대한 부과해보다가 depth에 따른 width의 증가를 (양자화된) 선형으로 움직이도록 제약해본 결과. efficientnet보다 빠르고 정확한 모델을 찾을 수 있었다. 다들 resnet을 더 깎으러 가셔도 될 듯.
이 두 논문은 resnet 깎기. 사실 designing network design spaces는 단순히 resnet을 깎는 것보다도 모델 서치를 잘 하려고 하는 쪽이 가깝긴 한데 어쨌든 이 방법을 사용해서 훌륭하게 깎은 resnet을 만들어냈다.
여담이지만 최근 res2net(https://github.com/Res2Net/Res2Net-PretrainedModels)이 업데이트된 걸 발견했다. Bag of tricks (https://arxiv.org/abs/1812.01187) 논문의 개선들, stem을 보강하고 skip connection conv에 avg pool을 사용하는 것을 도입했는데 보여주는 성능이 흥미롭다.
https://arxiv.org/abs/2004.00345
Editable Neural Networks (Anton Sinitsin, Vsevolod Plokhotnyuk, Vsevolod Plokhotnyuk, Sergei Popov, Artem Babenko)
뉴럴넷 모델에서 발생한 오류를 다른 데이터에 대한 성능에 영향을 미치지 않고 수정하기 위한 방법. 결론적으로는 오류 수정 작업(모델 업데이트)에 대한 메타 러닝 문제가 됨.
https://arxiv.org/abs/2004.00830
Tracking by Instance Detection: A Meta-Learning Approach (Guangting Wang, Chong Luo, Xiaoyan Sun, Zhiwei Xiong, Wenjun Zeng)
object detector를 가져와서 MAML로 새로운 샘플에 대해 빠르게 학습할 수 있도록 학습시킨 다음, 새로운 타겟에 대해 타겟을 주고 학습시켜서 이후 프레임의 타겟을 bounding box를 검출해서 트래킹하는 방법. 
이쪽은 메타러닝. 메타러닝이 최근 흥미로운 응용 사례들을 보여주고 있다. 얼마 전 쓴 글도 있고 해서 여러모로 생각을 좀 해보게 되지만 어쨌든 학습이 잘 되도록 모델을 학습시킨다는 목표는 중요하다. 핵심은 학습이 잘 되도록 모델을 학습시키는 방법이 얼마나 잘 되게 만들 수 있는가이지만. 정말 메타-하다...
https://arxiv.org/abs/2004.00849
Pixel-BERT: Aligning Image Pixels with Text by Deep Multi-Modal Transformers (Zhicheng Huang, Zhaoyang Zeng, Bei Liu, Dongmei Fu, Jianlong Fu)
요즘 자주 나오는 image-text pretraining. bounding box로 feature를 추출하는 대신 이미지 전체를 resnet에 넣고 나온 feature를 펼쳐서 임베딩으로 입력.
이런 이미지-텍스트 과제에서는 object detection 결과를 사용하는 게 일반적이었는데 그 부분을 단순화했다. 바야흐로 프리트레이닝의 시대.
https://arxiv.org/abs/2004.01180
Learning to See Through Obstructions (Yu-Lun Liu, Wei-Sheng Lai, Ming-Hsuan Yang, Yung-Yu Chuang, Jia-Bin Huang)
연속된 프레임을 입력으로 받아 이미지에서 obstruction을 제거. optical flow를 예측하고, 배경과 obstruction 두 레이어의 이미지를 reconstruction하고, 다시 optical flow를 refine하는 것을 반복하는 방식으로 동작.
https://arxiv.org/abs/2004.00626
Background Matting: The World is Your Green Screen (Soumyadip Sengupta, Vivek Jayaram, Brian Curless, Steve Seitz, Ira Kemelmacher-Shlizerman)
matting 과제. 전경/알파에 대한 레이블이 없는 데이터셋을 활용해 추가적으로 학습했다는 것이 흥미로움. 알파를 전부 1로 만들어서 입력 이미지를 복붙해버리는 것을 막기 위해 synthetic 데이터에 대해 학습된 모델의 출력과의 차이에 대해 loss를 추가.
잘 몰랐던 과제들인데 결과가 재미있다.
https://arxiv.org/abs/2004.01177
Tracking Objects as Points (Xingyi Zhou, Vladlen Koltun, Philipp Krähenbühl)
objects as points 기반 객체 트래킹. 이미지 두 장을 입력으로 주고 객체의 이동 방향 오프셋을 예측하게 하는 방법. anchor free detection은 flickering도 적다고 알려져 있으니 더 유용할지도?
objects as points는 이제 anchor free detection의 대표적인 방법 중 하나가 됐다. 간단히 설명하자면 bounding box 중심에서 히트맵을 찍어서 어떤 객체가 있는지를 분류하게 하고, 그 히트맵의 중심에서 bounding box의 크기를 바로 예측하게 하는 방법이다. 앵커를 사용하지 않고 히트맵을 찍고 그 히트맵 가운데에서 오프셋을 예측하게 만들면 되니까 실제 구현도 정말 단순해진다.
이 단순함과 히트맵과 오프셋을 사용한다는 아이디어의 범용성 때문인지 이 아이디어를 활용한 방법들이 보이고 있다. 사실 objects as points에서부터 이 접근을 기반으로 3d object detection이나 pose estimation을 시도하기도 했다.
이 논문은 (objects as points 저자들이 쓴 논문이긴 한데) 이 아이디어를 tracking에 적용해본 것. tracking에서도 상당히 단순한 방법으로 접근한다. 연속된 두 프레임을 입력으로 주고 object detection을 위한 출력에 추가적으로 객체의 이동 방향을 오프셋으로 예측하게 만든다. 끝!
단순한 방법의 강력함에 대해 좀 생각해보게 된다.

#review