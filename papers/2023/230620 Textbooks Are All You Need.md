https://arxiv.org/abs/2306.11644

Textbooks Are All You Need (Suriya Gunasekar, Yi Zhang, Jyoti Aneja, Caio César Teodoro Mendes, Allie Del Giorno, Sivakanth Gopi, Mojan Javaheripi, Piero Kauffmann, Gustavo de Rosa, Olli Saarikivi, Adil Salim, Shital Shah, Harkirat Singh Behl, Xin Wang, Sébastien Bubeck, Ronen Eldan, Adam Tauman Kalai, Yin Tat Lee, Yuanzhi Li)

1.3B 모델 + 7B 토큰으로 HumanEval 50.6% 달성. 대부분의 코드 데이터가 정보량이 크지 않거나, 코드 자체만으로는 이해하기 어려운 케이스가 많으니 이런 코드들을 필터링하고 6B 정도 뽑아온 다음, GPT-3.5로 교과서적인 형태의 파이썬 예시들과 파이썬 문제들을 1B, 180M 정도 생성한 다음 이걸로 모델을 학습시켰군요.

논문에서도 언급하는 것처럼 GPT-3.5를 경유해서 data leak이 있을 가능성이 있을 것 같긴 한데...여하간 흥미롭네요.

#llm 