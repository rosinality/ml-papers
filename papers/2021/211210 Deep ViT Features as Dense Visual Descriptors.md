https://arxiv.org/abs/2112.05814

Deep ViT Features as Dense Visual Descriptors (Shir Amir, Yossi Gandelsman, Shai Bagon, Tali Dekel)

self-supervised vit (dino)가 생성하는 feature의 특이한 특성. 단순히 개별 클래스의 semantic한 파트들을 검출하는 것이 아니라 여러 클래스에 걸쳐 공통된 파트들을 검출하는 특징이 있네요. 따라서 여러 이미지들이 주어졌을 때 공통된 파트들을 segmentation 하는 것(co-segmentation)이 가능해집니다. 예를 들어 서로 다른 동물들의 공통된 부위들을 찾아낸다거나 하는 것이 가능하네요. 재미있습니다. 저도 문서 이미지들을 dino에 돌려봤을 때 파트를 분할하는 것까지는 봤었는데...좀 다른 클래스의 이미지들에 대해 비교해볼 걸 그랬나 싶기도 하네요.

dino objective 말고 다른 self supervision object에 대해서는 어떨지 궁금하네요. mask prediction 같은?

https://dino-vit-features.github.io/

#vit #self_supervised #semantic_segmentation 