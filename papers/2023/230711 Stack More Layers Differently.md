https://arxiv.org/abs/2307.05695

Stack More Layers Differently: High-Rank Training Through Low-Rank Updates (Vladislav Lialin, Namrata Shivagunde, Sherin Muckatira, Anna Rumshisky)

아예 lora로 scratch에서부터 학습시키는 것도 괜찮지 않을까 싶었는데 그 방법이 나왔네요. 그런데 그냥 lora로만 학습시키면 low rank로 제약이 걸리니 일정 스텝마다 기본 weight를 lora로 학습된 weight로 치환하고 다시 lora를 리셋해서 학습하는 방법입니다. 재미있네요.

https://arxiv.org/abs/2108.06098

요새 hadamard product로 lora의 rank를 뻥튀기시키는 방법도 나왔던데 이런 것과 결합하면 또 재미있지 않을까 싶습니다.

#efficient_training 