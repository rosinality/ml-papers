https://arxiv.org/abs/2302.05206

The Wisdom of Hindsight Makes Language Models Better Instruction Followers (Tianjun Zhang, Fangchen Liu, Justin Wong, Pieter Abbeel, Joseph E. Gonzalez)

rl 없이 instruct tuning을 해보자. instruction prompt / query에 모델로 샘플링한 answer로 triplet을 만든 다음 이 answer의 스코어가 높아지도록 instruction prompt를 편집하는 방식으로 작동하는군요. 스코어 평가는 그렇다 치고 instruction prompt를 편집하는 것이 문제인데 여기서는 prompt 자체를 정답 생성 / 오답 생성으로 만들고 편집은 negation을 취하는 방식으로 했습니다. 흠.

#instruct #reinforcement_learning 