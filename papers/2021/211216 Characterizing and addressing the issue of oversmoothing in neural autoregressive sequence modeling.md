https://arxiv.org/abs/2112.08914

Characterizing and addressing the issue of oversmoothing in neural autoregressive sequence modeling (Ilia Kulikov, Maksim Eremeev, Kyunghyun Cho)

eos가 왜 이상한 곳에서 나오는가에 대한 연구. eos가 나오기 전 시점 모두에 대해서는 eos의 확률이 아주 낮아야 하고 eos가 나와야할 시점에서는 아주 높아야 하는데 이런 극적인 변화가 잘 모델링 되지 않고 smoothing 되는 지점에서 문제가 발생했다고 추정했네요. 그래서 이걸 막기 위한 loss를 사용해서 실험을 해봤는데...디코딩 시 큰 빔 크기에서는 효과가 있는데 실제로 쓰이는 작은 빔 크기에는 이 loss와는 별 관계 없이 잘 되는 것처럼 결과가 나왔네요.

#autoregressive_model 