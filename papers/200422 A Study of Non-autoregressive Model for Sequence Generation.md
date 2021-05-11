https://arxiv.org/abs/2004.10454

A Study of Non-autoregressive Model for Sequence Generation (Yi Ren, Jinglin Liu, Xu Tan, Zhou Zhao, Sheng Zhao, Tie-Yan Liu)

TTS에서는 NAR이 꽤 괜찮은 것 같은데 MT나 ASR에서는 왜 잘 안 될까? MLM 스타일의 seq2seq 모델을 만들어서 타겟 시퀀스에 어텐션이 얼마나 꽂히는지를 측정해 생성시 타겟 시퀀스에 대한 의존성을 측정. TTS에 비해 NMT/ASR에서 이 의존성이 큼. KD를 하면 성능이 높아지고 이 의존성이 낮아짐.

#non-autoregressive 