https://arxiv.org/abs/2308.04014

Continual Pre-Training of Large Language Models: How to (re)warm your model? (Kshitij Gupta, Benjamin Thérien, Adam Ibrahim, Mats L. Richter, Quentin Anthony, Eugene Belilovsky, Irina Rish, Timothée Lesort)

continual pretraining에 대한 탐색이 나왔군요. 주요한 포인트는 warm up을 다시 할 것인가, max learning rate를 바꾸는 것에 따라 새로운 데이터셋과 이전 데이터셋에 대한 성능이 어떻게 변화하는지에 대한 관측이네요.

결과적으로 다시 learning rate를 좀 높여준 다음 decay 하는 것이 새로운 데이터셋에 대해 성능을 확보하는데 필요하긴 하고, learning rate scheduling을 어떻게 하건 결과적으로 이전 데이터셋에 대한 성능에 타격이 오는 것은 어쩔 수 없네요.

일단 단순히 infinite learning rate scheduling을 쓰는 것으로는 잘 안 될 수도 있겠다는 생각이 드네요. 성능 저하는 mixture를 잘 구성해서 대응이 가능하지 않을까 싶기도 합니다. 물론 별 효과가 없을 가능성도 있지만요.

#pretraining