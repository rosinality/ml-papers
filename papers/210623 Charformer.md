https://arxiv.org/abs/2106.12672

Charformer: Fast Character Transformers via Gradient-based Subword Tokenization (Yi Tay, Vinh Q. Tran, Sebastian Ruder, Jai Gupta, Hyung Won Chung, Dara Bahri, Zhen Qin, Simon Baumgartner, Cong Yu, Donald Metzler)

바이트 레벨 lm에서 토큰들을 묶어 일종의 서브워드를 만들어주는 네트워크를 끼워넣기. 바이트 시퀀스를 다양한 길이로 자른 다음 각 길이별로 점수를 매겨 결합하고 정해진 비율로 다운샘플링하는 구조네요. 심플하고 성능 및 속도에서 상당히 괜찮은 것 같습니다. 흥미롭네요.

#lm #tokenizer