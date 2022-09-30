https://arxiv.org/abs/2206.07643

Coarse-to-Fine Vision-Language Pre-training with Fusion in the Backbone (Zi-Yi Dou, Aishwarya Kamath, Zhe Gan, Pengchuan Zhang, Jianfeng Wang, Linjie Li, Zicheng Liu, Ce Liu, Yann LeCun, Nanyun Peng, Jianfeng Gao, Lijuan Wang)

vision language model에 localization 끼얹기. glip과 비슷한 목표라고 할 수도 있겠네요. 단 localization은 이미지 크기가 커야할 필요가 있기 때문에 학습이 부담스럽고, 그래서 한 번에 같이 학습하기보단 contrastive learning/mlm 같은 objective로 한 번 학습한 다음(coarse) localization을 다시 학습시키는 방법을 씁니다. cross attention 모듈을 optional 하게 만들어서 retrieval에도 쓸 수 있게 만들었습니다.

localization이 추가되고 있는 것을 보면 vision-language에서 이쪽을 고려하는 것도 필요하겠다 싶네요.

#vision-language 