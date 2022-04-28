https://arxiv.org/abs/2110.08130

Breaking Down Multilingual Machine Translation (Ting-Rui Chiang, Yi-Pei Chen, Yi-Ting Yeh, Graham Neubig)

multilingual mt로 학습시킨 weight가 어떻게 다른 언어 pair에 대해서 transfer 될 수 있는지 분석. 인코더는 multilingual training으로 학습시켰을 때 부스트가 있는 반면 디코더는 도움이 되지 않는 것 같다는 분석이네요. 서로 다른 언어를 디코딩하는 작업에 parameter sharing을 하기가 어려운 것 같다는 추정.

그러고나서 어텐션 헤드의 importance score를 계산한 다음 이 importance score의 correlation을 가지고 유사 언어 그룹을 묶어 파인튜닝 하는 것으로 성능 부스트를 얻을 수 있다는 결과네요.

#nmt #multilingual 