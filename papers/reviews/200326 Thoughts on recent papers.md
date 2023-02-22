# 200326 최근 논문들에 대한 생각

요즘 기존의 연구와 방법들을 비판적으로 검토한 연구들이 여럿 나왔다. 내 입장에서야 흥미로운 결과들이지만 그 분야를 연구하던 사람들에게는 당혹스러운 것들일지도 모르겠다. 어떻게 보면 폭탄이 떨어진 것이라고 할 수 있지 않을까?

일단 메타러닝과 few shot learning부터 시작하면,

1. https://arxiv.org/abs/2003.11539

메타러닝 문제(few shot learning)를 메타트레이닝셋에 이미지 분류기를 학습시키고 그 학습된 모델에서 추출한 임베딩으로 few shot 학습을 시키는 것으로 풀기. 베이스라인에 가까운 전형적인 프리트레이닝-파인튜닝인데 기존의 복잡한 방법들보다 성능이 더 낫다.

비슷한 연구들이 이전에도 있었다: https://arxiv.org/abs/2003.04390 https://arxiv.org/abs/1904.04232
https://arxiv.org/abs/2003.06957

Frustratingly Simple Few-Shot Object Detection (Xin Wang, Thomas E. Huang, Trevor Darrell, Joseph E. Gonzalez, Fisher Yu)

이쪽은 few shot object detection. 프리트레이닝 후 box classifier/regressor만 학습시키고 나머지는 얼리는 간단한 파인튜닝으로 접근. 이것도 기존 방법들보다 잘 된다.

다음은 메트릭 러닝.

https://arxiv.org/abs/2003.08505

A Metric Learning Reality Check (Kevin Musgrave, Serge Belongie, Ser-Nam Lim)

그동안 메트릭 러닝에서 많은 방법, 모델, 특히 loss가 제안되어왔고 또 큰 성능 향상이 있었지만 여러 디테일을 맞추고 동등하게 비교해보니 실제로는 성능이 엇비슷하다는 연구.

https://arxiv.org/abs/2003.08983

Metric learning: cross-entropy vs. pairwise losses (Malik Boudiaf, Jérôme Rony, Imtiaz Masud Ziko, Eric Granger, Marco Pedersoli, Pablo Piantanida, Ismail Ben Ayed)

메트릭 러닝에서 흔히 쓰이는 pairwise loss들을 cross entropy와 연결. 잘 튜닝하면 특별한 샘플링 전략 없이도 cross entropy로 성능이 잘 나온다.

그리고 다른 사례들.

https://arxiv.org/abs/2003.03033

What is the State of Neural Network Pruning? (Davis Blalock, Jose Javier Gonzalez Ortiz, Jonathan Frankle, John Guttag)

뭔가 프루닝 연구들을 비교 정리하려다가 짜증나서 던지고 연구 좀 잘 하자로 방향을 튼 논문인 듯. 기존 프루닝 연구들을 제대로 공정하게 비교하는 것이 어렵다는 문제를 지적.

https://arxiv.org/abs/2003.04297

Improved Baselines with Momentum Contrastive Learning (Xinlei Chen, Haoqi Fan, Ross Girshick, Kaiming He)

SimCLR의 개선들을 MOCO에 붙였더니 MOCO가 더 낫더라.

https://arxiv.org/abs/2003.11154

A Systematic Evaluation: Fine-Grained CNN vs. Traditional CNN Classifiers (Saeed Anwar, Nick Barnes, Lars Petersson)

이쪽은 fine grained 이미지 분류 문제에서 특화 모델에 비해 일반적인 분류 모델이 성능이 오히려 낫더라는 보고.
공통적으로 지적되는 문제들은,

