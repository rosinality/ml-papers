https://proceedings.neurips.cc/.../f885a14eaf260d7d9f93c7...
요즘 논문 읽기를 좀 게을리했는데 그 와중에 눈에 띈 논문. 기본적으로는 stylegan에 grouping 모듈을 붙인 모델. convolution weight에서 유사한 커널들을 같은 그룹으로 묶어서 그룹 구조를 스스로 학습하게 한다. 이렇게 학습된 그룹이 semantic한 구조를 반영하게 되고, 이 그룹 구조를 활용한 adaptive instance norm과 adaptive group norm을 동시에 사용해서 feature modulation을 수행한다. 여기에 추가적으로 infogan loss도 붙여주고.
상당히 흥미로운 접근인 동시에 인상적인 결과. 저자들의 주장에 따르면 stylegan에서 고질적으로 나타나는 아티팩트들 또한 제거할 수 있는 것으로 보이는데...stylegan2를 잇는 새로운 베이스라인이자 sota 모델이 될 수 있을지도.

#review