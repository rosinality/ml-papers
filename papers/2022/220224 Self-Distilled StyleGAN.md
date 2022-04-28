https://arxiv.org/abs/2202.12211

Self-Distilled StyleGAN: Towards Generation from Internet Photos (Ron Mokady, Michal Yarom, Omer Tov, Oran Lang, Daniel Cohen-Or, Tali Dekel, Michal Irani, Inbar Mosseri)

큐레이션이 되어있지 않은 데이터셋에서 gan 생성 이미지의 퀄리티를 향상시키기. 약간 대놓고 데이터 커버리지를 포기하고 이미지 퀄리티를 높인 느낌이네요. stylegan2와 인코더를 가지고 오토인코딩을 해서 원본 이미지와의 차이를 사용해 outlier를 필터링하고, truncation trick을 적용할 때 전체 latent의 평균/중심을 사용하는 게 아니라 latent를 n개 클러스터로 클러스터링한 다음 새로운 latent에 대해서 가장 가까운 클러스터 중심으로 truncation을 하는 방법을 썼네요.

#gan 