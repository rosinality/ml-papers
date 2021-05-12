Denoising Diffusion Probabilistic Models (https://arxiv.org/abs/2006.11239)을 만들어서 돌려봤다. 모델의 기본적인 아이디어는 데이터 분포에서 다루기 편한 분포(가우시안)으로 전이하는 마르코프 체인(forward process)을 생각한 다음 이에 대한 반대 과정을 생각한다(reverse process). 이 반대 과정은 심플한 분포에서 데이터 분포로 이어지는 과정이므로 이걸 활용해 데이터의 확률을 계산할 수 있다. 여기에 forward process를 끼워넣어 variational lower bound를 구성하고 forward process의 분산이 0으로 가는 극한에 대해 reverse process와 동일한 함수형이 된다는 것을 활용한다. 이 논문은 이 프레임워크에 새로운 parameterization을 도입해 성능을 끌어올렸다.
상당히 산뜻하고 인상적인 결과를 보여준 접근이다. 최근 나온 NCSN의 개선 버전(https://arxiv.org/abs/2006.09011)도 그렇고 요즘 생성 모형에 대한 새로운 접근들이 보통 까다로운 높은 해상도의 이미지에 대해서 좋은 샘플 퀄리티를 보여주기 시작했다. 물론 생성 모델의 성능에서 샘플 퀄리티는 일부이긴 하지만 그래도 샘플 퀄리티가 좋아야 작업이 더 재미있으니까. ㅋㅋ
이런 모델들이 학습이 까다로운데 마찬가지로 까다로운 GAN의 안정화를 위해 널리 사용되기 시작한 ema 등이 꽤 도움이 됐다는 것도 재미있는 점.

[[200619 Denoising Diffusion Probabilistic Models]]

#review