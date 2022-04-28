https://arxiv.org/abs/2004.01655

Aligned Cross Entropy for Non-Autoregressive Machine Translation (Marjan Ghazvininejad, Vladimir Karpukhin, Luke Zettlemoyer, Omer Levy)

nonautoregressive mt 문제에서 cross entropy는 토큰의 위치가 어긋난 것에 대해 큰 패널티를 주기 때문에 학습을 어렵게 만듦. 이를 완화해서 모델 출력과 타겟 토큰 시퀀스 사이의 가능한 alignment들을 고려해서 loss를 계산하기.

#non-autoregressive 