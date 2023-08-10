https://arxiv.org/abs/2307.03172

Lost in the Middle: How Language Models Use Long Contexts (Nelson F. Liu, Kevin Lin, John Hewitt, Ashwin Paranjape, Michele Bevilacqua, Fabio Petroni, Percy Liang)

document qa를 시켜보면 long context 모델의 경우에도 관련된 정보가 들어있는 문서의 위치에 따라 성능이 많이 달라진다는 연구. 아예 앞에 있거나 뒤에 있는 경우에 성능이 높네요. 인코더-디코더 모델과 디코더 모델을 비교한 것을 보면 autoregressive한 특성도 영향을 미치는 것 같습니다.

위에서 소개한 논문과 조합해서 생각해보면 distractor에 대해 강인한 특성을 주는 것이 long context를 실질적으로 활용하는 것에 중요할 수 있겠다는 생각이 드네요.

#lm #transformer 