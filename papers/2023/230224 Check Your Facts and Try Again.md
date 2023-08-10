https://arxiv.org/abs/2302.12813

Check Your Facts and Try Again: Improving Large Language Models with External Knowledge and Automated Feedback (Baolin Peng, Michel Galley, Pengcheng He, Hao Cheng, Yujia Xie, Yu Hu, Qiuyuan Huang, Lars Liden, Zhou Yu, Weizhu Chen, Jianfeng Gao)

retrieval augment 같은 문제는 이미 retrieve된 텍스트를 사용해 답을 강화한다를 넘어 retrieval과 llm을 어떻게 조합해 전체 시스템을 구성할 것인가의 문제로 넘어가고 있군요. retrieval 혹은 llm generation을 결정하는 policy, retrieve된 문서를 가공하는 모듈, llm에 생성 프롬프트를 제공하는 모듈, 생성 텍스트의 품질을 평가하는 모듈, 그리고 이 과정을 저장하는 모듈로 구성된 시스템이네요.

#retrieval #llm 