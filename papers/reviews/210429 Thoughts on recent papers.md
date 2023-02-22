# 210429 최근 논문들에 대한 생각

그동인 비죤-트랜스포머 논문들이 쏟아졌는데 여기에는 안 올리고 있었네.

https://arxiv.org/abs/2104.01136 비전 트랜스포머 + 다운샘플링 한 편 더!

https://arxiv.org/abs/2104.02057 mocov3로 vit 학습시키기. 요즘 트렌드에 맞게 큐도 없애버리고 단순화. Kaiming He 선생님도 비죤- 트랜스포머를 만지기 시작하셨군요.

https://arxiv.org/abs/2104.04191 bit/vit/clip와 bn/gn에 대한 객체의 위치, 크기, 회전에 대한 robustness 평가. vit와 clip의 특성이 상당히 좋군요. conv padding 문제일까 싶기도 하고...bn과 gn도 location에 대한 robustness 패턴 차이가 크네요.

https://arxiv.org/abs/2104.10858 vit 튜닝. 메인으로 미는 개선 사항은 re-labeling을 활용한 토큰별 레이블링과 cutmix를 vit 토큰에 맞게 변형한 mixtoken, 토큰 앞에 conv 달기 정도겠네요. 흥미롭긴 한데 vit스러운 토큰 구조를 계속 가져갈 필요가 있는지는 잘 모르겠습니다.

https://arxiv.org/abs/2104.10935 와 covariance pooling이 다시 나왔군요. 원래 이거 하던 저자들이긴 합니다만...vision transformer에서 cnn 구조의 재발견을 하고 있어서 그런지 이런 것들이 다시 나오네요.

https://arxiv.org/abs/2104.11227 vit에 풀링을 끼얹으면 효율적이다 다시 한 번 더. fairscale이라서 그런지 비디오에 대해서도 했네요. 서로 통하는 아이디어가 이렇게 연달아서 나오는 것도 처음인 것 같네요.

https://arxiv.org/abs/2104.13840 local attention + window level global attention + positional encoding generator. positional encoding generator는 역시 꽤 흥미로운 접근인 것 같네요.

https://arxiv.org/abs/2104.12533 https://arxiv.org/abs/2104.13497 cnn스러운 디자인 혹은 아예 conv layer를 추가하기

https://arxiv.org/abs/2104.12753 vit의 문제가 patch embedding들이 서로 너무 비슷해진다는 것에 있다는 진단. 그래서 patch 사이의 cos sim에 loss를 걸었군요. 흥미롭습니다.

여러모로 재미있게 보고 있긴 한데...약간 아이디어가 겹친다는 감이 있어서. vit가 혁신적이었던 것은 오히려 cnn의 아이디어들을 깡그리 무시하고 nlp-퍼슨스러운 발상으로 접근했다는 점에 있지 않나 싶다. 그런 의미에서 cnn의 아이디어가 다시 도입되는 것은, 물론 효율적이기는 하지만, 약간 파격적인 느낌이 줄어들게 만든다는 것은 어쩔 수 없다.

지금까지 나온 사례 중에서 가장 흥미로운 것은 swin transformer. local attention으로 quadratic complexity를 풀면서 shifting/roll로 local attention의 문제를 우아하게 해소했다.

여전히 실용적으로는 vovnet 같은 백본을 가져오는 게 나을 것 같기도 한데, local attention의 구체적인 구현이 최적화되면 좋은 선택지가 될 듯 싶기도 하다. xla 같은 걸로 컴파일하면 좀 더 빨라지려나?

별개로 (많은 사람들이 지적하는 것처럼) 트랜스포머 혹은 self attention의 매력은 multimodal 데이터에 대한 결합을 아주 용이하게 만들어준다는 것이다. 이 가능성이 기존에 풀기 어려웠던, 혹은 풀 엄두를 내지 못했던 문제들을 태클할 수 있는 기회를 만들어주는 것 같다. 요즘 관심이 가는 응용 사례는 visual grounding, zero shot object detection 등등으로 불리는 텍스트 입력에 대해 상응하는 객체를 찾아주는 과제.

https://arxiv.org/abs/2104.00743 이미지와 텍스트 프롬프트를 넣으면 바운딩 박스도 잘라주고 텍스트로 설명도 뽑아주는 모델. 굉장히 멋짐.

https://arxiv.org/abs/2104.08541 visual grounding 풀기. vision transformer, language transformer, vision-language transformer를 조합하는 모던한 해법.

https://arxiv.org/abs/2104.12763 나온지 며칠 되어서 다들 보셨을 것 같긴 한데...이전 visual grounding들과 비슷하게 text 입력에 맞는 object를 찾아주는 모델. 핑크 코끼리를 찾아내는 게 꽤 재미있습니다. 드디어 vision-language multi modal 과제들이 뜨기 시작하는 것 같네요.

https://arxiv.org/abs/2104.13921 zero-shot object detection. 결과적으로는 텍스트 입력을 받아 object의 bbox를 찾는 모델. 이쪽은 clip을 사용했군요. clip이 생각의 제약을 많이 풀어준 모양새입니다.

그리고 눈에 띈 multimodal한 데이터를 트랜스포머로 결합해낸 사례.

https://arxiv.org/abs/2104.11896 raw point cloud + voxel + 2d birds' eye view를 결합하는 트랜스포머 3d object detection. 다양한 형태의 정보를 결합하는 장치로서의 트랜스포머의 위력을 새삼스럽게 잘 보여주는군요.

이런 의미에서 트랜스포머의 위력은 기존 과제를 더 잘 하게 해주는 것 이상으로 새로운 과제를 발견하고 풀 수 있는 기회를 제공하는 것에 있지 않을까 싶다. 물론 효율성을 개선할 수 있다면 더 좋겠지만...



#review