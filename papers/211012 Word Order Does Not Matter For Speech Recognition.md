https://arxiv.org/abs/2110.05994

Word Order Does Not Matter For Speech Recognition (Vineel Pratap, Qiantong Xu, Tatiana Likhomanenko, Gabriel Synnaeve, Ronan Collobert)

asr에서 단어 순서를 빼버리고 단어의 숫자를 세는 loss를 사용해 학습. 완전 ACE loss (https://arxiv.org/abs/1904.08364) 네요. 이쪽은 추가로 pseudo label을 만들고 word level로 순서 없이 학습된 모델을 character level 모델로 distill 하는 절차가 들어갔습니다.

#asr #weak_supervision 