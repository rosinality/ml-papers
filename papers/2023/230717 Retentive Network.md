https://arxiv.org/abs/2307.08621

Retentive Network: A Successor to Transformer for Large Language Models (Yutao Sun, Li Dong, Shaohan Huang, Shuming Ma, Yuqing Xia, Jilong Xue, Jianyong Wang, Furu Wei)

오...이건 좀 흥미롭네요. 기본적으로 linear attention에서 positional한 요소를 강화한 모델이라는 느낌인데...7B 정도에서까지 트랜스포머보다 나은 scaling curve를 보여줬네요.

개인적으로는 long context length에서 어느 정도까지 성능이 나올지 궁금하긴 합니다. 2048 정도까지는 괜찮다고 보고하고 있긴 하지만 rwkv도 2048 length 이상에서 문제가 있었던 것 같네요.

#linear_attention #recurrent 