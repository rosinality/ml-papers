https://arxiv.org/abs/2203.15556

Training Compute-Optimal Large Language Models (Jordan Hoffmann, Sebastian Borgeaud, Arthur Mensch, Elena Buchatskaya, Trevor Cai, Eliza Rutherford, Diego de Las Casas, Lisa Anne Hendricks, Johannes Welbl, Aidan Clark, Tom Hennigan, Eric Noland, Katie Millican, George van den Driessche, Bogdan Damoc, Aurelia Guy, Simon Osindero, Karen Simonyan, Erich Elsen, Jack W. Rae, Oriol Vinyals, Laurent Sifre)

이젠 flops - parameter 그래프를 다 보게 되네요. 모델 크기가 커지면 학습 토큰 양(학습 데이터 양) 또한 같은 비율로 늘어나야 하는데 기본 llm들은 모델 크기 증가에 비해 학습 토큰 양의 증가가 부족했다는 결론입니다. Gopher의 1/4 크기의 모델로 4배 이상의 학습 토큰을 사용해 총 연산량은 같게 맞춰 학습한 모델 Chinchilla로 Gopher를 압도했네요. 다만 어차피 데이터 규모가 워낙 커서 1 에폭을 돌지 못하는 상황이었다는 것을 고려할 필요는 있겠습니다.

딥 마인드 사람들이 lm을 잡기 시작하더니 결과가 무시무시하네요.

#lm 