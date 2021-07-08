https://arxiv.org/abs/2107.02192

Long-Short Transformer: Efficient Transformers for Language and Vision (Chen Zhu, Wei Ping, Chaowei Xiao, Mohammad Shoeybi, Tom Goldstein, Anima Anandkumar, Bryan Catanzaro)

efficient attention. non overlapping local attention + 길이를 축소한 global attention의 조합이군요. 길이 축소를 고정된 행렬로 처리하는 것이 아니라 키를 사용해 생성한다는 점은 마음에 듭니다. attention을 두 번 주는 방법 대신 local attention과 global attention의 키를 합쳐서 한 번에 처리하는 구성. long range arena, language model, imagenet classification에 테스트해봤네요.

#efficient_attention #local_attention 