https://arxiv.org/abs/2302.01318

Accelerating Large Language Model Decoding with Speculative Sampling (Charlie Chen, Sebastian Borgeaud, Geoffrey Irving, Jean-Baptiste Lespiau, Laurent Sifre, John Jumper)

딥 마인드에서 이런 작업을 했군요. llm으로 토큰 한 번 뽑는 시간과 K개 토큰에 대한 logit을 계산하는 시간이 비슷하니, 작은 lm으로 일단 K개 토큰을 뽑고 그 K개 토큰을 llm으로 평가해서 쓸만한 토큰 subsequence를 rejection sampling으로 뽑는 방법입니다. TPU에서 대략 2배 정도의 속도 향상이 있었군요.

#autoregressive_model #decoding 