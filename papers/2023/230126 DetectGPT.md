https://arxiv.org/abs/2301.11305

DetectGPT: Zero-Shot Machine-Generated Text Detection using Probability Curvature (Eric Mitchell, Yoonho Lee, Alexander Khazatsky, Christopher D. Manning, Chelsea Finn)

lm에서 생성된 텍스트를 어떻게 탐지할 것인가가 이제 중요한 문제가 됐네요. 이 논문의 가정은 lm이 생성한 텍스트는 사람이 쓴 텍스트와는 달리 perturbation에 따라 probability estimate가 크게 달라질 것이라는 가정을 사용해서 탐지 알고리즘을 설계했습니다. 다만 결국 텍스트를 생성한 lm에 접근이 가능해야할 것 같다는 게 문제네요.

#llm 