https://arxiv.org/abs/2307.06945

In-context Autoencoder for Context Compression in a Large Language Model (Tao Ge, Jing Hu, Xun Wang, Si-Qing Chen, Furu Wei)

long context 대응을 위한 방법. lm을 인코더로 삼아 context를 밀어넣고 몇 개 토큰으로 압축한 다음 그걸 lm에 입력하는 방법. 계속 나오는 context를 압축하려는 시도이긴 하죠. 일단 저는 토큰을 그대로 쓰는 것보다는 임베딩을 쓰는 쪽이 맞긴 맞지 않나...싶습니다.

MS에서 나왔는데 이쪽에서도 정말 온갖 방법을 다 해보고 있다는 생각이 드네요. Anthropic이 100K를 찍는 걸 보면 사실 이 문제에 대응하는 정석적인 방법은 이미 알음알음 알고 있을 것 같은데...

#llm 