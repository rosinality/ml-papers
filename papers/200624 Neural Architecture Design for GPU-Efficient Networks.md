https://arxiv.org/abs/2006.14090

Neural Architecture Design for GPU-Efficient Networks (Ming Lin, Hesen Chen, Xiuyu Sun, Qi Qian, Hao Li, Rong Jin)

보틀넥이나 dw conv는 베이직 블록(XX block)의 low rank 근사라고 생각할 수 있음. 그러면 베이직 블록이 full rank에 가까운 레이어에서는 베이직 블록을 쓰는 것이 낫지 않을까? 이 아이디어로 full rank에 가까운 낮은 계층에서는 베이직 블록을 쓰고 위쪽 계층에서는 보틀넥이나 dw conv를 사용. 결과적으로 같은 성능에서 GPU 추론이 훨씬 빠른 네트워크를 설계. 좋은 결과!