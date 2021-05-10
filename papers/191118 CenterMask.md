https://arxiv.org/abs/1911.06667
비단 모바일 환경이 아니더라도 더 빠르고 더 강력한 모델은 매력적이다. 비전 문제에서는 상당한 시간이 백본에서 소요되는 만큼 더 효율적인 백본은 효율적인 모델을 위한 중요한 요소라고 할 수 있겠다.
올해 초 정도에 vovnet, selecsls, hardnet 같은 효율성을 중시한 모델들이 공개됐다. 흥미로운 것은 dense connectivity에 기반한 모델들이고 flops보다 실제 gpu에서 inference하는 속도 개선에 중점을 둔 모델들이라는 것.
이 중에서 vovnet을 꽤 괜찮게 써보고 있다. resnet-50 정도의 속도에 resnet-101에 준하거나 그 이상의 성능을 보여준다.
그렇다면 그 다음 단계로 resnet-101 수준의 속도에 resnext-101 수준의 성능을 얻을 수 있지 않을까 하는 생각을 했었는데...마침 vovnet v2에서 비슷한 결과가 나온 듯 하다.
주요한 변경점은 skip connection의 추가와 개선된 se 모듈의 사용. skip connection은 공개된 코드에는 이미 추가되어 있기는 했다.
개선된 se 모듈은 se가 object detection에서는 도움이 되지 않을 수 있다는 보고(https://arxiv.org/abs/1904.09925)가 있었던 것을 고려하면 흥미로운 개선이라고 할 수 있겠다. 다만 se 이후 수많은 모듈들이 제안됐기 때문에 그 모듈들과의 비교를 해보는 것이 실용적인 목적에서 필요하긴 할 듯 하다.
사실 instance segmentation 논문인데 백본 이야기만 한 것 같긴 한데, fcos라는 강력한 anchor free object detection 모델의 instance segmentation으로의 확장도 재미있는 결과다.

#object_detection #instance_segmentation #backbone #1stage 