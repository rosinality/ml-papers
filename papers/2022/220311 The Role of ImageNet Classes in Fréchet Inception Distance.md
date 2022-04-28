https://arxiv.org/abs/2203.06026

The Role of ImageNet Classes in Fréchet Inception Distance (Tuomas Kynkäänniemi, Tero Karras, Miika Aittala, Timo Aila, Jaakko Lehtinen)

fid 계산에는 이미지넷 분류 모델(inception v3)의 로짓 직전 feature map을 사용하므로 결과적으로 이미지넷의 클래스와 밀접한 관계를 가지고 있음. 이미지에서 fid에 크게 영향을 미치는 영역들을 살펴봤더니 ffhq 같은 얼굴 데이터셋에서는 정작 얼굴 영역 밖이 중요하게 작용하는 것으로 나타남. 이건 이미지에 대해서 예측 결과로 나오는 이미지넷 클래스의 영향인 것으로 보임.

따라서 역으로 이미지넷 클래스 예측 결과를 real 이미지에 대한 예측 결과의 분포와 비슷하도록 맞춰주면 fid가 향상됨.

이러한 영향으로 이미지넷 프리트레이닝을 거친 모델을 학습에 결합한 모델(projected gan) 같은 경우 실제 성능에 비해 fid가 더 잘 나오는 것으로 보임.

평가 지표가 이미지넷 프리트레이닝된 모델을 사용해서 계산되는데 이미지넷 프리트레이닝을 거친 모델을 사용해서 생성 모델을 학습시키는 것은 위험하지 않은가 하는 이야기는 이전부터 나왔었는데 이렇게 터졌네요.

#gan 