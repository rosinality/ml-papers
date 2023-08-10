https://arxiv.org/abs/2303.06296

Stabilizing Transformer Training by Preventing Attention Entropy Collapse (Shuangfei Zhai, Tatiana Likhomanenko, Etai Littwin, Dan Busbridge, Jason Ramapuram, Yizhe Zhang, Jiatao Gu, Josh Susskind)

요즘 애플에서도 논문이 좀 나오는군요. attention 행렬의 row vector의 엔트로피가 너무 빠르게 감소하는 것이 학습 불안정성의 원인이고 이에 대해 놀랍게도 spectral norm(!) & scaling factor를 써서 태클했네요. power iteration이 할만하다고는 하지만 큰 모델에서는 부담스러울 것 같긴 합니다.

pre ln, adaptive optimizer, lr warmup 같은 것이 없어도 학습이 된다고 보고하고 있네요. 트랜스포머 학습의 불안정성에 대한 보고들을 종합하면 여러모로 attention weight의 phase transition이 너무 급격하게 발생하는 것과 관계가 있는 것 같긴 합니다. 이걸 얼마나 효율적이고 효과적으로 잡을 수 있는지가 중요한 방향인 것 같긴 하네요.

#transformer #stability 