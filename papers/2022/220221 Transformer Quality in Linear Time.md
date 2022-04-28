https://arxiv.org/abs/2202.10447

Transformer Quality in Linear Time (Weizhe Hua, Zihang Dai, Hanxiao Liu, Quoc V. Le)

mhsa의 단순화된 버전인 gated attention unit을 만든 다음 이것의 효율적인 버전을 만들었네요. 전반적인 형태는 chunked local quadratic attention + chunk linear attention이라는 느낌입니다. autoregressive lm에서 linear attention의 효율성을 고려한 결과라고 합니다. 좀 더 큰 모델에서 perplexity나 transfer 결과도 볼 수 있으면 재밌겠나 싶네요.

약간 다르지만 relu^2를 발견한 다음 잘 쓰고 있네요. softmax 대신 relu라는 발상에서는 https://arxiv.org/abs/2202.08791 이쪽도 생각나네요.

#efficient_attention #transformer #linear_attention #local_attention 