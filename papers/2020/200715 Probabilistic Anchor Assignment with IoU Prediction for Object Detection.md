https://arxiv.org/abs/2007.08103

Probabilistic Anchor Assignment with IoU Prediction for Object Detection (Kang Kim, Hee Seok Lee)

앵커 부여 문제. 확률적이고, 모델의 학습 과정에 adaptive하고 특별한 threshold가 없는 방법을 추구. cls/loc loss를 사용해 앵커에 스코어를 부여하고 그 스코어들에 gmm(!)을 피팅해서 pos/neg를 분리함. 앵커 부여가 이렇게 어렵습니다. #object_detection #anchor #1stage