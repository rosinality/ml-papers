https://github.com/Stability-AI/StableLM

이미 많은 분들이 뉴스를 전하셨기에 추가 사실만 기록하자면...

1. 라이센스는 CC BY-SA입니다. 동일조건 변경허락이라 아마 모델을 업데이트해서 뭔가를 하면 모델을 공개해야 하는 구조일 것 같은데...나름 제약이 될 수도 있겠군요. (모델은 그대로 두고 어댑터만 쓴다거나 하면 어떻게 되는지 궁금하네요.) 상업적 이용은 지금도 가능합니다. 분위기상 좀 더 포용적인 라이센스로 넘어갈 가능성도 있어 보이네요.
2. The Pile 기반 1.5T 토큰 분량 데이터셋을 썼다고 하는데 The Pile V2는 아닌 것 같습니다. 800B에서 학습이 멈춰있는데 오버피팅이 발생해서 멈춘 것이라고 하네요. duplicate 문제인 것 같고 수정 후 계속 진행될 모양입니다.

데이터셋 퀄리티와 관련해서 redpajama도 썩 좋지 않은 것 같다는 썰이 있군요. 아마 LLaMA와 거의 맞췄을 것 같은데 가능한 문제는 잘 모르겠습니다. 역시 The Pile V2도 지켜보는 게 필요할 것 같네요.