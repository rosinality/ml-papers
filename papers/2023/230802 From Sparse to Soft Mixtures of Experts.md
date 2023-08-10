https://arxiv.org/abs/2308.00951

From Sparse to Soft Mixtures of Experts (Joan Puigcerver, Carlos Riquelme, Basil Mustafa, Neil Houlsby)

sparse routing 대신 softmax를 사용한 soft routing으로, N개의 클러스터(슬롯)으로 토큰을 묶은 다음 각 클러스터에 각각의 expert network를 사용하는 방식이네요. 흥미롭긴 한데 lm 같은 케이스에는 적용하기 어렵겠군요.

#moe 