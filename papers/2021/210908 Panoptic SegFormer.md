https://arxiv.org/abs/2109.03814

Panoptic SegFormer (Zhiqi Li, Wenhai Wang, Enze Xie, Zhiding Yu, Anima Anandkumar, Jose M. Alvarez, Tong Lu, Ping Luo)

panoptic segmentation 모델이 하나 나왔네요. multiscale feature를 deformable attention encoder로 결합, location decoder로 각 instance의 위치 정보를 찾아낸 다음 이 정보를 mask decoder에 쿼리로 입력해 마스크를 뽑는 방식이군요. 흥미롭네요. deformable attention과 location을 쿼리의 초기값으로 잡는 방식이 디자인을 쉽게 만드는 측면이 있는 것 같습니다.

(segformer라는 이름이 붙어있긴 한데 역시 과제가 과제라서 그런지 segformer스러운 극단적인 심플함은 없긴 하네요.)

pvtv2를 백본으로 썼는데...어느새 pvtv2가 나왔었군요. 입력 크기를 줄이는 방식으로 태클하는 모델이라 한계가 있다는 생각을 했었는데 어쩌면 보통 쓰는 정도의 입력 크기에서 경쟁력이 있을 수도 있겠네요.

#panoptic_segmentation #transformer #detr 