https://arxiv.org/abs/2206.03452

Can CNNs Be More Robust Than Transformers? (Zeyu Wang, Yutong Bai, Yuyin Zhou, Cihang Xie)

convnext에서 보여줬던 cnn으로 vit 수준의 robustness를 확보할 수 있다는 결과의 연장선. patchify stem, 큰 커널 크기, normalization과 activation을 줄이는 것이 중요하다는 분석이네요. batch norm/relu를 사용했는데 layer norm/gelu와의 비교도 궁금하긴 합니다. 일단 batch norm과 relu를 사용하는 조건에서도 robustness를 증진시킬 수 있다는 것은 확인했네요.

downstream task들에서도 이렇게 확보된 robustness가 도움이 될지도 궁금합니다.

#robustness