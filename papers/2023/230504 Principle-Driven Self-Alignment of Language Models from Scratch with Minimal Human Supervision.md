https://arxiv.org/abs/2305.03047

Principle-Driven Self-Alignment of Language Models from Scratch with Minimal Human Supervision (Zhiqing Sun, Yikang Shen, Qinhong Zhou, Hongxin Zhang, Zhenfang Chen, David Cox, Yiming Yang, Chuang Gan)

수백 라인 정도의 어노테이션으로 LLM align. 주제 기반으로 LLM이 답하기 어려운 instruction을 LLM으로 생성, 사전에 지정된 원칙을 사용해 LLM으로 적절한 응답을 생성, 프롬프트들을 제거한 다음 만들어진 대화 기록으로 파인튜닝, 그리고 이후 적절한 스타일의 응답을 생성하도록 프롬프트를 주고 생성된 대화로 Distill 하는 순서로 진행합니다.

여러모로 사람이 직접 어노테이션한 Open Assistant 등에 비해서는 밀리는 듯 하지만 꽤 흥미로운 접근으로 보이네요.

#alignment 