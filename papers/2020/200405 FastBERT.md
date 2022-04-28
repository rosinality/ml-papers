https://arxiv.org/abs/2004.02178

FastBERT: a Self-distilling BERT with Adaptive Inference Time (Weijie Liu, Peng Zhou, Zhe Zhao, Zhiruo Wang, Haotang Deng, Qi Ju)

트랜스포머 마지막 레이어의 classifier를 teacher로 삼고 나머지 레이어들에 classifier를 달아 student로 만들어 self distillation을 수행. 그리고 각 레이어의 classifier의 결과로 uncertainty를 계산해서 uncertainty가 높으면 다음 레이어로 넘기고 낮으면 결과를 출력하는 방식.

#bert #distillation #lightweight 