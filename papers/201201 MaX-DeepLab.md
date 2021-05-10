https://arxiv.org/abs/2012.00759

MaX-DeepLab: End-to-End Panoptic Segmentation with Mask Transformers (Huiyu Wang, Yukun Zhu, Hartwig Adam, Alan Yuille, Liang-Chieh Chen)

그리고 또 하나의 대세가 detr식의 end2end. 앵커도 중심점도 nms도 merge 스텝도 박스도 없다! 마스크의 클래스 레이블과 dice loss로 마스크를 매칭해서 학습. argmax 두 번만으로 클래스 레이블과 마스크 id를 뽑아낼 수 있음.