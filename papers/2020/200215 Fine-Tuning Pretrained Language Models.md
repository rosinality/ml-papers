https://arxiv.org/abs/2002.06305

Fine-Tuning Pretrained Language Models: Weight Initializations, Data Orders, and Early Stopping (Jesse Dodge, Gabriel Ilharco, Roy Schwartz, Ali Farhadi, Hannaneh Hajishirzi, Noah Smith)

BERT 파인튜닝에서 랜덤 시드를 랜덤 서치해봤더니 시드에 따른 차이가 상당히 큼. 랜덤 시드는 가중치 초기화와 학습 데이터의 순서에 영향을 미치는데 이 둘 모두 모델 성능에 상당한 영향을 미침. 좋은 시드를 찾아야 하는데 (그런데 또 여러 데이터셋에 대해 잘 되는 시드가 있기는 있다고 함) 딱히 방법이 없으니 early stopping으로 랜덤 서치를 많이 해보는 것이 좋은 듯.

아무래도 파인튜닝에 좀 더 체계화된 방법을 찾아볼 필요가 있지 않을까 하는 생각. 이전 ULMFiT처럼.

#transformer #bert #finetuning