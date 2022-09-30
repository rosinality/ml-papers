https://arxiv.org/abs/2205.14135

FlashAttention: Fast and Memory-Efficient Exact Attention with IO-Awareness (Tri Dao, Daniel Y. Fu, Stefano Ermon, Atri Rudra, Christopher Ré)

메모리 접근 최적화로 attention 최적화. 속도가 2~4 배 빨라지고 모델 학습도 전반적으로 최대 1.5~2배 정도 빨라지는 것 같네요. A100/fp16/head dimension 제약이 있긴 한데 제약에만 부합한다면 쓰지 않을 이유는 없어 보입니다.

#efficient_attention 