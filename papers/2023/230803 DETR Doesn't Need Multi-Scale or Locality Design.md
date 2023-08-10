https://arxiv.org/abs/2308.01904

DETR Doesn't Need Multi-Scale or Locality Design (Yutong Lin, Yuhui Yuan, Zheng Zhang, Chen Li, Nanning Zheng, Han Hu)

오랜만에 detr이라는 이름을 보니 반갑네요. multiscale architecture 없이 plain detr로 성능을 끌어올리는 작업을 했습니다. attention에 box query와의 relative position 차이에 대한 bias를 주는 것과 mim pretraining이 핵심이군요. 사실 multiscale이 반드시 필요한 것은 아니라는 것은 object detection 쪽에 좀 알려져 있었던 부분이니 그 연장선상에서 볼 수도 있지 않을까 싶습니다.

#detr #multiscale 