https://arxiv.org/abs/2207.07611

Position Prediction as an Effective Pretraining Strategy (Shuangfei Zhai, Navdeep Jaitly, Jason Ramapuram, Dan Busbridge, Tatiana Likhomanenko, Joseph Yitan Cheng, Walter Talbott, Chen Huang, Hanlin Goh, Joshua Susskind)

와 과거의 직소 퍼즐 예측이 이렇게 돌아오네요. MAE에서 이미지 패치를 마스킹하는 대신 position embedding을 마스킹하고, key-value로는 일부 context patch만 사용하는 방식으로 forward 한 다음 마스킹된 패치들의 position을 예측하게 하는 방식입니다.

#unsupervised_training #mlm