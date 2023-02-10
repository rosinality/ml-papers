https://arxiv.org/abs/2302.00093

Large Language Models Can Be Easily Distracted by Irrelevant Context (Freda Shi, Xinyun Chen, Kanishka Misra, Nathan Scales, David Dohan, Ed Chi, Nathanael Schärli, Denny Zhou)

엉뚱한 문장이 끼어들었을 때 llm의 in context learning 성능이 감소하는 것에 대한 벤치마크와 대응 방법에 대한 탐색이군요. 가장 괜찮은 것은 sub program으로 문제 분해 + chain of thought + 여러 답을 샘플링하고 majority voting인 것 같긴 하네요. (least-to-most prompting + self-consistency).

#llm #in_context_learning 