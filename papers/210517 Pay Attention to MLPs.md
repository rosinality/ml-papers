https://arxiv.org/abs/2105.08050

Pay Attention to MLPs (Hanxiao Liu, Zihang Dai, David R. So, Quoc V. Le)

mlp로 비전과 nlp 태클하기. Spatial dimension으로 mlp를 돌리고 glu 같은 디자인을 채택해 gating을 추가. 트랜스포머보다 우수한 결과가 찍히기도 하는데, 단 시퀀스 간 모델링에는 좀 약해서 attention을 붙여주는 것이 필요. [https://arxiv.org/abs/2105.03322](https://arxiv.org/abs/2105.03322) 에서 나온 결과가 일치하기도 하고, [https://arxiv.org/abs/1904.05873](https://arxiv.org/abs/1904.05873) 에서 인코더-디코더 attention에 query-key interaction이 필요하다는 결과가 상응하기도 하고. (attention 이야기가 나올 때마다 이 논문을 끌어오게 되네요.)

[[200129 Empirical Attention]] [[210510 Are Pre-trained Convolutions Better than Pre-trained Transformers]]

#mlp #attention