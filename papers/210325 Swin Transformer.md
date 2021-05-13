https://arxiv.org/abs/2103.14030

Swin Transformer: Hierarchical Vision Transformer using Shifted Windows (Ze Liu, Yutong Lin, Yue Cao, Han Hu, Yixuan Wei, Zheng Zhang, Stephen Lin, Baining Guo)

이쪽은 좀 더 cnn스럽게 feature downsampling을 하면서 local attention을 사용. https://arxiv.org/abs/2103.12731 처럼 local window의 context를 섞어주기 위해 이쪽은 feature map을 몇 칸 밀어버리는 방법을 채택. roll에 mask만 씌워주면 쉽게 구현할 수 있을 듯. HTC++를 끼얹어서 mAP 58! 우왕!

[[210323 Scaling Local Self-Attention for Parameter Efficient Visual Backbones]]

#vision_transformer #local_attention 