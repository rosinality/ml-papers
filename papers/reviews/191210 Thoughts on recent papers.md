# 191210 최근 논문들에 대한 생각

최근에 object detection에서 재미있는 결과들이 좀 있었다. EfficientDet도 그렇고 이번에는 COCO 2019 챌린지 우승 모델 (https://arxiv.org/abs/1912.04260) 논문도 나왔다. Appendix A에 모델 성능 개선을 어떻게 했는지에 대한 결과들이 나와있는데 특히 COCO 2018 챌린지에서 사용한 모델 (https://www.dropbox.com/.../xwvurvj.../COCO2018_MMDet.pdf...) 과 비교해보면 재미있다.

또 눈에 띄었던 논문이 있어서 적어보려고 한다.

1. Bridging the Gap Between Anchor-based and Anchor-free Detection via Adaptive Training Sample Selection https://arxiv.org/abs/1912.02424

올해 anchor free detector들이 여럿 등장했는데, 흥미로운 것은 anchor free일 뿐만 아니라 성능이 anchor based detector보다 더 좋은 경우가 많았다는 것이다. 왜 그런가를 분석하기 위해 이 논문에서는 anchor free detector인 fcos에 추가되어 있는 모델 측면의 개선들을 retinanet에 옮겨보는 실험을 했다. 그랬더니 차이는 0.8 mAP 정도로 줄어들었다.

큰 차이가 없으니 거의 동등하다고 생각할 수 있겠지만 1 mAP 1 mAP가 중요한 object detection이다보니...이 차이가 어디서 왔는지를 더 분석했다. 저자들이 주목한 건 이 두 모델이 positive/negative sample을 나누는 기준이 다르다는 것. retinanet은 각 스케일의 앵커들과 gt 박스와의 overlap으로 positive/negative를 나누지만 fcos는 일단 gt 박스 내에 있는 점들을 positive로 선정한 다음 스케일에 따라 positive를 걸러내는 접근이다. 이 차이를 없애니 성능 차이가 거의 사라진다는 것이 나타났다.

여기서 더 나아가 positive sample을 정하는 개선된 기준을 제안한다. gt 박스의 중심과 중심이 가장 가까운 앵커들을 선정한 다음 그 앵커들의 iou의 평균과 표준편차를 구해서 그걸로 iou의 역치를 정한다. freeanchor 같은 접근을 생각하면 될 것 같다.

보고된 결과를 보면 대략 1 mAP 정도의 성능 향상이 있는 듯 하다. 장점은 학습 중에 사용하는 positive/negative의 기준을 변화시키는 것이기 때문에 추론 시점에서는 속도에 미치는 영향이 없다는 것.

2. Multiple Anchor Learning for Visual Object Detection https://arxiv.org/abs/1912.02252

이쪽은 더 freeanchor를 연상시키는 접근이다. 애초에 freeanchor와 저자가 한 명 겹친다...

아이디어는 앵커 기반 접근에서는 보통 gt 박스와 앵커의 iou로 앵커들을 고른 다음 그 앵커들에 대해서 classification과 localization을 학습하는데, 이렇게 선정한 앵커가 이 두 과제를 학습하기에 최적이라는 보장이 없다는 발상에서 시작한다. 그렇다면 classification과 localization 스코어를 가지고 앵커를 선정하면 되지 않을까? 학습 초반부터 스코어를 가지고 앵커의 수를 줄이고 시작하는 건 무리가 따르니 학습 과정에서 선정된 앵커의 수를 줄여나가는 것이 좋겠다. 이 부분은 freeanchor와 공통이다.

이 논문에서는 추가적으로 스코어를 가지고 앵커를 선정하다 보면 썩 좋지 않은 앵커에 대해서 반복적으로 학습될 수 있으니 스코어가 높은 앵커들을 억제해서 perturbation을 주는 과정이 추가됐다.

이 두 접근의 핵심이 positive 샘플을 어떻게 선정할 것인가에 있다는 것은 공통점이 있다고 할 수 있겠다. 아이디어를 조합할 수 있는 방법들이 몇 가지 있을 텐데 그것도 흥미로운 실험이 될 듯 싶다.



#review