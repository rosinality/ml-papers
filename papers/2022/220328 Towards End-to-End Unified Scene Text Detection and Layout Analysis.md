https://arxiv.org/abs/2203.15143

Towards End-to-End Unified Scene Text Detection and Layout Analysis (Shangbang Long, Siyang Qin, Dmitry Panteleev, Alessandro Bissacco, Yasuhisa Fujii, Michalis Raptis)

구글에서 단어 박스 + 라인, 문단 annotation이 된 데이터셋을 구축해서 공개했네요. 테스트용으로 돌린 모델은 max-deeplab 기반 instance segmentation 입니다. 단어 혹은 라인 instance를 instance segmentation으로 검출한 다음 이 instance들의 affinity를 예측해서 문단으로 묶는 방식이네요. 매칭은 텍스트 instance로 하고 여기서 나온 permutation으로 affinity matrix를 구성하네요.

꽤 흥미롭고 scene에 대해서 line/paragraph 같은 layout을 추출하는 방향으로 진전이 있었다는 것은 의미있는 것 같습니다.

#ocr