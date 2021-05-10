https://arxiv.org/abs/2007.03074

Kernel Stein Generative Modeling (Wei-Cheng Chang, Chun-Liang Li, Youssef Mroueh, Yiming Yang)

sgld가 날아오르는 동안 svgd는 여러 문제들로 인해 그러지 못했음. ncsn(https://arxiv.org/abs/1907.05600)에서 sgld에서 데이터 분포가 low density region으로 분리되어 있을 때 mixing이 느려지는 것을 노이즈를 도입해서 해소했지만 이 방법도 svgd에는 잘 통하지 않음. 이 문제의 원인이 노이즈 수준에 대해서 커널이 고정되어 있다는 것에 기인한다고 착안해 노이즈 수준에 대한 커널 러닝을 도입. #sgld #svgd