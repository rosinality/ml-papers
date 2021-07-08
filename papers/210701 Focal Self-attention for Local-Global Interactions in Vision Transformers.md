https://arxiv.org/abs/2107.00641

Focal Self-attention for Local-Global Interactions in Vision Transformers (Jianwei Yang, Chunyuan Li, Pengchuan Zhang, Xiyang Dai, Bin Xiao, Lu Yuan, Jianfeng Gao)

halo attention [[210323 Scaling Local Self-Attention for Parameter Efficient Visual Backbones]]과 비슷하게 window 근방을 aggregation하는 local attention vit. 이쪽은 이 과정에서 multiscale하게 구성했다는 점이 차이가 있네요. swin을 제치고 58.7 box mAP, 50.9 mask mAP라는 무시무시한 결과를 찍었습니다.

F.unfold를 사용하는 게 가장 직관적인 구현 방법이긴 한데 아무래도 이쪽은 비효율적이죠. 저자에게 물어봤더니 roll을 사용해서 구현했다고 하네요. 코드가 공개되면 테스트해볼만한 가치가 있겠습니다.

#vit #local_attention