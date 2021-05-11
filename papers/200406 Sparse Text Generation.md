https://arxiv.org/abs/2004.02644

Sparse Text Generation (Pedro Henrique Martins, Zita Marinho, André F. T. Martins)

lm에서 generation을 할 때 문제가 생기는 이유 중 하나가 분포의 꼬리 부분의 확률 때문이라고 알려져 있고 이 문제에 대해 top-k 혹은 nucleus sampling이 많이 쓰이고 있음. 그런데 분포의 꼬리가 문제라면 sparsemax 같은 방법을 사용해서 분포 자체를 sparse하게 만들면 되지 않을까? 하는 아이디어.

#language_generation #language_model #sampling 