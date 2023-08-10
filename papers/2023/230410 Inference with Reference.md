https://arxiv.org/abs/2304.04487

Inference with Reference: Lossless Acceleration of Large Language Models (Nan Yang, Tao Ge, Liang Wang, Binxing Jiao, Daxin Jiang, Linjun Yang, Rangan Majumder, Furu Wei)

llm 디코딩 가속. lm에서 생성한 토큰들 중 마지막 N개와 매칭되는 레퍼런스 문서의 시퀀스가 있는지 확인하고, 시퀀스가 있다면 가져와서 lm에 입력으로 넣은 뒤 argmax를 해서 lm의 출력과 consistent한지 체크하고 consistent한 토큰들을 생성 토큰으로 출력. speculative decoding에서 모델을 따로 쓰는 대신 retrieval로 해결했다는 느낌이네요.

#efficiency #llm 