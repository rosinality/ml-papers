# 210508 최근 논문들에 대한 생각

mixer (https://arxiv.org/abs/2105.01601)가 나오자마자 mlp로 classification을 태클해보겠다는 아이디어가 쭈루룩 나왔다. transformer로 해보겠다는 사람들이 한둘이 아니었던 것처럼 mlp로 해보겠다는 사람들도 한둘이 아니었던 것으로.

RepMLP: Re-parameterizing Convolutions into Fully-connected Layers for Image Recognition

https://arxiv.org/abs/2105.01883

repvgg를 만들었던 양반들이라 그런지 학습시에는 conv를 병렬로 붙여놓고 추론시에 fc로 밀어넣는 작업을 함.

Do You Even Need Attention? A Stack of Feed-Forward Layers Does Surprisingly Well on ImageNet

https://arxiv.org/abs/2105.02723

luke melas의 mixer와 거의 완전히 똑같은 mlp 기반 image classification.

denoising diffusion은 이제 generative modeling이 필요한 종류의 과제들에 충분히 사용할 수 있는 도구로 부상하고 있지 않나 싶다. 요즘 이거 때문에 jax에도 관심이 많이 감. (https://github.com/yang-song/score_sde)

SRDiff: Single Image Super-Resolution with Diffusion Probabilistic Models

https://arxiv.org/abs/2104.14951

DiffSinger: Diffusion Acoustic Model for Singing Voice Synthesis

https://arxiv.org/abs/2105.02446

denoising diffusion 기반 singing voice synthesis. 요즘 singing voice synthesis가 어느 정도 되나 들어볼만. https://diffsinger.github.io/

detr (https://arxiv.org/abs/2005.12872) 이후로 end2end detection을 채택하거나 혹은 그 기반 아이디어를 차용하는 것은 자연스러운 접근이 됐다. 물론 object detection만으로는 재미 없으니 instance segmentation으로 넘어가주는 것이 자연스러운 흐름.

QueryInst: Parallelly Supervised Mask Query for Instance Segmentation

https://arxiv.org/abs/2105.01928

learned proposal을 쓰는 sparse r-cnn에 dynamic conv로 mask head를 붙여준 형태의 instance segmentation.

ISTR: End-to-End Instance Segmentation with Transformers

https://arxiv.org/abs/2105.00637

end2end instance segmentation. end2end라기엔 뭔가 많이 붙은 것 같은데? (end2end 단속반) 농담이고, matching을 위해 mask를 dimension reduction 한 것과 learnable query box를 기반으로 시작한다는 것이 특징.

요즘 보면 정말로 all you need인 것은 positional encoding이 아닌가 싶다.

ACORN: Adaptive Coordinate Networks for Neural Scene Representation

https://arxiv.org/abs/2105.02788

전체 공간을 block들로 쪼갠 다음 각 block의 id를 입력으로 받아 그 block 내의 local coordinate에 대한 feature로 매핑하는 네트워크를 사용해서 neural scene representation을 학습. 결과가 무시무시.

이번 주는 필터링한 논문이 별로 없으니 잡담을 첨부.

트랜스포머, 정확히는 어텐션을 unimodal한 시퀀스에 대한 모델링이 아니라 multimodal한 데이터를 모델링하는 과정에 사용해보고 있는데...새삼스럽지만 잠재력이 엄청난 것 같다. feature의 부분적 추출, feature의 결합, feature 내부의 모델링 모두를 어텐션을 도입해서 태클할 수 있다. 과거 이런 절차에는 정말 많은 수작업이 필요했다. object detection으로 이미지 영역을 특정해서 roialign으로 이걸 잘라내고 여기에 convolution을 얹고 이걸 다른 시퀀스와 결합하고...object detection은 object detection이라고 묶어서 그렇지 또 이 내부는 얼마나 복잡한 feature 추출과 feature에 대한 모델링 작업이 필요했던가? 이 모든 작업을 어텐션으로 태클할 수 있다. 거기에 detr에서 보여준 것처럼 헝가리안 알고리즘으로 loss 부여라는 골치아픈 작업 또한 좀 더 자동화된 방식으로 접근이 가능하다.

이 유연한 가능성 덕분에 이전 같았으면 모델의 복잡성 증가로 엄두도 내기 어려웠던 형태의 과제에 접근하는 것을 가능하게 한다. 그러니까 이전 같았으면 이렇게 저렇게 하면 가능할 것 같긴 한데 대체 엄두가 나지 않아 절로 하고 싶지 않아졌던 과제에 대해 훨씬 간결한 형태의 모델을 구상하고 실제로 구현해볼 수 있게 해준다.

물론 가능하다는 것이고 그게 잘 되는가는 별개의 문제지만. 자동화된 접근일수록 연산 효율성이나 데이터 효율성이 떨어져서 땜질을 해줘야 하기도 하고, 또 이 무거운 어텐션을 좀 가볍게 만들어주기 위한 구조들 자체가 하나의 새로운 큰 영역이 되기도 하지만.

그래서 어텐션의 힘으로 더 복잡한, 새로운 과제들을 풀 여지가 점점 더 보이는 것 같다. 아니 굳이 새로운 과제를 찾아내지 않더라도 좋다. 기존에 여러 모델들을 엮어 파이프라인을 만들었던 것을 end2end로 단축해버릴 수 있는 기회가 주어지고 있다.

GPU와 데이터가 조금만 더 있다면 (농담)



#review