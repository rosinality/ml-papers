https://arxiv.org/abs/2302.03686

Long Horizon Temperature Scaling (Andy Shih, Dorsa Sadigh, Stefano Ermon)

흠...흥미롭네요. autoregressive lm에서 temperature scaling을 한다고 하면 각 타임 스텝의 토큰의 logit을 temperature T로 scaling 해주는 방식으로 접근하죠. 그러나 이 접근은 각 토큰에 대한 scaling이지 전체 토큰 시퀀스에 대한 scaling, 즉 log(p(x))/T 는 아니라는 것에 대한 대안이네요. temperature에 대해 전체 샘플에 대한 distribution을 근사하도록 튜닝이 필요하긴 하지만 lm 뿐만 아니라 ddpm 같은 사례에도 적용이 가능하군요.

#calibration #lm #ddpm 