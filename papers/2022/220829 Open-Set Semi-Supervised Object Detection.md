https://arxiv.org/abs/2208.13722

Open-Set Semi-Supervised Object Detection (Yen-Cheng Liu, Chih-Yao Ma, Xiaoliang Dai, Junjiao Tian, Peter Vajda, Zijian He, Zsolt Kira)

semi supervised object detection + unlabeled 데이터에는 labeled 데이터의 레이블, 레이블 셋에 없는 종류의 객체도 있다고 가정했을 때 성능 올리기. 기본의 semi supervised 방법으로 pseudo label을 만들면 label이 확장되는 경향이 있어서 (예를 들어 캥거루도 강아지로 분류한다거나) 문제가 있고 따라서 레이블 밖 데이터, ood 데이터를 검출하는 것이 필요하군요.

ood 검출은 dino를 사용해서 객체 박스 패치를 positive로 사용하고 proposal box 중에 다른 객체에 걸리지 않은 백그라운드 박스를 네거티브로 사용하는 방법을 사용했습니다.

#semi_supervised_learning #open_set_recognition 