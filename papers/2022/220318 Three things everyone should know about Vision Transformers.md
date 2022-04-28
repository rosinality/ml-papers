https://arxiv.org/abs/2203.09795

Three things everyone should know about Vision Transformers (Hugo Touvron, Matthieu Cord, Alaaeldin El-Nouby, Jakob Verbeek, Hervé Jégou)

논문 제목 짓기가 새로운 경지에 도달했네요. 세 가지 사실은:

1. y = x + mhsa(x), z = y + ffn(y) 같은 방식으로 계속 쌓는 대신 y = x + mhsa(x) + mhsa(x), z = y + ffn(y) + ffn(y) 같은 식으로 모듈들을 병렬로 (약간 multi branch스럽게) 결합할 수 있다. 계산도 병렬로 잘 하면 더 빨라질지도? 입니다. gpt-j에서 y = x + mhsa(x) + ffn(x) 같은 접근을 사용한다던데 비슷한 것 같기도 하네요.
2. 파인튜닝 할 때 (특히 입력 크기가 달라질 때) mhsa만 튜닝해도 충분하다.
3. stride 16 patchify 레이어를 더 작은 stride를 가지는 patchify 레이어들로 쪼개는 것도 괜찮다(resnet-d 스럽게) 입니다.

#vit #backbone