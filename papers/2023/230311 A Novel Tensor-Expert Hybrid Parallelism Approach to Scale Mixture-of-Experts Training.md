https://arxiv.org/abs/2303.06318

A Novel Tensor-Expert Hybrid Parallelism Approach to Scale Mixture-of-Experts Training (Siddharth Singh, Olatunji Ruwase, Ammar Ahmad Awan, Samyam Rajbhandari, Yuxiong He, Abhinav Bhatele)

마침 또 moe 논문이 보이는군요. moe에서 expert scaling은 효과가 점진적으로 감소하니 모델 또한 따라서 커져야 하고, 이 scaling에 적절한 3d parallel (data, tensor, expert) + zero를 디자인했다는 결과입니다. 6.7B + 16 expert로 40B 모델까지 테스트해봤군요.

#mixture_of_experts 