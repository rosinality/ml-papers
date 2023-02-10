https://arxiv.org/abs/2301.13310

Alternating Updates for Efficient Transformers (Cenk Baykal, Dylan Cutler, Nishanth Dikkala, Nikhil Ghosh, Rina Panigrahy, Xin Wang)

densenet 시절의 아이디어를 이런 형태로 다시 보게 되네요. 임베딩 벡터의 일부 dimension에만 transformer layer를 적용, 전체 dimension에는 간단한 vector 연산을 적용, 이후 이 둘을 결합해 결과 보정이라는 방식으로 실질 dimension을 늘리면서 연산 증가는 억제할 수 있다는 아이디어군요. 그런데 이건 단어 임베딩에만 적용해본 것 같네요.

#efficiency