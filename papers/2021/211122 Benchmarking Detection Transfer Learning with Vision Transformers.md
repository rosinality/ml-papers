https://arxiv.org/abs/2111.11429

Benchmarking Detection Transfer Learning with Vision Transformers (Yanghao Li, Saining Xie, Xinlei Chen, Piotr Dollar, Kaiming He, Ross Girshick)

mae에 나왔던 vit로 object detection을 수행하는 레시피군요. 역시 그냥 하는 건 실용적이지 않으니 window self attention을 사용하고 fpn을 붙였네요.

주제는 오히려 vit로 object detection을 하는 것 자체가 좋더라보다도 mask prediction 기반 방법(beit, mae)들이 object detection에 transfer 됐을 때 supervised pretraining이나 moco 같은 contrastive pretraining에 비해서 성능이 좋더라는 쪽입니다. 그리고 모델 크기가 커지는 것에 따라 성능의 향상폭이 더 크다는 것도 발견했네요.

mask prediction 기반 방법이 기본적으로 locality에 도움이 될 수 있으니 image level contrastive learning과 바로 비교하는 것은 약간 반칙이 아닌가 싶기도 한데...어쨌든 contrastive learning이라는 흐름에는 영향이 꽤 있겠네요. mask prediction이 훨씬 straightforward한 방식이니까요.

#unsupervised_training #object_detection #vit