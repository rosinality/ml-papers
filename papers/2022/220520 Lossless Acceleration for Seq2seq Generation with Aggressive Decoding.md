https://arxiv.org/abs/2205.10350

Lossless Acceleration for Seq2seq Generation with Aggressive Decoding (Tao Ge, Heming Xia, Xin Sun, Si-Qing Chen, Furu Wei)

제목 뿐만 아니라 abstract도 공격적이네요. 입력 시퀀스 혹은 nar이 생성한 시퀀스를 autoregressive 모델에 입력한 다음 모델 출력과 같은 부분의 시퀀스를 사용하고, 달라지는 부분이 생기면 autoregressive 모델의 출력으로 입력 시퀀스를 고친 다음 다시 생성하는 것을 반복하는 방식. autoregressive 모델의 성능을 내면서 동시에 디코딩 속도를 수 배 향상시켰습니다.

#non-autoregressive #efficiency 