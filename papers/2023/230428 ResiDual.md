https://arxiv.org/abs/2304.14802

ResiDual: Transformer with Dual Residual Connections (Shufang Xie, Huishuai Zhang, Junliang Guo, Xu Tan, Jiang Bian, Hany Hassan Awadalla, Arul Menezes, Tao Qin, Rui Yan)

transformer와 layer norm의 잔혹사에 다시 한 획이 추가됐네요. pre layer norm은 representation collapse, 즉 상위 레이어의 출력에 대한 기여 정도가 감소하는 문제가 있고, post layer norm은 gradient vanish가 있으니 이 둘을 합쳐 두 가지 경로를 동시에 유지한다...라는 발상이군요. 효과가 아주 크진 않은 것 같은데 layer norm을 두 개 사용하고 elementwise add가 몇 번 더 추가되는 것이 조금 아쉽긴 하네요.

별개로 비교 결과로 B2T라고 하는, post layer norm + skip conn 추가로 태클한 논문이 있는데 (https://arxiv.org/abs/2206.00330) 이것도 나쁘지 않아 보이네요.

#transformer #normalization 