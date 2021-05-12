최근 트위터에서 화제가 됐던 논문을 하나 소개.

https://arxiv.org/abs/2007.08902

t-SNE (http://www.jmlr.org/papers/v9/vandermaaten08a.html) 같은 (주로 시각화를 위한) dimensionality reduction 모델들은 시각화가 필요한 상황에서 아주 강력한 도구다. 비교적 최근에는 UMAP (https://arxiv.org/abs/1802.03426)이 인기 끌었고 ForceAtlas2 (https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0098679)도 인기가 있는 모양이다. (ForceAtlas2는 그래프 레이아웃 알고리즘 정도로 생각했었는데...사실 이런 형태의 시각화에도 쓰지 못할 이유가 전혀 없긴 하다.)

이런 방법들은 같은 클러스터를 묶어주고 다른 클러스터와 분리시켜준다는 점에서 패턴이 비슷해보이면서도 결과의 형태가 전반적으로 다르다. 왜 그럴까? UMAP 같은 경우에는 loss 등이 달라서 그런 것이 아닌가 하는 생각이 일반적이었던 것 같다. (https://towardsdatascience.com/how-exactly-umap-works-13e3040e1668)

이 논문은 이 방법들의 차이가 attraction-repulsion 사이에서 균형을 어디에 맞추는가의 차이였다고 분석한다. attraction은 근접한 점들끼리 끌어당기는 힘이고 repulsion은 모든 점들 사이에 작용하는 미는 힘이다. 그렇다면 이 균형을 조절할 수 있는 파라미터가 있는가? t-SNE에서는 early exagerration이라는 트릭이 사용된다. 학습 초기에 점들 사이의 인접성을 반영하는 term을 키워주는 역할을 하고 이것이 최적화를 더 쉽게 해준다는 것이었다. 그런데 이게 (원 논문에서도 어느정도 시사되었다고 할 수 있을 듯 하지만) 임베딩의 결과에 중요한 영향을 미친다는 것이다. exagerration이 강해지면 attraction이 강해지고 exagerration이 감소하면 repulsion이 증가한다.

이 exagerration을 증가시켜 attraction을 높여주면 t-SNE에서도 UMAP이나 ForceAtlas2와 같은 패턴이 나온다! (더 증가하면 laplacian eigenmap (https://papers.nips.cc/paper/1961-laplacian-eigenmaps-and-spectral-techniques-for-embedding-and-clustering)과 같은 형태가 된다.) 즉 UMAP이나 ForceAtlas2가 보여주는 패턴은 t-SNE보다 attraction이 좀 더 강했기 때문이다.

그렇다면 UMAP에서 attraction이 더 강한 이유는 뭘까? 논문의 저자들이 제안하는 이유는 loss 같은 formulation의 차이가 아니라 (이 차이는 적은 것 같다고 주장한다.) 학습의 효율성을 위해 적용된 negative sampling 때문이었다는 것이다. 따라서 negative sample의 샘플을 늘리거나 혹은 negative sampling 자체를 없애면 attraction이 감소하고 (일반적인) t-SNE 같은 패턴이 나타난다.

즉 이 방법들이 아주 많은 차이를 가지고 있는 것처럼 보였고 그렇게 생각되어왔지만 실제로는 하나의 스펙트럼에 있었고, 실제로 보여진 차이들은 오히려 우연에 가까운 요소에 크게 영향을 받은 결과였다는 것이다. 꽤 충격적인 결과가 아닌가?

(좀 더 나아가서 생각하면 뉴럴넷 판의 매운 맛도 이런 식은 경우가 적지 않다고 생각할 수 있겠다. 우리가 생각하는 이유는 실제로는 그렇게 중요하지 않을 수 있고 유의미한 차이 또한 생각하지 못한 이유에서 온 것일 수 있다는 것이다. 예를 들면 이런 경우? https://arxiv.org/abs/2003.08505)

또한 네거티브 샘플링은 상당히 널리 쓰이는 방법인데 네거티브 샘플링이 단순한 근사 이상의 의미가 있다고 한다면 그에 대해 좀 더 생각해보는 것이 의미가 있을 듯. 사실 메트릭 러닝 같은 영역에서는 이전부터 중요한 문제가 아니었나 싶다.

#review