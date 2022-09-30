https://arxiv.org/abs/2209.14500

Bidirectional Language Models Are Also Few-shot Learners (Ajay Patel, Bryan Li, Mohammad Sadegh Rasooli, Noah Constant, Colin Raffel, Chris Callison-Burch)

bidirectional lm으로 few shot prompting. mT5에 일반적인 prompt처럼 few shot 샘플들을 입력으로 주고 마지막 부분을 마스크 토큰으로 입력을 줍니다. 그 다음 디코더로 이 마스크를 디코딩하고, 디코딩된 토큰 하나를 입력에 붙인 다음 다시 마스크를 붙여서 생성해나가는 작업의 반복이네요. 더 작은 모델에서도 성능이 잘 나온다고는 하지만 디코딩이 좀 비효율적이긴 하겠습니다.

#in_context_learning #mlm 