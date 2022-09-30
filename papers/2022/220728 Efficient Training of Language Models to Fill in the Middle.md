https://arxiv.org/abs/2207.14255

Efficient Training of Language Models to Fill in the Middle (Mohammad Bavarian, Heewoo Jun, Nikolas Tezak, John Schulman, Christine McLeavey, Jerry Tworek, Mark Chen)

텍스트의 시작(prefix)과 끝 부분(suffix)이 주어졌을 때 중간 부분(middle)을 채워넣는 과제를 풀기 위한 lm 프리트레이닝. 아니 그런 문제를 왜 풀지 싶었는데 예를 들어 코드에서 docstring을 생성하기 같은 과제에 쓸 수 있다고 제안하네요.

방법은 프리트레이닝 시점에서 텍스트를 세 부분으로 잘라(prefix/middle/suffix) 순서를 바꾸고 토큰을 끼워넣는 형태입니다. (<pre> prefix <suf> suffix <mid> middle) 파인튜닝으로 하면 되지 않는가 싶지만 파인튜닝으로 성능을 내려면 생각보다 많은 학습량을 투입해야 한다고 하네요.

#lm #mlm 