https://arxiv.org/abs/2007.03496

AutoAssign: Differentiable Label Assignment for Dense Object Detection (Benjin Zhu, Jianfeng Wang, Zhengkai Jiang, Fuhang Zong, Songtao Liu, Zeming Li, Jian Sun)

fcos 같은 anchor-free 디텍터들은 center sampling과 박스 크기에 기반한 scale assign을 통해 레이블을 부여하는데 optimal한 방식이라고 보기는 어려움. 그래서 confidence map을 뽑아서 loss를 weighting하는 방식으로 레이블 부여를 학습하게 만듦. 직관적이고 좋은 아이디어지만 구현은...까다로울 듯. #detection #anchor_free