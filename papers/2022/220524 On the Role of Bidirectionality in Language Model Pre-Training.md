https://arxiv.org/abs/2205.11726

On the Role of Bidirectionality in Language Model Pre-Training (Mikel Artetxe, Jingfei Du, Naman Goyal, Luke Zettlemoyer, Ves Stoyanov)

bidirectional/unidirectional attention과 bidirectional context(mlm)과 unidirectional context(regular lm)을 하나의 프레임워크로 통합한 다음 이 비중을 조절하면서 각 과제에 대해 보이는 성능을 관찰. regular lm이 next token prediction에 강하고 bidirectional mlm이 infilling과 finetuning에 강하고, 예측 대상이 적은 케이스(zero shot priming)에서는 regular lm도 잘 된다는 결과네요. 이 두가지 축(llm과 bert)외의 하이브리드들은 이 두 모델에 미치지 못합니다.

결과적으로 lm으로 푸는 게 적합한 과제에는 lm이 베스트고 파인튜닝으로 푸는 과제에는 mlm이 최선이고 그렇네요.

#lm #bert