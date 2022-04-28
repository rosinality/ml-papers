https://arxiv.org/abs/2112.09747

A Simple Single-Scale Vision Transformer for Object Localization and Instance Segmentation (Wuyang Chen, Xianzhi Du, Fan Yang, Lucas Beyer, Xiaohua Zhai, Tsung-Yi Lin, Huizhong Chen, Jing Li, Xiaodan Song, Zhangyang Wang, Denny Zhou)

vit에서 multiscale 구조는 딱히 필요하지 않고 single scale로 레이어를 쭉 쌓아도 좋다는 결과. 다만 연산이 비효율적이니 window attention을 활용하는데 이 window 크기를 점진적으로 키우는 구조는 고려해봤네요. 다 좋은데 이 window attention이 overlapping window 기반이라...이걸 구현하는 게 문제긴 하네요. single scale swin 같은 구조가 가능할까 싶기도 한데요.

#vit #multiscale 