https://arxiv.org/abs/2306.17563

Large Language Models are Effective Text Rankers with Pairwise Ranking Prompting (Zhen Qin, Rolf Jagerman, Kai Hui, Honglei Zhuang, Junru Wu, Jiaming Shen, Tianqi Liu, Jialu Liu, Donald Metzler, Xuanhui Wang, Michael Bendersky)

llm으로 query-passage 사이의 relevancy를 ranking. 적절한 prompt를 주고 passage a 혹은 b가 relevant한가를 묻는가 하는 일반적인 방식이지만 이 논문의 요점은 N개 passage가 있을 때 O(N^2) comparison을 피하는 것이네요. sorting에 착안해서 sorting 알고리즘 진행 과정의 comparator로 사용하는 방식을 사용했습니다.

#llm 