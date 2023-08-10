https://arxiv.org/abs/2306.00983

StyleDrop: Text-to-Image Generation in Any Style (Kihyuk Sohn, Nataniel Ruiz, Kimin Lee, Daniel Castro Chin, Irina Blok, Huiwen Chang, Jarred Barber, Lu Jiang, Glenn Entis, Yuanzhen Li, Yuan Hao, Irfan Essa, Michael Rubinstein, Dilip Krishnan)

single style image를 사용한 stylized text-to-image. 특이하게 masked image generation 모델을 사용했네요. 파인튜닝 기반인데 오버피팅 문제를 학습 과정에서 모델이 생성한 이미지 중 괜찮은 것을 골라 학습 데이터셋으로 추가하는 방식으로 태클했습니다.

#ddpm #style_transfer 