https://arxiv.org/abs/2203.16634

Transformer Language Models without Positional Encodings Still Learn Positional Information (Adi Haviv, Ori Ram, Ofir Press, Peter Izsak, Omer Levy)

트랜스포머 lm은 positional encoding이 없어도 성능이 나옵니다. 아마 autoregressive masking 때문에 각 position마다 context length가 다르기 때문일 것이라고 추측. 그래서 디코더가 아닌 인코더에서는 안 됩니다. 조금이라도 힌트가 있으면 집요하게 이용하는 걸 여기서 다시 확인하네요. 반대로 relative positional encoding을 사용하는 경우에도 context length를 사용한 absolute positional encoding이 어느 정도 결합된다고 볼 수도 있겠네요.

#lm #transformer #positional_encoding 