https://arxiv.org/abs/2110.10819

Shaking the foundations: delusions in sequence models for interaction and control (Pedro A. Ortega, Markus Kunesch, Grégoire Delétang, Tim Genewein, Jordi Grau-Moya, Joel Veness, Jonas Buchli, Jonas Degrave, Bilal Piot, Julien Perolat, Tom Everitt, Corentin Tallec, Emilio Parisotto, Tom Erez, Yutian Chen, Scott Reed, Marcus Hutter, Nando de Freitas, Shane Legg

노골적인 제목.

expert가 생성한 액션들의 시퀀스를 관측하는 것(예: language model)만으로 모델이 액션들의 시퀀스를 생성할 수 있는가라는 문제. 액션 시퀀스의 관측 p(x_n|x_1:n-1)은 conditioning이고 액션 시퀀스 생성 p(x_n|do(x_1:n-1))은 causal intervention이기 때문에 관측되지 않은 confounder가 영향을 미치는 상황에서 이 둘 사이에는 차이가 발생하게 된다. observe된 시퀀스가 confounder에 대해 충분한 정보를 제공하는 상황이라면 차이가 감소할 수 있겠지만, 그렇지 않다면?

사람의 언어 생성은 특정한 환경에 대한 액션이고 거기에는 잠재 변수의 형태로 의도나 메시지 등의 변수가 영향을 미치고 있을 것이다. 그렇지만 우리가 언어 모델을 학습시키는 데이터는 이 영향을 미치는 변수들이 관측되지 않은 상황에서 사람들이 취한 액션들의 목록이다. 이 최종 결과물들을 학습하는 것이 액션을 생성하기에 충분한가 하는 문제에 대해서는 막연한 생각 정도만 있었는데 이 부분에 대해 명료하게 설명한 결과라고 할 수 있을 듯.

#lm #causality 