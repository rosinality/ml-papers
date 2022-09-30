https://arxiv.org/abs/2208.03306

Branch-Train-Merge: Embarrassingly Parallel Training of Expert Language Models (Margaret Li, Suchin Gururangan, Tim Dettmers, Mike Lewis, Tim Althoff, Noah A. Smith, Luke Zettlemoyer)

이쪽은 도메인 정보를 사용하는 작업을 많이 하는군요. 시드 모델을 일단 학습시킨 다음 각 도메인 별로 모델을 학습시키고 이 새로 학습한 모델을 앙상블하거나 파라미터 평균 내는 식으로 domain expert lm을 학습합니다. 앙상블/평균 가중치는 demix처럼 domain probability를 사용했네요.

#lm #product_of_experts #ensemble