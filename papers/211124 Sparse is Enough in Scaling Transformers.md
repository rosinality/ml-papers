https://arxiv.org/abs/2111.12763

Sparse is Enough in Scaling Transformers (Sebastian Jaszczur, Aakanksha Chowdhery, Afroz Mohiuddin, Łukasz Kaiser, Wojciech Gajewski, Henryk Michalewski, Jonni Kanerva)

sparsity로 추론 시 디코딩 속도를 가속한 트랜스포머. relu activation에서 0인 부분을 예측하는 모듈로 ff를 sparse하게 만들고 qkv linear를 permutation + conv로 대체했네요. 추가로 logit linear를 sparse하게 만든다거나 sru를 끼워넣어서 학습 시점에 사용하지 않은 길이에 대한 generalization을 시도한다거나 한 결과들도 있습니다.

결과적으로 17B 모델에서 토큰 당 3.7초 걸리던 것을 0.1 ~ 0.2초 수준으로 낮췄네요. cpu에서 batch size 1로 본 결과라고 합니다만 이 정도 향상이 가능하다면 쓸 수 있는 방법이 있지 않을까 싶네요.

#sparsity #efficiency #transformer