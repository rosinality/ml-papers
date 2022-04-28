https://arxiv.org/abs/2111.02387

An Empirical Study of Training End-to-End Vision-and-Language Transformers (Zi-Yi Dou, Yichong Xu, Zhe Gan, Jianfeng Wang, Shuohang Wang, Lijuan Wang, Chenguang Zhu, Nanyun (Violet)Peng, Zicheng Liu, Michael Zeng)

vision-language 모델 조합을 테스트해봤네요. 꽤 유용한 증거가 될 것 같습니다.

1. vision 인코더로는 clip, language 인코더로는 roberta가 강력. vision 인코더 자체의 성능은 swin이 낫지만 데이터 학습량과 objective의 차이가 큰 것 같긴 하네요.
2. vision/language 토큰을 같은 self attention에 밀어넣는 것보다는 개별적으로 self attention을 주고 cross attention을 활용하는 쪽이 강력.
3. 인코더-디코더보다는 인코더가 더 나아보임. 인코더-디코더 쪽이 더 유연하지만.
4. 학습 objective는 mlm + image-text matching이 효과적. maked image prediction은 도움이 되지 않음.

#vision-language #multimodal 