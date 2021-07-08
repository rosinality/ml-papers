https://arxiv.org/abs/2106.12423

Alias-Free Generative Adversarial Networks (Tero Karras, Miika Aittala, Samuli Laine, Erik Härkönen, Janne Hellsten, Jaakko Lehtinen, Timo Aila)

stylegan2의 후속은 alias free gan. 문제 의식은 generator가 hierarchical한 구조를 갖고 있긴 하지만 coarse level feature가 fine level feature의 feature를 대략 지정해주기는 하지만 정확한 위치를 지정해주는 형태로 학습되지는 않는다는 것이다. 그렇다면 fine level feature가 어딘가에서 position 정보를 주워와서 써먹는다는 이야기가 된다.

첫 번째 이유는 패딩이 되겠다. 다음 이유는 aliasing이다. alias free gan은 generator의 aliasing을 철저하게 억제해서 모델을 translation/rotation에 대해 equivariant하게 만들었다.

fid나 샘플 하나의 퀄리티만 보면 stylegan2와 별 차이가 없다. 사실 stylegan2와 비슷한 fid를 뽑기 위해 많은 노력을 하기도 했다. 그러나 latent space의 거동은 완전히 다르다. 이건 직접 봐야 이 강렬한 느낌이 느껴지니 위 페이지(https://nvlabs.github.io/alias-free-gan)에서 영상을 한 번 보시길...stylegan2가 갑자기 오징어로 보이면서 이런 모델을 지금까지 썼다고? 하는 생각이 들게 만든다.

#gan #antialiasing 