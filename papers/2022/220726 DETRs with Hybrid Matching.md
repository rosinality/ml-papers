https://arxiv.org/abs/2207.13080

DETRs with Hybrid Matching (Ding Jia, Yuhui Yuan, Haodi He, Xiaopei Wu, Haojun Yu, Weihong Lin, Lei Sun, Chao Zhang, Han Hu)

두 논문이 아이디어가 놀라울 정도로 유사하네요. detr에서 one-to-one matching을 하니 positive query의 수가 줄어들고, 이 문제를 해소하기 위해 n개 그룹의 query embedding을 만들고 ground truth box도 k개로 복사한 다음 디코더에 입력해서 매칭하는 방식으로 one-to-many 학습을 시키는 방법입니다. query embedding 그룹 사이에 interaction을 없애기 위해 attention masking을 사용하고요. 두 논문의 차이는 query embedding 그룹의 개수를 1개로 설정하는가 k개로 설정하는가인 것 같네요.

#detr #efficient_attention 