# 210424 최근 논문들에 대한 생각

https://arxiv.org/abs/2104.11222

어떻게 보면 생각보다 알려지지 않은 이슈. (image restoration을 하던 사람들에게는 스코어 차이가 크게 나기 때문에 잘 알려져 있었던 것 같지만) opencv나 tensorflow(antialias=False), pytorch에서 resizing은 prefiltering이 없어 aliasing이 발생한다. 의외로 PIL의 구현이 괜찮다. 다만 이게 fid 계산에 큰 이슈일 것이라고는 생각하지 못했던 부분이 있었던 듯.

어떤 resizing 구현이 가장 정확한가 하는 것도 의문이긴 하다. matlab의 imresize가 괜찮다는 이야기는 들었는데, 논문에서 선호한 pil의 resize와 matlab의 imresize는 비슷해보이는 것 같으면서도 차이를 계산해보면 또 꽤 다르다. 그게 질적인 차이까지 유발하는지 아니면 그냥 동등한데 결과가 다른 것 뿐인지도 잘 모르겠고.



#review