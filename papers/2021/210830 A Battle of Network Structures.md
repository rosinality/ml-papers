https://arxiv.org/abs/2108.13002

A Battle of Network Structures: An Empirical Study of CNN, Transformer, and MLP (Yucheng Zhao, Guangting Wang, Chuanxin Tang, Chong Luo, Wenjun Zeng, Zheng-Jun Zha)

똑같은 형태의 네트워크를 만들고 conv, self attention, mlp를 갈아끼워넣으면서 성능이 가장 잘 나오는 게 어느쪽인지 테스트해보자는 발상. 결과적으로 스코어는 비슷비슷하긴 합니다. (미묘하게 트랜스포머가 가장 나아보이기도 하지만)

추가로 멀티스테이지 구조와 로컬리티가 중요하다는 것을 발견. 요것도 친숙하긴 하죠.

거기에 cnn과 트랜스포머의 하이브리드가 좋지 않을까 하는 것도 발견. 이것도 요즘 (다들) 해볼만한 생각이긴 하죠.

사실 전 이미지넷보다는 디텍션이나 세그먼테이션 같은 다운스트림 과제로 넘어갔을 때의 퍼포먼스에 주목해야하지 않을까 싶긴 합니다. 다만 mlp 구조 중에 이쪽으로 넘어갈 수 있는 친구들이 거의 없는 상태죠.

#cnn #transformer #mlp #backbone