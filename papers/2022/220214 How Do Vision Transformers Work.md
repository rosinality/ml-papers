https://arxiv.org/abs/2202.06709

How Do Vision Transformers Work? (Namuk Park, Songkuk Kim)

이거 제가 소개를 했었던가요? vit와 cnn의 차이.

1. vit의 loss landscape가 더 평탄하지만 더 non-convex하다. locality가 주입되면 더 convex해진다.
2. self attention은 loss pass filter이고 conv는 high pass filter. 따라서 self attention이 더 shape를 선호하고 conv가 더 texture를 선호한다.

self attention과 conv를 어떻게 조합하는 것이 좋을까? self attention은 끝 단계 레이어에 추가하는 것이 좋다. conv와 번갈아가면서 self attention을 사용하는데 self attention 사용으로 성능이 향상되지 않으면 이전 resolution 단계에 self attention을 추가해보는 식. 

#vit #cnn 