Implicit Generation and Generalization in Energy-Based Models (https://arxiv.org/abs/1903.08689) 를 구현해봤다. 아직 더 트레이닝을 해봐야겠지만 일단 그림 같아 보이는 것이 나오기는 한다. 형체가 좀 더 온전하게 나오자면 더 시도를 해봐야할 것 같긴 하지만...
energy based model은 p(x) = exp(-E(x)) / Z 형태로 분포를 정의하는 모형이다. 왜 E(x)가 아니라 -E(x)인지 이걸 또 왜 에너지라고 부르는가 하면 이 친구의 출처 혹은 기원이 물리학(통계역학)이기 때문이다.
딱 보면 이런식으로 모델링된 분포에서 샘플을 뽑는 것이 만만찮다는 것을 알 수 있다. 샘플 하나를 주면 (정규화되지도 않은) 확률값을 던져주는 모델로 샘플을 만들어야 한다. GAN 같은 친구들은 확률이 직접 나오진 않아도 샘플을 잘 찍는 걸로 대성공했는데!
아주 단순하게 생각하면 모든 가능한 샘플을 만든 다음에 값을 뽑아보면 되겠다. 그러나 이게 이미지 같은 고차원 데이터에는 통할 리 없으니 좀 더 효율적인 방법을 생각해보게 된다. MCMC가 바로 그런 방법이다.
그러나 깁스 샘플링 같은 전통적인 방법들로는 여전히 이미지 같은 샘플을 뽑기에는 한세월이 필요하다. 그래서 이 논문에서 쓴 방법은 SGLD, Stochstic Gradient Langevin Dynamics이다. (이름 한 번 끝장나게 멋있다. 스토캐스틱 그래디언트 랑주뱅 다이내믹스! 역시 물리학자들이 붙인 이름이라 그렇다.) 아주 복잡하지는 않고 [다음 샘플 = 현재 샘플 + 에너지 함수의 샘플에 대한 그래디언트 + 약간의 노이즈] 와 같은 접근으로 샘플을 계산해낸다.
샘플을 그럭저럭 효율적으로 뽑아낼 수 있게 됐으니 힌튼의 Contrastive Divergence를 쓸 수 있다. 실제 데이터에 대해 구한 E(x)는 낮추고 (-가 붙어있으니까) 모델로 뽑은 샘플에 대한 E(x)는 높여주면 된다.
저자도 언급하고 있지만 지금 기준으로 보면 WGAN과 비슷한 느낌? 다만 generator가 따로 있지는 않은. 사실 나온 순서로 보면 WGAN이 CD와 비슷하다고 해야겠지만.
물론 여기까지는 쉬운 말이고 이걸 실제로 돌아가게 만들자니 그래디언트 클리핑도 여기저기 끼워넣고 spectral normalization도 달고 리플레이 버퍼도 달고 에너지 함수가 펑 날아가지 않도록 loss를 좀 수정해주기도 했다.
거기다 샘플링이 비교적 효율적이긴 하지만 매 학습 스텝마다 60번씩 샘플 생성을 위한 작업을 해줘야 한다는 것도 좀 부담스러운 일이긴 하다.
어쨌든 그래도 돌아가고 그림이 나온다는 게 중요한 것이지만!

#energy_based_model #generative_model 