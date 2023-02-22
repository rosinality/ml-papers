https://arxiv.org/abs/2302.04931

In-Context Learning with Many Demonstration Examples (Mukai Li, Shansan Gong, Jiangtao Feng, Yiheng Xu, Jun Zhang, Zhiyong Wu, Lingpeng Kong)

transformer lm의 context length가 그리 넉넉하지 않은데 in-context learning을 위해 프롬프트와 예제를 추가하다보면 더 부족해지죠. 그 문제에 대한 제안이네요. 사실 핵심은 long-range efficient attention과 efficient attention의 locality + ciruclar positional embedding을 사용한 length extrapolation입니다. 여기서 efficient attention으로는 EVA (https://arxiv.org/abs/2302.04542) 를 썼습니다. (놀랍게도 저자가 한 명 빼고 안 겹치네요.)

EVA 논문의 설명이 복잡하긴 한데 이 논문의 요약을 따르자면 청킹 / 청크 밖 원격 feature 내에 efficient attention과 pooling, remote feature와 청크 내 feature에 대한 plain attention 조합이군요. 이 설명으로는 window attention + long rang feature의 조합으로 보이네요.

지금 openai나 구글에서는 context length 문제에 대해 어떻게 대응하고 있는지 궁금하긴 합니다. (그냥 gpt-3 그대로일까요?)

#efficient_attention #transformer 