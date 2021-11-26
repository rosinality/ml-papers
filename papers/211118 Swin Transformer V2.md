https://arxiv.org/abs/2111.09883

Swin Transformer V2: Scaling Up Capacity and Resolution (Ze Liu, Han Hu, Yutong Lin, Zhuliang Yao, Zhenda Xie, Yixuan Wei, Jia Ning, Yue Cao, Zheng Zhang, Li Dong, Furu Wei, Baining Guo)

swin v2가 나왔네요. 모델을 3B까지 키웠습니다. 흥미로운 부분은

1. pre norm -> post norm. 그렇지만 skip add 다음이 아니라 skip add 이전에 ln을 적용한 다음 add하는 방식.
2. dot prod attn -> cos attn. attn logit 값을 normalize 하기 위함.
3. discrete learnable pos bias -> 2 layer mlp를 사용한 continuous bias.
4. transfer 시점에 window 크기를 변화시키는 작업을 좀 더 쉽게 만들기 위해 position을 linear에서 log space로 변화.

결과적으로 vision task들을 한 번 더 쭉 도장깨기 했습니다.

#vit