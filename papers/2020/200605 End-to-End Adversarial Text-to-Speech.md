https://arxiv.org/abs/2006.03575

End-to-End Adversarial Text-to-Speech (Jeff Donahue, Sander Dieleman, Mikołaj Bińkowski, Erich Elsen, Karen Simonyan)

character/phoneme에서 시작해서 오디오로 바로 tts. 토큰을 오디오 내에서의 위치와 지속시간에 맞게 정렬해주는 aligner 모듈이 핵심. 정렬이 완벽하게 일치해야 한다는 제약을 풀어주기 위해 soft dtw를 사용한 loss를 적용.

#tts #end2end