https://arxiv.org/abs/2302.03202

Exploring the Benefits of Training Expert Language Models over Instruction Tuning (Joel Jang, Seungone Kim, Seonghyeon Ye, Doyoung Kim, Lajanugen Logeswaran, Moontae Lee, Kyungjae Lee, Minjoon Seo)

LG AI Research 쪽의 연구군요. multitask instruction finetuning에서 수많은 과제를 학습하는 것보다 하나의 과제만 학습한 모델이 그 학습 과제와 유사한 과제들에서 성능이 더 나을 수 있다는 결과. 그러니 개별 과제에 대해 adapter tuning을 하고 테스트 시점에서는 주어진 과제 텍스트와 유사한 텍스트에 학습된 모델을 꺼내와서 추론시키면 더 나을 수 있다, 이런 느낌이군요.

그렇지만 모델이 왕창 커지면 또 다른 문제가 될 것 같긴 합니다.

#multitask #instruct 