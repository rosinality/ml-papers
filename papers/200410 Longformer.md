https://arxiv.org/abs/2004.05150

Longformer: The Long-Document Transformer (Iz Beltagy, Matthew E. Peters, Arman Cohan)

장거리 self attention. 단순하게 attention mask에 패턴을 만드는 방식으로 접근. 속도 향상을 위해서 커스텀 커널을 만들었는데 파이썬으로 TVM 코드를 만들고 TVM으로 커널을 컴파일해서 파이토치에 바인딩하는 방식. TVM이 flops를 실제 속도로 바꿔주는 위력을 발휘한다는 것을 생각하면 여러모로 유용하지 않을지.