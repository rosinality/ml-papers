https://arxiv.org/abs/2307.02486

LongNet: Scaling Transformers to 1,000,000,000 Tokens (Jiayu Ding, Shuming Ma, Li Dong, Xingxing Zhang, Shaohan Huang, Wenhui Wang, Furu Wei)

attention sparsification인데 dilated conv 스타일로 만들었습니다. dilated라는 표현을 정말 오랜만에 보는 느낌이군요. sparse attention이라고 하면 bigbird 같은 스타일이 생각나지만 이쪽은 실제로 꽤 고속으로 작동하도록 만들 수 있는 모양입니다. 메모리 제약이 아니라면 sequence length에 대한 제약이 거의 없다는 느낌이네요.

#efficient_attention 