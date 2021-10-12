https://arxiv.org/abs/2108.13032

Shatter: An Efficient Transformer Encoder with Single-Headed Self-Attention and Relative Sequence Partitioning (Ran Tian, Joshua Maynez, Ankur P. Parikh)

bert 학습이 빠른 트랜스포머. attention 행렬에 적당한 relative position에 따라 변화하는 적당한 polynomial을 곱해서 relative position bias처럼 사용하기, softmax 대신 sigmoid attention 사용하기, multi head 대신 single head를 사용해서 key projection을 빼버리기, 추가로 query, value에 대해 position에 대한 bias를 query/value에 대한 projection으로 계산 등이 들어갔습니다. 기묘하네요.

#bert #transformer