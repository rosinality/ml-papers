https://arxiv.org/abs/2004.03828

Attentive Normalization for Conditional Image Generation (Yi Wang, Ying-Cong Chen, Xiangyu Zhang, Jian Sun, Jiaya Jia)

gan의 self attention을 대체하는 모듈. 채널을 몇 개 클래스에 해당하는 채널로 축소한 다음, 채널에 대해 softmax로 normalize하고 이 normalize된 feature에 대해 mean/std를 구해 원 feature map을 normalize하는 방법. self normalization 같은 느낌?