1. 이전 연구와의 비교가 공정하지 않다.
2. 베이스라인 혹은 베이스라인에 가까운 방법들이 충분히 탐색되지 않았거나 튜닝되지 않았다.
3. 그런데 더 복잡하고 정교한 방법들이 제안되었고 또한 그 방법들에 의해서 성능이 진전되는 것으로 나타났다.
라고 할 수 있겠다. speech recognition에 대해 들었던 이야기가 생각난다. 모든 논문들이 wer을 조금씩 낮추는데 성공했다고 보고하고 있는데, 그 방법들을 합치면 speech recognition 문제가 풀렸어야 하는 게 아닌가? 그런데 왜 그렇지 않았나?

학계와는 좀 비껴있는 입장에서 학계에 대해 뭐라고 왈가왈부하는 것이 적절할지는 모르겠다. 다만 더 새롭고 정교한 방법들에 대한 추구 뿐만 아니라 더 정확하고 엄밀한 결과들에 대한 노력이 필요하지 않나 싶다. 물론 더 많은 성과를 더 빠르게 내는 방향으로 유인이 작동하니 쉽지 않겠지만...

이런 사례들은 학계에 참여하는 사람들 뿐만 아니라, 기존 성과들을 활용하는 사람들에게도 몇 가지 교훈을 준다. 아니 실용적으로는 이런 사람들에게 오히려 더 유용할지도 모르겠다.

1. 기존의 잘 검증된, 단순하고 널리 통용되는 방법을 가장 먼저 고려해야 한다. 그리고 이 방법을 충분히 튜닝해볼 필요가 있다.
2. 새로운 방법이 다른 방법과 조합되었을 때에도 동일한 성능 향상을 가져오지 못하는 경우가 많다. 이건 서로 다른 방법들이 비슷한 문제를 풀고 있는 경우가 많기 때문이다.
3. 따라서 새로운 방법에 대해서 종합적인 평가를 할 필요가 있는데, 이건 누가 대신 해주는 경우는 드문 듯 하고 실제로 그 방법을 사용하는 사람들이 수행하고 경험을 쌓아야 할 듯 싶다.
4. 이런 점들을 고려했을 때에도 문제에 대해 좋은 성능 향상을 보여주는 방법은 "진짜"다...
5. 프리트레이닝-파인튜닝은 많은 문제들을 푸는데 도움을 줄 수 있는 강력한 베이스라인이다. 파인튜닝도 그냥 통째로 트레이닝을 시키는 것이 아니라 좀 더 섬세한 방법을 사용할 필요가 있다. 즉 파인튜닝 또한 튜닝해야 한다.
6. 뉴럴넷 판의 격언. loss나 activation을 조절하는 것은 좀 조심하는 것이 좋다...

그리고 새로운 결과들을 볼 때 조심해야 한다고 생각되는 것들:

1. 안 되던 문제, 혹은 새로운 문제를 풀거나 혹은 기존 방법에 비해 확연한 성능 향상을 보여준 것은 의미있을 가능성이 높다.
2. 새로운 방법이 비교하고 있는 베이스라인들의 수치가 충분히 건전한지 체크해야 한다. object detection이라면 faster r-cnn의 성능이 제대로 나왔는지, 학습 스케쥴이 충분히 길었는지 등등. (예를 들어 1x 스케쥴로 보고된 성능은 좀 부족하다.)
3. 다른 방법과 조합했을 때도 성능 향상이 보이는지. 그리고 그것을 보고했는지. detection이라면 더 강력한 백본, dcn, 더 긴 학습 스케쥴에서도 성능 향상이 있는지.
4. 단순한 방법 선호. 오컴의 면도날 같은 기준 이전에 문제를 푸는데 적용하기도 쉬워진다.
5. 연구가 제시하고 있는 주된 방법 이외에 추가한 디테일들을 충분히 점검할 것
내가 생각하기에는 대충 이렇다. 새로운 방법을 꾸준히 수집하고 시도해봐야 하지만 연구 결과를 활용하는 사람들 또한 이러한 시도들을 통해 얻은 결과들을 엄밀하게 평가해야 한다. 그렇게 얻은 결과들이 새로운 문제를 푸는데 유용한 도구상자를 채워주는 것이므로...

#review 