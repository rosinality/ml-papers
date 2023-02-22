https://arxiv.org/abs/2302.09650

Scaling Laws for Multilingual Neural Machine Translation (Patrick Fernandes, Behrooz Ghorbani, Xavier Garcia, Markus Freitag, Orhan Firat)

scaling law 논문은 많이 나왔지만 multitask나 multilingual로 가면 좀 흥미로워지네요. NMT에서 학습시 각 언어의 가중치 비율과 scaling이 무관하게 움직인다는 것, 즉 모델이 커지면 가중치와는 관계 없이 일정하게 향상된다는 것, 모델 크기와는 관계 없이 각 언어에 사용되는 실질 파라미터는 가중치에 의해 결정된다는 것, 추가로 EN -> XX 번역의 경우 타겟 언어의 유사도와 성능은 관계가 없으며 시너지는 XX -> EN의 형태로 multilingual 인코딩을 할 때 발생한다는 것을 보였네요. 이쪽 결과는 디코더가 아니라 인코더에서 공유가 발생한다는 이전 결과들과 합치하는 것 같습니다.

결과적으로 모델 크기와 가중치에 따라 각 언어에 대해 달성할 수 있는 성능을 예측하는 커브를 그릴 수 있었네요.

#multilingual #nmt #scaling 