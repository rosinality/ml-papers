https://arxiv.org/abs/2109.04912

ReasonBERT: Pre-trained to Reason with Distant Supervision (Xiang Deng, Yu Su, Alyssa Lees, You Wu, Cong Yu, Huan Sun)

엔티티 사이의 관계를 추론할 수 있는 능력을 탑재한 bert. 프리트레이닝 시에 단순히 mlm을 하는 게 아니라, 텍스트에서 엔티티들의 페어를 찾은 다음 그 페어가 들어있는 다른 텍스트를 찾아서 추가 정보로 제공한 다음 엔티니 하나를 마스킹하고 예측하게 학습시켰습니다.

좀 흥미로운 부분은 qa 벤치마크에서 파인튜닝 데이터셋이 증가할수록 reasonbert가 다른 프리트레이닝 방법에 대해 보이는 성능 차이가 감소한다는 점이겠네요. 여러모로 qa 같은 문제에 대해 휴리스틱으로 만들어낸 weak supervision 데이터로 학습시키는 것이라고 보이기는 합니다.

#bert #pretraining #reasoning #qa