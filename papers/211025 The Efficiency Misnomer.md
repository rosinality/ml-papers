https://arxiv.org/abs/2110.12894

The Efficiency Misnomer (Mostafa Dehghani, Anurag Arnab, Lucas Beyer, Ashish Vaswani, Yi Tay)

모델을 비교하자면 모델 추론에 드는 비용과 그에 따른 효율성을 고려해서 비슷하게 맞춘 다음에 해야 하는데 널리 알려져 있듯 쓸만한 비용 척도가 없다는 문제네요. gflops나 파라미터 수가 별 쓸모가 없다는 건 이미 다들 받아들이는 부분이고(파라미터 수는 대체 왜 쓰는 걸까요) 그냥 속도를 측정하자니 온갖 변수들이 너무 많죠.

결론은 하나만 가지고는 안 되겠고 이것저것 다 보자...그런 형태가 되긴 했습니다.

Ross Wightman 아저씨는 activation count가 괜찮은 지표인 것 같다고 하시네요.  (https://twitter.com/wightmanr/status/1453060491970953217) 그렇지만 결국 쓰는 사람이 자기 사용 환경에 최적화해서 테스트해보는 수밖에 없지 않나 싶긴 합니다.

#metric 