https://arxiv.org/abs/2205.06266

Lifting the Curse of Multilinguality by Pre-training Modular Transformers (Jonas Pfeiffer, Naman Goyal, Xi Victoria Lin, Xian Li, James Cross, Sebastian Riedel, Mikel Artetxe)

multilingual 모델의 capacity 한계를 해소하기 위해 각 언어별 특화 모듈을 self attention/feed forward 모듈 뒤에 끼워넣는 방식을 채택했네요. adapter와 비슷하지만 adapter와는 다르게 각 언어별 모듈을 학습 시에 동시에 학습하고 언어 추가는 새 모듈을 추가하고 다른 weight를 고정시킨 다음 파인튜닝하는 방식으로 접근한다는 발상입니다.

#multilingual #adapter #mixture_of_experts 