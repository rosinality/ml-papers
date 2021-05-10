[https://arxiv.org/abs/1911.09737](https://l.facebook.com/l.php?u=https%3A%2F%2Farxiv.org%2Fabs%2F1911.09737%3Ffbclid%3DIwAR02PN-e9TXQUF5drZDbInO_FmOmuLYLu6HFzBdxndamgkoM_d4AGXJPJ60&h=AT3fSGGrBOCuF3Sxdt9glG0dAQLOnG0XhuRIaACK3dSk7tTmKHjX3zRRJvUPS7rdSQgrBsayFXTT3L6hY02RE52MhXN-LIpX28feGag9tgpe64BtYjj4Qqb5xSL-9NYbzNoD&__tn__=-UK-R&c[0]=AT3N7PTHTIcCEJ05Nkpka0-wAWTiPT5u72yEQvO3-B3_Nn3b8-McT7G3sO6Fio7xxG0KpjT4xlVOEKbzRWOa7fI8So1FFW7D2FbP5y2WyuknYwGFkabe2eFLRaxhpcnYXFuycRsBv9C7Se41x8NP37fv0g)

나온지는 좀 됐는데 이제 화제에 오르고 있는 것 같아서 잠깐 써보고 싶어졌다.

batch normalization은 굳이 말을 얹을 필요도 없을 정도로 강력한 도구다. 하나의 모듈이 트레이닝 과정의 안정화, 트레이닝 속도 향상, 거기에 regularization 효과까지 같이 보여주기는 어렵다.

다만 batch normalization은 모델 학습 과정이 배치 크기에 더 직접적인 영향을 받게 만들기 때문에 상당히 귀찮은 문제들을 야기한다. 적절하게 배치 통계를 계산하지 않으면 추론 과정에서 상당한 문제를 발생시키고. 배치 크기가 충분히 확보되지 않으면 (보통 16 이상) 모델의 성능에 적지 않은 악영향을 끼친다. 뒤의 문제가 배치 크기를 확보하기 어려운 object detection 같은 문제에서는 백본의 batch norm을 고정하고 위에 추가한 head에는 normalization을 사용하지 않는 방법이 베이스라인이 되어있다.

그래도 워낙 강력한 모듈이다보니 synchronized batch norm이나 inplace abn 같은 대응 방법들이 개발되기도 했다.

좀 더 직접적으로 이 문제를 해소하기 위한 방법들도 batch norm 이후 등장했다. batch renormalization 같은 방법이 시작이라고 할 수 있겠고, group normalization, fixup initialization, weight standardization 같이 배치 통계에 의존하지 않는 방법이나 switchable normalization 같이 각종 normalization을 섞어버리는 방법들이 등장했다.

실제로 group normalization, 그리고 group normalization + weight standardization 같은 방법들은 object detection에서 괜찮은 결과를 보여주고 있다.

이 논문에서 제안하는 filter response normalization은 이 문제에 대해 기존의 방법보다 더 단순한 방법을 제안하고 있다. 형태는 mean centering이 없는 instance norm이라고 생각할 수 있겠다. 배치 통계에 의존하지 않는 방법에서 mean centering이 굳이 필요하지 않다는 것이다. 대신 mean centering을 뺀 결과 output이 0에서 크게 벗어나는 bias를 가질 수 있으므로 학습 가능한 threshold를 갖는 TLU라는 activation을 같이 도입했다.

결과적으로는 imagenet classification과 coco object detection에서 batch norm과 group norm보다 나은 성능을 보여주고 있다. 기존의 normalization 방법과는 다르게 fully connected layer에 적용해본 결과도 있는데 이것도 꽤 흥미롭다.

train/valid 커브를 보면 group norm/weight standardization과 비슷하게 트레이닝이 더 잘 되고 그만큼 validation accuracy가 상승하는 형태를 보여주고 있다. 아무래도 배치 통계를 쓰지 않으니 노이즈에 의한 regularization 효과가 약하다는 의미일 수 있는데 적절한 regularization과 결합했을 때의 결과도 의미있는 튜닝 시도가 될 수 있을 것 같다. weight standardization을 결합하는 것도 가능할 듯 한데 같이 사용했을 때의 결과도 흥미로울 듯 싶다.