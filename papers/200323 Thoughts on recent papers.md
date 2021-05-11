GAN이 일단 생성 모델이기는 한데 생성 모델로서는 문제가 이것저것 많다. (사실 모든 생성 모델들이 제각기 문제가 있기는 하지만.) 학습 objective 자체가 안정적으로 수렴시키기 어렵고 생성 모델이기는 하지만 직접적으로 확률을 계산하기 어렵고 등등. 단순히 이론적인 문제가 아니라 실용적으로도 중요한 한계이기도 하다. 안정적으로 수렴시키기 어렵다는 것은 GAN을 수렴시키기 위한 많은 도구들과 레시피들이 주어진 지금에서도 학습시키다 터지는 경우가 적지 않다는 문제로 나타나고, 확률을 계산하기 어렵다 혹은 샘플로부터 latent code를 추출하기 어렵다는 문제는 이미지를 latent code에 프로젝션에서 뭔가를 해보려는 시도를 어렵게 만드는 문제로 나타난다. 이미지에서 latent code projection을 해본 사람들은 딥 러닝 판에서 별로 문제가 아닌 것 같았던 non convex objective의 매운 맛을 한 번 쯤은 봤을 것이다.
그러나 GAN objective를 MSE 같은 이미지에 대한 loss로 활용한다면 문제가 좀 다르다. 좋은 퀄리티의 이미지를 생성하는데 활용할 수 있는 가장 *쉬운* loss가 GAN loss인 경우가 의외로 적지 않다.
그러면 아예 문제를 좀 바꿔서, 굳이 노이즈에서 이미지를 생성하는 것이 아니라 image to image translation 같이 충분한 정보를 조건으로 주고 생성하는 것에 집중한다면 어떨까? 그걸로도 충분히 재미있지 않을까? 뭐 직접 저자들에게 들어보지는 않았지만 대충 그런 아이디어를 공유하는 것 같은 논문들이 최근 좀 나왔다. SinGAN 같은 single image gan들도 이런 방식으로 생각할 수 있을 것 같은데, 어쨌든 최근 나온 논문들을 생각해보면:
https://arxiv.org/abs/2003.02365
Creating High Resolution Images with a Latent Adversarial Generator (David Berthelot, Peyman Milanfar, Ian Goodfellow)
low resolution 이미지를 중심 시드로 해서 그 주변의 high resolution 이미지들의 분포를 생성하는 모델. 완전 super resolution스럽지만 일단 원칙적으로 super resolution과는 다르긴 하다. (별개지만 low resolution 이미지를 통해 GAN의 latent space를 탐색하는 방법도 재미있긴 하다. 여기는 그냥 대놓고 super resolution이라고 했지만. https://arxiv.org/abs/2003.03808)
https://arxiv.org/abs/2003.08074
OpenGAN: Open Set Generative Adversarial Networks (Luke Ditria, Benjamin J. Meyer, Tom Drummond)
metric learning 모델로 추출한 feature를 활용해서 생성하는 방법. feature가 잘 뽑히면 그 feature에 대해 생성이 가능하니 새로운 도메인의 이미지에 대해서도 생성이 되는 것을 기대할 수 있다.
https://arxiv.org/abs/2003.06221
Semantic Pyramid for Image Generation (Assaf Shocher, Yossi Gandelsmam, Inbar Mosseri, Michal Yarom, Michal Irani, William T. Freeman, Tali Dekel)
위 방법과 비슷한데 VGG를 사용해 semantic feature들의 pyramid를 만들어서, 그 feature들을 활용해 생성하는 방법.
뭐 조금씩 다르지만 내가 보기엔 비슷비슷들 하다. 이러한 접근에 적절한 창의성을 섞으면 해볼만한 재미있는 것들이 많을 듯 싶다.
각설하고 굳이 이런 시시콜콜한 논문 나열을 한 건 이 논문들 중 하나인 Semantic Pyramid를 한 번 적당히 돌려봤기 때문이다. 아래 이미지에서 1번 컬럼은 소스 (입력) 이미지이고 오른쪽으로 순서대로 VGG의 Stride 2 / 4 / 8 / 16 / 32 그리고 FC 7 (4096), FC 8 (1000) feature를 조건으로 줘서 생성한 결과다. 좀 디테일하고 복잡한 scene은 아직 생성이 잘 안 되는 것 같은데 특정 카테고리 (풀숲, 바다 등) 에 대해서는 나름 재미있는 결과가 나오는 듯 싶다.

#review 