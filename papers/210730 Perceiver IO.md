https://arxiv.org/abs/2107.14795

Perceiver IO: A General Architecture for Structured Inputs & Outputs (Andrew Jaegle, Sebastian Borgeaud, Jean-Baptiste Alayrac, Carl Doersch, Catalin Ionescu, David Ding, Skanda Koppula, Andrew Brock, Evan Shelhamer, Olivier Hénaff, Matthew M. Botvinick, Andrew Zisserman, Oriol Vinyals, João Carreira)

딥 마인드 선생님들이 퍼시버가 마음에 들었나 보네요. 퍼시버에 출력을 위한 쿼리 임베딩을 레이턴트 임베딩과 어텐션으로 연결해서 출력 형태의 다양화를 추가한 모델입니다. 그래서 IO이기도 하고요. 예를 들어서 utf-8 바이트 시퀀스에 대해 그냥 bert 트레이닝을 해버린다거나 하는 것이 가능합니다.

어떻게 보면 모두가 꿈꾸는 만능 모델에 가까운 형태가 트랜스포머 덕분에 좀 더 단순한 형태로 설계될 수 있었다고 생각할 수 있겠네요.

#transformer 