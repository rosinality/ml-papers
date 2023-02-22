https://arxiv.org/abs/2302.08582

Pretraining Language Models with Human Preferences (Tomasz Korbak, Kejian Shi, Angelica Chen, Rasika Bhalerao, Christopher L. Buckley, Jason Phang, Samuel R. Bowman, Ethan Perez)

alignment reward를 파인튜닝이 아니라 프리트레이닝 시점부터 결합하는 것이 더 유리하지 않은가라는 연구. reward 모델로 계산한 스코어를 추가 condition으로 결합할 수도 있고 아니면 unlikelihood 같은 loss에 결합할 수도 있겠네요.

condition으로 결합하는 것은 얼마 전에 나왔던 https://arxiv.org/abs/2302.07388 와 유사하다고 할 수 있을 것 같네요. 이쪽이 더 다양한 활용 방법을 비교 분석했다고 할 수 있을 듯 합니다. 다만...이쪽에서도 가장 강력한 방법은 condition 추가라고 보는 것 같네요.

#llm #instruct #alignment