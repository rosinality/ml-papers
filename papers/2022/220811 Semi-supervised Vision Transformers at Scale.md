https://arxiv.org/abs/2208.05688

Semi-supervised Vision Transformers at Scale (Zhaowei Cai, Avinash Ravichandran, Paolo Favaro, Manchen Wang, Davide Modolo, Rahul Bhotika, Zhuowen Tu, Stefano Soatto)

이미지넷 데이터 1%로 top-1 80% 달성. mae + fixmatch + ema teacher + mixup with pseudo label + vit-huge 조합입니다.

성능 변화를 보고 싶어서 정리해봤는데 대략 이렇습니다.

vit-base imagenet 1%
mae, finetune: 57.4
mae, ema-teacher: 65.3
mae, ema-teacher, mixup: 71.0

vit-base imagenet 10%
scratch, ema-teacher: 68.9
mae, finetune: 73.7
mae, ema-teacher: 78.1
mae, ema-teacher, mixup: 79.7

#semi_supervised_learning 