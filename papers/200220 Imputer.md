https://arxiv.org/abs/2002.08926

Imputer: Sequence Modelling via Imputation and Dynamic Programming (William Chan, Chitwan Saharia, Geoffrey Hinton, Mohammad Norouzi, Navdeep Jaitly)

CTC와 같이 출력 시퀀스의 길이가 입력 시퀀스의 길이보다 짧은 상황에 적용할 수 있는 시퀀스 생성 알고리즘. 이전 alignment에 대해서 conditional하게 다음 시퀀스를 생성하는 방식으로 문제에 접근. 따라서 CTC처럼 conditionally independent하게 생성할 수 있고 완전히 autoregressive하게 생성할 수도 있고 그 중간 지점도 가능한 방식. 굉장히 흥미로운 도구로 사용할 수 있을 것 같음.

#non-autoregressive #asr #ctc