https://arxiv.org/abs/2305.19466

The Impact of Positional Encoding on Length Generalization in Transformers (Amirhossein Kazemnejad, Inkit Padhi, Karthikeyan Natesan Ramamurthy, Payel Das, Siva Reddy)

causal mask 때문에 transformer decoder에서는 positional encoding 없이도 위치 정보를 추론할 수 있다는 것이 알려져 있었죠. 다르게 말하면 positional encoding이 존재하는 경우에도 causal mask를 통해 모델이 위치 정보를 파악할 수 있다는 의미라 문제가 복잡해진다는 느낌이었는데 힌트가 좀 더 생겼네요.

positional encoding이 없는 경우 T5 스타일의 relative positional encoding이 학습되는 것 같다고 합니다. alibi는 거리에 따라 attention weight가 감소한다는 느낌이고 rotary나 absolute pe는 비교적 uniform 하다고 하면 T5나 positional encoding이 없는 경우는 거리에 따라 감소하다가 비교적 장거리에 대해서 다시 attention weight가 증가하는 것 같은 패턴이네요.

학습한 과제가 algorithmic한 문제들이라서 이 결과가 natural language에 대해 갖는 의미로 바로 연결하기는 어려울 것 같긴 합니다.

#positional_encoding 