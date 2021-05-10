fcos 이야기가 나오니 anchor free object detection에 대해서 잠깐 써보고 싶어졌다.
faster r-cnn 이후 앵커를 사용하는 방법이 object detection의 주류라고 할 수 있겠다. 덕분에(?) object detection에 대한 튜토리얼들을 보면 상당한 분량을 앵커에 대해 설명하는 것에 사용하고 있다. 실제 구현에서도 적지 않은 양의 코드가 앵커를 구현하는데 사용된다.
그런데 앵커가 반드시 필요한 걸까?
이전에도 yolo나 densebox 같이 앵커를 사용하지 않는 방법들이 제안됐었다. 그러다 faster r-cnn과 mask r-cnn의 성공으로 잠깐 밀려났다가, 2018년 말 ~ 2019년 초에 anchor free object detection 연구들이 여럿 등장했다.
이 방법들은 크게 두 가지로 나눠볼 수 있겠다. 하나는 박스를 바로 regress하는 방법들이고 fcos, foveabox, centernet (object as points), reppoints가 여기 속한다. 다른 하나는 키포인트를 사용하고 키포인트를 그룹화해서 박스를 찾아내는 방법으로 cornernet, extremenet, centernet (keypoint triplet)이 여기 속한다.
박스를 바로 regress하는 방법들은 어디서 아이디어를 공유했나 싶을 정도로 흡사한 부분이 많고 또 나온 시점도 비슷하다. 공통적으로 박스 중앙 근처 영역을 샘플링하고 그 지점에서 박스 좌표를 예측하는 방법이다. foveabox는 박스를 축소한 영역에서, centernet은 박스 중앙의 키포인트에서 좌표를 예측하고 reppoints는 중앙 근처에 포인트들을 할당한다. fcos는 박스 전체 영역에서 좌표를 예측하고 centerness라는 중앙에 얼마나 가까운가에 대한 맵을 추가로 예측하는 방식이었지만 이후 개선된 버전에서는 중앙 근처의 지점에서 예측하도록 할당하는 식으로 바뀌었다.
키포인트 기반 방법은 cornernet에서는 의도적으로 중앙 대신 좌상단과 우하단에 키포인트를 찍고 각 키포인트에서 키포인트들에 대한 차이/거리를 부여해서 키포인트를 그룹화하는 방식을 취했지만 이후 extremenet이나 centernet에서는 중앙 부분의 키포인트를 예측해서 박스 추출에 활용하는 식으로 변형되었다.
결론적으로 이 방법들은 다들 박스의 중앙점을 중요하게 활용하고, 이전에도 관찰되었던 것이지만 박스의 regress보다 이 중앙점을 찾는 것이 더 어려운 것으로 나타난다.
어쨌든 이 방법들은 다들 coco에서 mAP 40 이상을 달성했다. 서두의 질문에 답하자면 앵커 없이도 coco에서는 스코어가 잘 나올 수 있다고 할 수 있겠다.
요즘은 panoptic segmentation이 흥미로운 문제로 부상하면서 segmentation에 중점을 둔 방법들도 나오고 있는데...이건 문제 자체가 많이 다르긴 하다. 그런데 panoptic segmentation에서도 물체의 중앙이 중요하게 등장하기도 한다. 예를 들어 panoptic deeplab 같은 접근에서는 물체의 무게중심에 키포인트 히트맵을 잡고 물체 영역에서 키포인트와의 거리를 예측하는 접근을 쓴다.
여튼 중앙이 중요하다.

#object_detection 