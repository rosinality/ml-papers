https://arxiv.org/abs/2201.02609

Generalized Category Discovery (Sagar Vaze, Kai Han, Andrea Vedaldi, Andrew Zisserman)

unlabelled 데이터셋에 labeled 데이터셋의 카테고리에 해당하는 이미지도 있고 새로운 카테고리의 이미지도 섞여 있을 때 unlabelled 데이터셋을 분류하는 문제. labelled 데이터에 대해서는 supervised contrastive, unlabelled 데이터에 대해서는 self supervised contrastive learning으로 representation learning을 한 다음 linear classifier를 쓰는 대신 semi supervised k-means로 클러스터링을 해서 분류하는 방법을 썼네요. unlabelled 데이터 또한 학습 과정에는 사용할 수 있어야 한다는 제약이 붙긴 합니다.

가장 간단한 과제인 classification도 현실에서 쓰려면 할 게 참 많습니다.

#classificiation #open_set_recognition 