https://arxiv.org/abs/2107.06278

Per-Pixel Classification is Not All You Need for Semantic Segmentation (Bowen Cheng, Alexander G. Schwing, Alexander Kirillov)

semantic segmentation을 instance segmentation처럼 풀 수는 없는 것인가라는 질문. 따라서 semantic segmentation, instance segmentation, panoptic segmentation 세 segmentation 과제에 대한 대통합 모델이 됩니다.

물론 그렇다고 bounding box를 도입하는 것은 잘 맞지 않고, detr 파워를 빌려 instance별 임베딩을 뽑아 마스크를 만드는 방식으로 해결. swin까지 붙여놓으니 벤치마크를 막 뒤집어놨네요.

#instance_segmentation #panoptic_segmentation #semantic_segmentation #detr 