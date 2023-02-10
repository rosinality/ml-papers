https://arxiv.org/abs/2211.05826

The CRINGE Loss: Learning what language not to model (Leonard Adolphs, Tianyu Gao, Jing Xu, Kurt Shuster, Sainbayar Sukhbaatar, Jason Weston)

lm은 보통 모델이 출력해야 하는 토큰(positive)들로 학습시키는데 모델이 출력하지 않아야 할 토큰(negative) 데이터를 사용해 모델이 적절하지 않은 출력을 생성하지 않도록 하기. standard cross entropy에 positive top-k 토큰 중 하나를 샘플링하고 negative 토큰과의 contrastive loss를 사용하는 방식으로 학습.

#lm #safety 