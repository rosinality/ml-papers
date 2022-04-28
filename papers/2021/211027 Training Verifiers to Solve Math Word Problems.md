https://arxiv.org/abs/2110.14168

Training Verifiers to Solve Math Word Problems (Karl Cobbe, Vineet Kosaraju, Mohammad Bavarian, Jacob Hilton, Reiichiro Nakano, Christopher Hesse, John Schulman)

gpt-3로 계산 문제 풀기. 8.5k 규모의 데이터셋을 만들었네요. 그냥 파인튜닝으로는 성능이 잘 안 나오고...답이 맞았나 틀렸나 체크하는 verifier를 학습시키고 파인튜닝된 모델에서 샘플을 여러 개 뽑아서 체크하는 방법을 붙이니 성능이 꽤 올라가네요.

여전히 계산 실수를 많이 해서 계산은 계산기를 쓰도록 학습을 시켰다고 합니다.

#lm