https://twitter.com/SanhEstPasMoi/status/1632775840135016448
https://docs.google.com/document/d/1ZNGyVWYFUbzV0xuei4SED2QAakGjMpaaQALcKYQm46U

huggingface의 flamingo 재현 시도 과정에서 겪은 경험.

교훈 두 가지.

1. loss 폭발의 전조는 activation 폭발. 최하단 레이어에서부터 증가하기 시작해 네트워크 전체로 퍼져나감.
2. vit-22b의 qk layer norm은 확실히 효과가 있음. l2 normalization은 효과는 있지만 성능이 약간 떨어짐
3. 
#llm #multimodal 