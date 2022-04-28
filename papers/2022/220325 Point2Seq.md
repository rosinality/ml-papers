https://arxiv.org/abs/2203.13394

Point2Seq: Detecting 3D Objects as Sequences (Yujing Xue, Jiageng Mao, Minzhe Niu, Hang Xu, Michael Bi Mi, Wei Zhang, Xiaogang Wang, Xinchao Wang)

포인트 클라우드 논문은 잘 안 보는데 제목 파워가 상당해서 읽어봤습니다. pix2seq처럼 모든 객체들을 하나의 시퀀스로 합치는 것은 아니고 각 객체를 객체 속성의 시퀀스로 처리하는 쪽이네요. 시퀀스 디코딩을 시작하기 위한 시작은 전체 feature map의 feature token을 사용하고 loss 부여는 매칭을 얹은 형태.

#point_cloud