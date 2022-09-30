https://arxiv.org/abs/2209.15003

Compositional Semantic Parsing with Large Language Models (Andrew Drozdov, Nathanael Schärli, Ekin Akyuürek, Nathan Scales, Xinying Song, Xinyun Chen, Olivier Bousquet, Denny Zhou)

llm으로 semantic parsing하기. 방법이 꽤 복잡하군요.

1. 우선 입력 시퀀스를 syntactic parsing으로 분해해서 트리를 만듭니다.
2. 이 트리를 기반으로 학습 셋에서 추출한 일부 샘플과 비교해서 추가 예제를 샘플링합니다.
3. 이렇게 추출한 예제와 입력 문장을 분해해 추출한 단순한 문장들을 결합해서 답을 예측하도록 한 다음 최종 semantic parse 결과를 출력하게 합니다.

#semantic_parsing #llm 