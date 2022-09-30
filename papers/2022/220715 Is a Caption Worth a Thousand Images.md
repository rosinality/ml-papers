https://arxiv.org/abs/2207.07635

Is a Caption Worth a Thousand Images? A Controlled Study for Representation Learning (Shibani Santurkar, Yann Dubois, Rohan Taori, Percy Liang, Tatsunori Hashimoto)

simclr vs clip. simclr이 나은 영역도 있고 clip이 나은 영역도 있는데 어떤 영역에서는 simclr의 사용 데이터가 증가해도 clip의 성능에 미치지 못하는 경우가 있네요. clip 성능에는 caption의 다양성과 퀄리티와 이미지 당 수가 중요하다고 하네요. lm을 써서 caption을 필터링하고 augment 하는 방식도 시도했습니다. 추가로 clip의 기본 augmentation이 아니라 simclr의 augmentation을 사용하는 것이 도움이 됐다고 합니다. (caption의 특성상 강한 augmentation을 쓰기가 좀 애매한 점이 있었는데 참고할만한 것 같습니다.)

물론 simclr이 아닌 보다 최근 ssl 알고리즘에서 어떨지가 궁금하긴 하네요.

#self_supervised #clip 