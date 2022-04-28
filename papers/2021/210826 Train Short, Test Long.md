https://ofir.io/train_short_test_long.pdf

Train Short, Test Long: Attention with Linear Biases Enables Input Length Extrapolation (Ofir Press, Noah A. Smith, Mike Lewis)

학습때 본 시퀀스 길이 이상에서도 작동하는 attention (positional encoding) 만들기. 더 복잡한 pe가 아니라 오히려 더 단순하게 relative position에 대한 고정된 scalar bias * 고정된 헤드별 scalar weight로 만들어놨습니다.

다만 이 extrapolation의 효과는 inference시에 더 긴 시퀀스에서 더 긴 context를 모델링하는 효과라기보다는 학습 당시에 본 길이만큼으로 attention을 억제하는 효과에 가깝긴 하네요. (다시 말해 다른 pe와는 달리 터지지 않는다는 쪽에 가깝습니다.) 모두가 꿈꾸는 context를 더 주면 더 잘 하는 모델은 여전히 쉽지 않을 것 같네요. (애초에 가능한 것인지 좀 의심스럽기는 합니다만...)

#positional_encoding #attention 