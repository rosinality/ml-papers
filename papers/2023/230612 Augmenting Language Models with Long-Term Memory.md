https://arxiv.org/abs/2306.07174

Augmenting Language Models with Long-Term Memory (Weizhi Wang, Li Dong, Hao Cheng, Xiaodong Liu, Xifeng Yan, Jianfeng Gao, Furu Wei)

long context transformer 모델이 하나 더 나왔군요. 트랜스포머 백본의 key/value를 캐싱한 다음, 현 스텝의 트랜스포머의 hidden state와 retrieval한 key/value를 결합해 토큰을 예측하는 side network를 옆에 부착한 형태의 모델입니다.

long context와 관련된 방법들이 많이 나오는데 비교가 쉽지는 않네요. 다만 종종 그렇듯 이런 방법들이 결과적으로는 엇비슷할 가능성도 있다고 보입니다.

#transformer 