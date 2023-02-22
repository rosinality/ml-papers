https://arxiv.org/abs/2302.10688

On Calibrating Diffusion Probabilistic Models (Tianyu Pang, Cheng Lu, Chao Du, Min Lin, Shuicheng Yan, Zhijie Deng)

diffusion 모델의 reverse process에 들어오는 스코어 함수가 마팅게일이며 기대값이 0이 되어야 하는데 실제 스코어 함수를 근사하는 모델은 기대값이 0이 아니다, 따라서 기대값이 0이 되도록 조정해주면(calibration) 특성이 나아진다...그런 결과입니다. 일단 기대값을 빼주기만 하면 되는 느낌이라 재학습이 필요하지는 않군요.

sde로 formulation 되면서 확률맨들이 전가의 보도처럼 휘두르고 있군요. 무시무시.

#ddpm 