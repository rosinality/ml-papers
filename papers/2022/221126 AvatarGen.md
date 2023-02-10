https://arxiv.org/abs/2211.14589

AvatarGen: A 3D Generative Model for Animatable Human Avatars (Jianfeng Zhang, Zihang Jiang, Dingdong Yang, Hongyi Xu, Yichun Shi, Guoxian Song, Zhongcong Xu, Xinchao Wang, Jiashi Feng)

human avatar generation은 늘 2010년 정도의 게임 그래픽 같은 것이 나오는 것 같다는 생각을 합니다만 이 모델은 좀 흥미롭네요. smpl을 기반으로 해서 template smpl로 변환한 다음 이 template에서 eg3d처럼 tri-plane을 만들고, 실제 smpl에 대해 sdf를 만들어서 이 sdf를 사용해 volumetric rendering을 하는 방식으로 아바타 생성을 했네요.

#3d_generative_model 