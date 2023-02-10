https://arxiv.org/abs/2302.04761

Toolformer: Language Models Can Teach Themselves to Use Tools (Timo Schick, Jane Dwivedi-Yu, Roberto Dessì, Roberta Raileanu, Maria Lomeli, Luke Zettlemoyer, Nicola Cancedda, Thomas Scialom)

외부 도구를 API로 호출해서 사용할 수 있는 lm 만들기. API 호출 구문이 삽입된 텍스트를 생성하도록 파인튜닝 하는 것이라 이 API 호출이 삽입된 데이터를 만드는 게 가장 중요한 부분입니다. 자주 그렇듯 lm에 in-context learning으로 이 예시 텍스트를 샘플링하게 만드는 방식으로 태클했네요.

#llm 