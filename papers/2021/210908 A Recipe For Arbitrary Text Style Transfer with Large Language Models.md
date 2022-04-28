https://arxiv.org/abs/2109.03910

A Recipe For Arbitrary Text Style Transfer with Large Language Models (Emily Reif, Daphne Ippolito, Ann Yuan, Andy Coenen, Chris Callison-Burch, Jason Wei)

구글 사람들이 요즘 llm으로 해보고 있는 것들. text style transfer인데...프롬프트 튜닝에서 style transfer 사례들을 추가할 때(few-shot) 타게팅하는 스타일을 입력해주는 것이 아니라 여러 스타일 사례들을 프롬프트로 추가해서 style transfer라는 일반적인 과제로 모델을 가이드한다...이런 느낌이군요.

한 가지 재미있는 트릭이 있는데 모델이 삑살난 케이스를 검출하기 위해 중괄호({)를 프롬프트에 추가해서 닫는 중괄호가 나오지 않으면 거르는 방식을 썼네요.

nlp에는 bert 이후에 그랬던 것처럼 한동안 llm 하나 만들어놓고 이것저것 해보고 찔러보는 연구들이 많이 나오겠네요.

#lm #prompt 