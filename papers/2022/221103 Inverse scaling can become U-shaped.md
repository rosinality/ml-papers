https://arxiv.org/abs/2211.02011

Inverse scaling can become U-shaped (Jason Wei, Yi Tay, Quoc V. Le)

모델이 커질 수록 성능이 떨어지는 과제가 있는가? 라는 방향의 탐색의 결과 4가지 과제가 선정됐는데(inverse scaling law) PaLM 540B를 가져오니 그 중 3개 과제에 대해서는 모델이 커지자 성능이 다시 올라오는 패턴이 발견됐고 (U-shaped scaling) chain of thought를 가져오니 4개 문제 다 해결이 됐네요. 헌 창 쓰듯 PaLM 540B를 휘두르고 있군요.

이 현상에 대해 이 4개 과제는 true task와 distractor task로 구성되어 있고(signal and noise로 생각할 수 있겠네요.) 작은 모델은 둘 다 못 풀어서 랜덤 찍기를 하고, 중간 사이즈 모델은 distractor task를 풀어서 성능이 떨어지고, 더 큰 모델을 동원하니 distractor를 무시하고 true task만 풀어서 성능이 높아진다는 설명을 제시하고 있습니다.

#llm #prompt 