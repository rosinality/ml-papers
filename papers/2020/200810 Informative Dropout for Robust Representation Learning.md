https://arxiv.org/abs/2008.04254

Informative Dropout for Robust Representation Learning: A Shape-bias Perspective (Baifeng Shi, Dinghuai Zhang, Qi Dai, Zhanxing Zhu, Yadong Mu, Jingdong Wang)

cnn에서 texture bias를 억제하고 shape에 집중하게 만들기. 패치 근방의 패치들을 사용해서 self information을 계산하고 self information이 낮은 패치를 dropout으로 억제. texture는 반복되는 경향이 있으므로 이렇게 계산된 self information이 낮을 것이라는 아이디어. #robustness