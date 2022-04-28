https://arxiv.org/abs/2203.06850

Efficient Language Modeling with Sparse all-MLP (Ping Yu, Mikel Artetxe, Myle Ott, Sam Shleifer, Hongyu Gong, Ves Stoyanov, Xian Li)

mlp with gating으로 lm 학습하기. moe 기반의 sparse 모델입니다. 더 높은 성능을 더 적은 연산량으로 달성했네요. autoregressive lm을 all mlp로 태클한 건 이전에도 별로 없었던 것 같네요. autoregressive이기 때문에 moe routing에 이후 토큰 정보를 쓸 수 없어서 그에 대한 고려가 들어가 있습니다. spatial mixing에서 어떻게 했는지는 나와있진 않은데 nxn 행렬이니 아마 masking으로 될 것 같네요.

#mlp #lm