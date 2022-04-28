https://arxiv.org/abs/2002.09402

Addressing Some Limitations of Transformers with Feedback Memory (Angela Fan, Thibaut Lavril, Edouard Grave, Armand Joulin, Sainbayar Sukhbaatar)

Accessing Higher-level Representations in Sequential Transformers with Feedback Memory (Angela Fan, Thibaut Lavril, Edouard Grave, Armand Joulin, Sainbayar Sukhbaatar)

트랜스포머가 이전 스텝의 정보를 충분히 사용하지 못하는 것(즉 레이어 l의 attention은 이전 스텝의 정보를 레이어 l-1 이하에서만 가져올 수 있다는 것)이 아쉬우니 이전 스텝의 정보를 weighted sum 해서 다음 스텝에 결합해주는 방법을 도입. 이 팀은 이런 작업을 계속 하는 듯. recurrent스러워서 학습이 느려지지만 어차피 생성 시에는 한 토큰씩 가져오니 괜찮지 않을까? 하는 제안.

#transformer #recurrent