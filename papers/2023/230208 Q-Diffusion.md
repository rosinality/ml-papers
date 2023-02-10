https://arxiv.org/abs/2302.04304

Q-Diffusion: Quantizing Diffusion Models (Xiuyu Li, Long Lian, Yijiang Liu, Huanrui Yang, Zhen Dong, Daniel Kang, Shanghang Zhang, Kurt Keutzer)

diffusion 모델에 대한 quantization. 각 타임 스텝 별로 출력 분포가 달라진다는 게, 그리고 오차가 누적된다는 게 주요 문제인 것 같군요. 그런데 8bit 까지는 베이스라인도 꽤 괜찮아서 논문의 목표는 4bit 까지 내려가는 것인 것 같네요.

#ddpm #quantization 