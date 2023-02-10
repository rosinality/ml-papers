https://arxiv.org/abs/2211.06220

OneFormer: One Transformer to Rule Universal Image Segmentation (Jitesh Jain, Jiachen Li, MangTik Chiu, Ali Hassani, Nikita Orlov, Humphrey Shi)

semantic segmentation, instance segmentation, panoptic segmentation 데이터셋을 동시에 학습하는 단일 모델로 sota 달성. 각 segmentation을 지시하는 task token을 복사한 다음 1/4 stride feature로 업데이트해 N-1개 쿼리를 만들고, 이 쿼리와 object label을 쭉 나열한 텍스트 시퀀스와의 contrastive loss를 사용 & 쿼리와 feature map의 결합으로 마스크 생성. 꽤 복잡하긴 한데 흥미롭군요.

#semantic_segmentation #instance_segmentation #panoptic_segmentation #detr 