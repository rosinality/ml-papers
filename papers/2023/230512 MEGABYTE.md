https://arxiv.org/abs/2305.07185

MEGABYTE: Predicting Million-byte Sequences with Multiscale Transformers (Lili Yu, Dániel Simig, Colin Flaherty, Armen Aghajanyan, Luke Zettlemoyer, Mike Lewis)

byte level tokenizer free transformer. patch embedding으로 byte sequence를 묶고, 그 위에서 일반적인 트랜스포머 레이어를 쌓은 다음 출력 단에 각 patch 내에서 동작하는 레이어를 하나 올린 형태입니다. 이쪽 연구는 꽤 오랜만에 보네요. 토크나이저는 다들 어떻게든 해결하고 싶은 대상이긴 하지만 byte representation의 임의성과 지금까지 나왔던 character level 모델들의 결과를 보면 잘 될까...하는 생각이 들긴 하네요.

#transformer #tokenizer 