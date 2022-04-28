https://arxiv.org/abs/2109.05070

Instance-Conditioned GAN (Arantxa Casanova, Marlène Careil, Jakob Verbeek, Michal Drozdzal, Adriana Romero-Soriano)

pretrain된 네트워크로 이미지 임베딩을 뽑은 다음 이 이미지 임베딩을 condition으로 generator와 discriminator에 주입 & 이미지 임베딩의 k-nn 임베딩을 학습에 사용. 사실 이미지 한 장이 열 클래스 레이블보다 낫긴 하죠.

feature embedding을 써서 학습을 향상시키는 작업은 이전에도 있었지만 좀 더 과감하긴 하네요.

#gan