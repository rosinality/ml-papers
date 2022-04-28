https://nvlabs.github.io/instant-ngp

Instant Neural Graphics Primitives with a Multiresolution Hash Encoding

이미 엄청나게 화제가 되어서 다들 보셨을 것 같긴 하네요. implicit representation에서 좌표를 feature로 변환하는 부분을 좌표를 학습되는 feature로 매핑하는 해시 테이블과 선형 보간으로 바꿔버렸습니다. nerf가 순식간에 학습되고 순식간에 렌더링 됩니다. 매 scene마다 학습이 필요한 implicit representation을 바로 쓸 수 있는 가능성이 생겼네요.

#implicit_representation 