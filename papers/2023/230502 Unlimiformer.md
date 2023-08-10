https://arxiv.org/abs/2305.01625

Unlimiformer: Long-Range Transformers with Unlimited Length Input (Amanda Bertsch, Uri Alon, Graham Neubig, Matthew R. Gormley)

overlapping window를 사용해서 긴 시퀀스의 청크들을 인코더로 인코딩하고, 이렇게 만들어진 임베딩을 디코더에서 knn으로 top-k개 가져와서 cross attention에 사용한다...이런 방법이군요. 어차피 입력 시퀀스 길이가 길어지면 인코더 입력을 k개로 truncation 하는 것과 비슷하다고 보는 느낌이네요. 여하간 이 방법으로 99%의 attention mass를 유지 가능하다고 주장합니다.

인코더-디코더 모델에만 가능하고 이런 형태를 사용했을 때 attention mass가 유지되는 현상이 autoregressive lm에서 어느 정도 기대할 수 있는지 궁금하긴 합니다. 그렇지만 저도 이런 형태의 knn query가 꽤 괜찮은 접근이 아닌가 하는 생각이 들긴 합니다. 어차피 벡터 데이터베이스도 많이 쓰는데요.

#seq2seq