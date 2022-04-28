https://arxiv.org/abs/2010.10241

BYOL works even without batch statistics (Pierre H. Richemond, Jean-Bastien Grill, Florent Altché, Corentin Tallec, Florian Strub, Andrew Brock, Samuel Smith, Soham De, Razvan Pascanu, Bilal Piot, Michal Valko)

BYOL([https://arxiv.org/abs/2006.07733](https://arxiv.org/abs/2006.07733))이 동작하는 이유가 batch norm에 의해서 일종의 contrast가 발생하기 때문이라는 주장([https://untitled-ai.github.io/understanding-self-supervised-contrastive-learning.html](https://arxiv.org/abs/2006.07733))이 나왔었는데 다시 딥마인드에서 batch norm 없이도 initialize만 잘 하면 학습이 가능하고 group norm + weight standardization으로 batch norm에 근접한 성능을 달성하는 것이 가능하다고 보고.오 재미있네! 그런데 그래서 대체 BYOL은 무엇인 걸까?

#contrastive_learning 