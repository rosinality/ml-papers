https://arxiv.org/abs/2304.03216

On the Pareto Front of Multilingual Neural Machine Translation (Liang Chen, Shuming Ma, Dongdong Zhang, Furu Wei, Baobao Chang)

multitask, 여기서는 multilingual nmt에서 loss weight에 성능이 monotonic하게 변화하는 것도 사실 이상적인 상황이고, training data의 수에 따라 loss weight를 증가시킬 수록 성능이 향상되다가 오히려 다시 감소하는 패턴이 나타날 수 있다는 지적이군요. 이를 커버하기 위해서는 데이터의 수를 고려하는 scaling law를 고려해야 한다는 주장. 흥미롭군요. llm 같은 경우는 1 epoch training이 기본이니 이 이슈에 해당되지는 않을 것 같긴 하지만요.

#multilingual #multitask #scaling 