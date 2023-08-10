https://arxiv.org/abs/2305.19370

Blockwise Parallel Transformer for Long Context Large Models (Hao Liu, Pieter Abbeel)

memory efficient하게 long context attention을 구현하기. q를 쪼개고 kv를 다시 쪼개서 계산하는 방식이군요. 실제로 이렇게 학습하는 것이 정말로 잘 돌아갈지가 궁금하긴 한데...여하간 이제 context length를 늘리는 것 자체는 큰 문제는 되지 않는 것 같군요. 실제로 그 context length를 잘 활용하는가와는 별개로.

#efficiency 