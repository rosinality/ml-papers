논문 이야기가 나온 김에 꺼내보자면 역시 요즘 efficient attention/transformer가 물을 만났다. 나온지 좀 된 Nyströmformer (https://arxiv.org/abs/2102.03902) 등을 필두로 해서,
LazyFormer: Self Attention with Lazy Update
https://arxiv.org/abs/2102.12702
attention을 몇 블럭마다 한 번씩만 계산해서 연산 필요량 낮추기. 역시 정말 갖가지 시도가 나오는 중.
SparseBERT: Rethinking the Importance Analysis in Self-attention
https://arxiv.org/abs/2102.12871
sparse attention 밀어붙이기. bert 프리트레이닝 상황에서 sparsity 조건 아래 attention map을 최적화해서 정말로 필요한 attention pattern만 뽑아보기. attention map의 diagonal element가 별로 필요하지 않다는 것을 발견.
Random Feature Attention
https://arxiv.org/abs/2103.02143
performer의 발전형 같은 느낌인데...efficient attention의 결과가 점점 더 좋아지네요.
Perceiver: General Perception with Iterative Attention
https://arxiv.org/abs/2103.03206
pixel (224 * 224!)-latent (1024) attention과 latent에 대한 transformer를 결합해서 pixel level attention 모델링.

#review