https://arxiv.org/abs/2108.05036

DEMix Layers: Disentangling Domains for Modular Language Modeling (Suchin Gururangan, Mike Lewis, Ari Holtzman, Noah A. Smith, Luke Zettlemoyer)

요즘 mixture of experts가 인기있네요. 큰 모델에 관심이 많은데 moe가 큰 모델 만드는 전통적인 레시피였기 때문에 그런가 싶기도 하고요.

이쪽은 일반적인 moe와는 다르게 routing을 학습 기반으로 하는 것이 아니라 도메인 레이블이 있다고 가정하고 도메인 별로 다른 expert를 쓰는 방식으로 태클했습니다. 그러면 테스트할 때 도메인을 모른다면 어떻게 할 것인가? 베이즈 룰로 도메인에 대한 시퀀스 확률을 뒤집어서 이 확률을 mixture weight로 사용합니다.

도메인 특화 모델을 만들고 싶은 수요가 꽤 있어서 참고할만...할 수도 있겠지만 트랜스포머에서는 ffn을 moe로 만들면 할만하다는 레시피가 있어서 가능한 것이기는 하죠.

#lm #mixture_of_experts