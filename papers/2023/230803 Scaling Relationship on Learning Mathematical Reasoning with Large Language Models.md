https://arxiv.org/abs/2308.01825

Scaling Relationship on Learning Mathematical Reasoning with Large Language Models (Zheng Yuan, Hongyi Yuan, Chengpeng Li, Guanting Dong, Chuanqi Tan, Chang Zhou)

mathematical reasoning vs pretrain & sft. sft 혹은 in context learning으로 gsm8k를 테스트했을 때의 성능이 pretrain loss에 대해 거의 선형적으로 움직이는 군요. pretrain loss가 낮아질수록 sft 데이터에 대한 의존도도 낮아집니다.

추가로 rejection sampling을 사용해 sft 데이터를 보강하는 방식으로 작은 모델에서 성능을 크게 향상시킨 결과도 보고했네요. 여기서의 rejection sampling이 feedback 기반 튜닝으로도 생각할 수 있다는 것을 고려하면 feedback의 잠재적인 효과를 보여주는 것 같기도 합니다.

#llm 