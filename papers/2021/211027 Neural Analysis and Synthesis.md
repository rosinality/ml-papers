https://arxiv.org/abs/2110.14513

Neural Analysis and Synthesis: Reconstructing Speech from Self-Supervised Representations (Hyeong-Seok Choi, Juheon Lee, Wansoo Kim, Jie Hwan Lee, Hoon Heo, Kyogu Lee)

wav2vec 2.0에서 추출한 feature와 yin algorithm으로 추출한 feature를 reconstruction하는 방식으로 self supervision으로 학습됐네요. voice conversion은 이 feature들을 교체하는 방식으로 가능합니다. 이 feature들 속에 pitch나 speaker 정보가 섞이지 않도록 perturbation을 주는 작업이 중요하겠습니다.

오디오 생성이나 오디오 변환도 요즘 꽤 재밌는 결과들이 나오네요. 이 모델도 집에 하나 들여놓으면 가지고 놀기 재미있을 듯 합니다.

#audio_synthesis #self_supervised 