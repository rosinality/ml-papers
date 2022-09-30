https://arxiv.org/abs/2205.13543

Revealing the Dark Secrets of Masked Image Modeling (Zhenda Xie, Zigang Geng, Jingcheng Hu, Zheng Zhang, Han Hu, Yue Cao)

supervised training / contrastive learning으로 학습된 vit는 상위 레이어로 갈수록 attention head들이 서로 유사해져서, 결과적으로 global한 관계를 모델링하고 더 넓은 영역을 커버하도록 학습됨. 그런데 masked image model로 학습된 vit는 상위 레이어에서도 attention head들이 diverse하고, global한 관계 뿐만 아니라 local한 관계, local한 영역을 커버하는 head들이 존재. 이 diversity와 locality가 downstream task에서 finetuning을 하는 과정에 도움이 된다는 설명. 그래서 반대로 supervised training을 한 경우에는 파인튜닝 시점에는 상위 레이어 weight는 쓰지 않는 것이 더 나은 패턴이 나타남.

아예 locality 제약이 걸린 attention을 사용하는 케이스에는 어떨지가 흥미로운 부분이네요.

#self_supervised #representation 