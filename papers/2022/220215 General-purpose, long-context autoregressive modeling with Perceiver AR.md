https://arxiv.org/abs/2202.07765

General-purpose, long-context autoregressive modeling with Perceiver AR (Curtis Hawthorne, Andrew Jaegle, Cătălina Cangea, Sebastian Borgeaud, Charlie Nash, Mateusz Malinowski, Sander Dieleman, Oriol Vinyals, Matthew Botvinick, Ian Simon, Hannah Sheahan, Neil Zeghidour, Jean-Baptiste Alayrac, João Carreira, Jesse Engel)

autoregressive perceiver. 입력 시퀀스를 lm 타겟 시퀀스의 앞에 붙여놓고 causal mask를 타겟 시퀀스와 입력 시퀀스 + 타겟 시퀀스 사이의 cross attention을 사용. 평이해보이기도 하는데 이 cross attention 레이어를 단 한 번 사용한다는 것이 특징적이네요.

#efficient_attention #lm #autoregressive_model 