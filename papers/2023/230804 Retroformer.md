https://arxiv.org/abs/2308.02151

Retroformer: Retrospective Large Language Agents with Policy Gradient Optimization (Weiran Yao, Shelby Heinecke, Juan Carlos Niebles, Zhiwei Liu, Yihao Feng, Le Xue, Rithesh Murthy, Zeyuan Chen, Jianguo Zhang, Devansh Arpit, Ran Xu, Phil Mui, Huan Wang, Caiming Xiong, Silvio Savarese)

reflexion과 같은 선상에서 llm이 action을 취하고 그 action에 대한 결과를 토대로 llm의 action을 개선하는 피드백 루프를 구성했군요. 여기서는 llm의 action과 그 결과, 메모리를 종합해 llm에 주입할 프롬프트를 생성하는 lm을 놓고 이 lm을 rl 기반으로 학습시켰습니다. actor는 고정해놓은 채로 actor가 과거의 시도를 기반으로 planning을 하고 새로운 시도를 할 수 있게 하는 부분을 lm과 rl로 구현했다고 볼 수 있겠네요.

뭐 그런데 이런 프레임워크의 핵심은 피드백 루프 이상으로 reward의 존재 자체라는 생각이 드네요. reward를 확보할 수 있다면 많은 것이 가능하겠지만 reward를 확보하기 어렵다면 문제가 어려워지겠죠. 그런 의미에서는 풀기 원하는 문제에 대해 reward를 구성하는 것 자체 중요하지 않을까 싶습니다.