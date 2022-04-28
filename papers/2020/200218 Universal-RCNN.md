https://arxiv.org/abs/2002.07417

Universal-RCNN: Universal Object Detector via Transferable Graph R-CNN (Hang Xu, Linpu Fang, Xiaodan Liang, Wenxiong Kang, Zhenguo Li)

여러 데이터셋에 대해 작동하는 object detector를 만들기. 가장 기본적인 방법이 논문에서도 언급하고 있는 백본은 공유하고 디텍션 헤드를 데이터셋별로 만드는 것인데, 이 방법은 디텍션 헤드들이 데이터셋에 따라 따로 노는 것이 아쉬움. 그래서 데이터셋의 레이블/카테고리 사이의 관계를 반영해보려고 한 것. 데이터셋 내의 카테고리의 관계들을 모델링하고 서로 다른 데이터셋의 카테고리의 사이의 매핑을 만들어서 다른 데이터셋의 정보를 결합. 뭔가 scene graph 같은 걸 하다가 나온 아이디어가 아닌가 싶음.

#multi_dataset #object_detection #graph