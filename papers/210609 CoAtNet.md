https://arxiv.org/abs/2106.04803

CoAtNet: Marrying Convolution and Attention for All Data Sizes (Zihang Dai, Hanxiao Liu, Quoc V. Le, Mingxing Tan)

stride 4, 8은 mbconv에 맡기고 16, 32는 attention을 도입. conv + attention = attention + relative attention이라는 transformer-xl 저자스러운 아이디어. imagenet scratch로 86%, imagenet 21k pretraining으로 88.6%를 찍었군요. 이 저자들에게는 비전이 너무 쉬운 게 아닌지.

#vit