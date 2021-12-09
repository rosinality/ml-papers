https://arxiv.org/abs/2112.01526

Improved Multiscale Vision Transformers for Classification and Detection (Yanghao Li, Chao-Yuan Wu, Haoqi Fan, Karttikeya Mangalam, Bo Xiong, Jitendra Malik, Christoph Feichtenhofer)

pooling attention 기반 visual backbone이 하나 더 나왔네요. 풀링 기반 방법은 이미지 크기가 커지면 결국 문제가 생기는 게 문제인데...그래서 이 부분에 대한 고려가 나와있네요. 풀링의 stride를 키우는 식으로 대처했을 때 swin 같은 window attention 기반 방법보다 특성이 더 낫고 아예 window attention을 섞어서 하이브리드를 만들면 더 낫다, 이런 결과입니다.

vit도 이제 성능 찍기의 단계에서 pooling vs window 같은 문제도 그렇고 약간 속도와 성능 사이의 트레이드오프에서 균형을 맞추는 작업의 단계로 넘어온 것 같네요.

#vit