https://arxiv.org/abs/2105.14217

Less is More: Pay Less Attention in Vision Transformers (Zizheng Pan, Bohan Zhuang, Haoyu He, Jing Liu, Jianfei Cai)

트랜스포머로 구성한 피라미드에서 stride가 작은 앞부분은 attention 대신 mlp를 쓰기. vit에서 16x16 패치를 썼던 걸 생각하면 뒷부분만 attention에 맡겨도 될 것 같긴 하죠.

#vit