https://arxiv.org/abs/2109.14279

Localizing Objects with Self-Supervised Transformers and no Labels (Oriane Siméoni, Gilles Puy, Huy V. Vo, Simon Roburin, Spyros Gidaris, Andrei Bursuc, Patrick Pérez, Renaud Marlet, Jean Ponce)

dino를 써서 unsupervised object detection. dino가 segmentation map을 잘 뽑아주기 때문에 적절한 처리로 적절한 salient object detection을 수행하는 것이 가능하겠죠. 이렇게 추출한 salient object box를 사용해서 object detection 모델을 학습했을 때에도 multiple object detection이 가능한 덕에 unsupervised object detection까지 넘어갈 수 있었네요.

이쪽 문제가 어느 정도 성능이 나와야 잘 나오는 것일지는 모르겠는데 스코어는 꽤 인상적이군요.

여하간 이런 도구들 덕분에 레이블이 없더라도 문제 도메인의 데이터가 많이 있으면 뭔가 해볼 수 있는 가능성이 생기긴 했습니다. 다만 현실의 문제들은 레이블만 없는 게 아니라 데이터 자체가 없는 경우가 많은 것 같네요.

#self_supervised #self_supervised_discovery #object_detection #salient_object_detection 