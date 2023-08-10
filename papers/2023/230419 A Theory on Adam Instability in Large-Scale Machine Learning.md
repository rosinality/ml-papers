https://arxiv.org/abs/2304.09871

A Theory on Adam Instability in Large-Scale Machine Learning (Igor Molybog, Peter Albert, Moya Chen, Zachary DeVito, David Esiobu, Naman Goyal, Punit Singh Koura, Sharan Narang, Andrew Poulton, Ruan Silva, Binh Tang, Puxin Xu, Yuchen Zhang, Melanie Kambadur, Stephen Roller, Susan Zhang)

adam으로 대규모 모델을 학습할 때 불안정성이 발생하는 이유는? 그래디언트가 시간에 따라 독립적이지 않고 correlation이 생기면서 결과적으로 업데이트가 bimodal 해지는 것을 원인으로 보고 있군요. 추정하는 문제의 흐름은 다음과 같습니다:

1. 처음에는 업데이트가 unimodal하게 시작됨.
2. 학습이 진행되면서 특정, 특히, 앞 부분 레이어의 그래디언트가 감소하기 시작.
3. first, second order momentum이 감소하기 시작.
4. 업데이트가 감소하면서 그래디언트 사이에 상관이 높아지기 시작.
5. first/second order momentum의 비례가 bimodal해지기 시작함. 아직 eps가 들어간 업데이트는 unimodal.
6. 나머지 부분의 weight는 업데이트 되고 있기 때문에, 앞 부분 레이어 또한 업데이트 되어야 할 필요가 생김.
7. 업데이트가 bimodal 분포로 바뀜.
8. 그래디언트가 증가하면서 상관이 감소하기 시작함.
9. 학습이 다시 정상화됨.

6번 단계에서 학습이 폭발하는 현상이 나타난다고 하네요. 바로 관련되어서 생각나는 것은 초기 단계의 activation이 증가하는 것이 네트워크 전체로 퍼져나가고, 그 시점에서 학습이 폭발한다는 관측들과 weight norm이 계속해서 증가하는 현상 (AdamP, https://arxiv.org/abs/2006.08217) 인데 어떤 관계가 있을지는 바로는 잘 모르겠네요. 뭔가 이 부분에 대한 해결책이 나올 수 있을 것 같은데...좀 기다려보면 결과가 나오지 않을까 싶습니다.

여하간 작은 모델에서는 잘 나타나지 않는 현상이라는 것 같습니다. 여담이지만 최대 크기 모델로 테스트한 것이 7B, 30B, 65B, 546B이고 학습을 꽤 진행한 것을 보면 메타에서 500B 수준의 LLaMA를 학습해보고 있는 모양이네요.

#optimizer #llm 