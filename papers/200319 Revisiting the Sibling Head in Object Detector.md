https://arxiv.org/abs/2003.07540
Revisiting the Sibling Head in Object Detector (Guanglu Song, Yu Liu, Xiaogang Wang)
디텍터에서 box regressor와 classifier가 같은 헤드와 같은 공간적 위치를 공유하는 것이 병목이라는 문제의식에서 출발한 연구. 박스의 크기와 위치를 예측하는 것에 도움이 되는 feature의 위치와 객체를 분류하는데 도움이 되는 feature의 위치는 당연히 다를 수 있다.
방법은 일단 기존 방식대로 헤드를 만들되, 그 헤드에서 box regressor를 위한 프로포절과 classifier를 위한 프로포절의 오프셋을 각각 예측해서 deformable roi pooling으로 feature를 끌어오고, 다시 (분리된) box regress 헤드와 classifier 헤드를 사용해서 박스 예측과 객체 분류를 수행하는 것.
결과적으로 3 mAP 정도의 상승이 나타났다. DCN이 보통 2 mAP 정도 상승한다는 것을 고려하면 엄청난 결과라고 할 수 있겠다.
SABL 같은 요즘 나오는 boundary aware 방법들이나 Cascade R-CNN 같은 방법들, 그리고 DCN 자체와도 겹치는 부분이나 공통된 부분이 좀 있는 것 같아서 고려해볼 부분이 좀 있을 것 같지만, 어쨌든 흥미로운 결과.
저자들이 이 방법을 사용해서 OpenImage 2019 챌린지 1위를 달성했는데 그에 대한 리포트도 있다: https://arxiv.org/abs/2003.07557