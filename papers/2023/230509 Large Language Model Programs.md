https://arxiv.org/abs/2305.05364

Large Language Model Programs (Imanol Schlag, Sainbayar Sukhbaatar, Asli Celikyilmaz, Wen-tau Yih, Jason Weston, Jürgen Schmidhuber, Xian Li)

슈미트후버 선생님의 이름이 딱 보여서 봤습니다. 알고리즘을 구성하고 그 알고리즘 내에 LLM을 끼워넣는다는 (요즘 많이 유행하는) 아이디어입니다. QA에 대한 알고리즘을 만들어봤네요. 질문에 대해 필요한 텍스트들을 LLM으로 찾아내고, 각 지문들과 그 지문들에 의거한 추론을 LLM으로 생성하고, 각 지문에 대한 추론들을 트리 형태로 구축해 LLM으로 순위를 매기고, 이 과정을 반복해서 트리 탐색을 하고 답을 내리는 식이군요.

end2end의 이상에서는 좀 멀어지는 느낌이지만...이런 알고리즘을 구성하는 것 자체는 흥미롭다 싶습니다.

#llm #prompt 