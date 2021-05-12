https://arxiv.org/abs/2006.16378

An EM Approach to Non-autoregressive Conditional Sequence Generation (Zhiqing Sun, Yiming Yang)

train set의 multimodality가 nar의 난점이라는 것이 업계의 합의인 듯. 이 문제에 대응하기 위해 ar모델로 kd 해서 nar 모델을 학습시키고, nar 모델의 결과로 reweighting한 샘플로 ar을 학습시키는 것을 반복하는(EM) 방법을 제안.

#non-autoregressive #distillation 