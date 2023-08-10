https://arxiv.org/abs/2303.03846

Larger language models do in-context learning differently (Jerry Wei, Jason Wei, Yi Tay, Dustin Tran, Albert Webson, Yifeng Lu, Xinyun Chen, Hanxiao Liu, Da Huang, Denny Zhou, Tengyu Ma)

in context learning에서 train set의 label (positive/negative)을 flip하면 semantic prior에 강하게 의존하는 모델은 여전히 flip 되지 않은 예측을 할 것이고 케이스와 지시에 따를 수 있는 모델은 semantic prior를 거슬러서 flip된 예측을 할 수 있겠죠. semantic prior를 덮어쓰고 지시에 따르는 현상이 일정 규모 이상의 모델에서만 나타난다는 결과입니다. 비슷하게 label을 엉뚱하게 (foo/bar) 제공했을 때에도 큰 모델에서만 이에 맞게 작동하는 현상이 나타납니다. 늘 그랬듯 크기는 곧 질이죠.

그러나 한 가지 규명되고 있지 않은 것은 학습 토큰 수에 따른 변화일 것 같네요. chinchilla vs palm에 대한 결과는 있으니 추측은 가능하지만 확정적이지는 않지 않은가 싶습니다.

#llm #in_context_learning 