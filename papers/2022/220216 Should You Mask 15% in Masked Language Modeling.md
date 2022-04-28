https://arxiv.org/abs/2202.08005

Should You Mask 15% in Masked Language Modeling? (Alexander Wettig, Tianyu Gao, Zexuan Zhong, Danqi Chen)

mlm에서 마스크 비율을 15%로 잡는 것이 최적인가? 물론 그럴 리 없겠죠. 40%가 최적으로 보이고 80%까지도 학습이 되네요. 토큰 교체나 동일 토큰 예측 같은 것도 필요 없고 masking만으로 충분한 것 같다고. 또한 span prediction 같은 것도 좋긴 한데 마스크 비율을 높이는 것으로 커버가 된다고 하는군요.

#mlm