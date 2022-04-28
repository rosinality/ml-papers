https://arxiv.org/abs/2105.01601
트랜스포머로 되니까 mlp로는 안 되는가 하는 생각을 하는 것이 자연스럽긴 함. 토큰별 mlp + 각 토큰을 input dim으로 해서 동작하는 (토큰 sequence를 transpose한) mlp로 이미지 분류하기. 당연하게도 vit보다 오버핏이 심하게 발생. 그렇지만 데이터 수를 끌어올리면 이것도 태클이 가능.
개인적으로 흥미로운 부분은 이쪽은 트랜스포머와 달리 원칙적으로는 linear complexity가 가능하다는 것. 물론 실질적으로는 input sequence의 길이가 길어지면 hidden dim의 크기도 커져야 할 것이니 quadratic complexity에 가까워지겠지만...어쨌든 self attention의 quadratic complexity에 대해 시사하는 바가 있을 듯 싶다. funnel transformer의 input sequence를 축소하는 접근도 좀 생각나고.

#review