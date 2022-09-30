https://arxiv.org/abs/2208.02515

Fine-Grained Semantically Aligned Vision-Language Pre-Training (Juncheng Li, Xin He, Longhui Wei, Long Qian, Linchao Zhu, Lingxi Xie, Yueting Zhuang, Qi Tian, Siliang Tang)

clip처럼 이미지 레벨로 contrastive learning을 하면 이미지 내의 세부적은 구조를 놓치게 되니 이미지 내의 세부적인 영역을 활용하도록 하자는 아이디어. 텍스트는 constituency parser로 pharse들을 추출하는데 이미지에서 영역을 추출하는 방식이 정교하네요.

shapely value와 shapely interaction을 사용하는데 shapely value는 이미지-텍스트 매칭에 대한 기여도를 측정하는 것이라고 한다면 shapely interaction은 여러 패치 영역의 단위로 이미지-텍스트 매칭에 대한 기여도를 측정하는 것이라고 할 수 있습니다. 예를 들어 같은 객체에 대한 패치들이라면 서로 같이 움직일 때 기여도가 높다는 형태의 아이디어네요. 이걸 사용해서 이미지에서 영역을 추출하도록 만듭니다. 다만 여기서 발생하는 loss가 bbox prediction에 어떻게 이어지는지는...논문만으로는 좀 애매하네요.

전반적으로는 region annotation free visual grounding 같다는 생각도 들고 그렇습니다.

#contrastive_learning #vision-language