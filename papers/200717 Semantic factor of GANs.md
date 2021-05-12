gan에서 semantic한 의미를 찾는 latent space의 factor를 추출하기.
gan이 압도적인 샘플들을 뽑아낸지는 꽤 됐다. 이걸로도 충분히 재미있고 어딘가 쓸모도 있긴 하지만 (예를 들면 이런 것? https://waifulabs.com/) 역시 부족함이 있다. 샘플의 확률 추정 같은 근사한 것은 좀 제쳐놓고 생각하면 주요한 이슈는 두 가지가 있을 것 같다. 하나는 이미지를 latent space로 매핑하는 것. 몇 번인가 이야기했지만 상당히 어려운 문제다. 데이터셋의 문제도 있고 모델의 문제도 있고 학습 과정의 문제도 있고 매핑하는 프로세스의 문제도 있고. 이게 잘 안 되니까 최근 PULSE(https://arxiv.org/abs/2003.03808)로 흑인 사진을 넣었더니 백인이 나오더라 같은 사건이 터진다.
둘째는 latent vector를 적당히 변환해서 이미지를 의미있는 방향으로 변환하는 것. 이 문제에 대해서 최근 흥미로운 진전들이 몇 있었다. 처음으로 소개해볼만한 것은 이것:
Unsupervised Discovery of Interpretable Directions in the GAN Latent Space (https://arxiv.org/abs/2002.03754)
아이디어를 요약하면 이렇다. 벡터 v와 스칼라 s를 하나 뽑고 행렬 A를 사용해 Asv로 변환시킨다. 그리고 latent/noise vector z에 이걸 더해서 (z + Asv) generator에 입력해준다. generator로 생성된 이미지를 추가적인 모델(reconstructor)에 입력해서 v와 s를 예측하게 만든다. 그리고 A 또한 이 reconstructor에 대한 loss를 최소화하도록 학습시킨다. 그렇다면 A가 이미지 상에서 가장 변화를 포착하기 쉬운 방향으로 z에 perturbation을 주도록 학습되지 않을까가 핵심 아이디어다. 여기서 변화를 포착하기 가장 쉬운 방향이 latent space에서 의미있는 semantic factor라는 가정이 핵심이라고 할 수 있겠다. 아래 논문들도 이를 공유한다고 볼 수 있다.
그 다음은 요것:
GANSpace: Discovering Interpretable GAN Controls (https://arxiv.org/abs/2004.02546)
여기는 좀 더 과격한 아이디어를 사용한다. latent space에서 의미있는 방향은 결국 (noise input에서 매핑된) latent/activation vector의 principal component가 아닐까? 그렇다면 noise 샘플을 여럿 뽑아서 latent vector로 매핑한 다음 이 샘플에 대해 pca를 돌리면 이 component들을 찾을 수 있다. 방법이 더 간단해졌다!
여기서 방법이 다시 한 번 더 단순해진다:
Closed-Form Factorization of Latent Semantics in GANs (https://arxiv.org/abs/2007.06600)
위 두 논문의 핵심은 즉 latent space가 크게 변화하는 방향을 찾는다에 있는 것이 아닐까? noise가 fc 레이어 W에 의해 latent vector로 변환된다고 가정해보자. 그렇다면 A(z + v) - A(z)를 최대화하는 v를 찾는 문제라고 생각할 수 있겠다. 그렇다면 ||Av||를 최대화하는 v를 찾는 문제가 된다. 적당한 제약을 주면 이 AᵀA의 eigenvector를 찾는 문제가 된다.
AᵀA의 eigenvector야 SVD 한 방이면 되고 A는 여러분의 모델 체크포인트에 들어있으니 그대로 불러오면 끝. 산뜻하다!
그런데 뭐 이번 주 논문 정리에 한 번 써놓고 다시 이렇게 정리해서 올리는 건...그냥 마음에 들어서 한 번 만들어서 결과를 뽑아봤기 때문이다. 이 방법으로 찾은 체형, 인종, 성별, 포즈 요인이다.

#review