https://arxiv.org/abs/2006.00995

Amnesic Probing: Behavioral Explanation with Amnesic Counterfactuals (Yanai Elazar, Shauli Ravfogel, Alon Jacovi, Yoav Goldberg)

When Bert Forgets How To POS: Amnesic Probing of Linguistic Properties and MLM Predictions (Yanai Elazar, Shauli Ravfogel, Alon Jacovi, Yoav Goldberg)

probing(BERT 임베딩에 linear classifier를 붙여 POS 같은 정보가 추출되는지를 테스트하는 방식)은 추출되는 정보가 실제로 BERT에서 사용되는지를 검증할 수는 없음. 그래서 임베딩에서 정보를 지우면 성능이 변화하는지를 테스트하는 방식을 사용해 실험. masked vs non-masked에서 패턴이 다른 것도 유의미해보임.