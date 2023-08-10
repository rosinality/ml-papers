https://arxiv.org/abs/2307.02628

SkipDecode: Autoregressive Skip Decoding with Batching and Caching for Efficient LLM Inference (Luciano Del Corro, Allie Del Giorno, Sahaj Agarwal, Bin Yu, Ahmed Awadallah, Subhabrata Mukherjee)

early exit이 llm 판에 등장했군요. 그런데 전통적인 early exit과는 달리 배치 처리 등을 고려해서, 하위 레이어에서 exit 하는 대신 하위 레이어를 skip하고 상위 레이어를 쓰는 방식입니다. 추가적으로 토큰 단위로 쓰는 레이어의 수가 monotonic 하게 감소하는 세팅을 고정해놓네요. 흥미롭긴 한데 성능 변화를 감안해서 최적화하기가 까다로울 것 같군요. 늘 그렇지만 큰 모델을 최적화하다가 그냥 작은 모델을 쓰는 것이 나은 상황이 되어버리는 것을 조심해야겠죠.

#efficiency 