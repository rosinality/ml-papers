https://arxiv.org/abs/2306.15400

Length Generalization in Arithmetic Transformers (Samy Jelassi, Stéphane d'Ascoli, Carles Domingo-Enrich, Yuhuai Wu, Yuanzhi Li, François Charton)

트랜스포머의 계산에 대한 extrapolation 실험. 덧셈 같은 경우 relative positional encoding을 쓰면 기본적으로 숫자의 자리수 증가에 대해 generalization이 되는데 곱셈 같은 경우는 안 되는군요. 그런데 500 샘플 정도의 긴 자리수의 곱셈 예제를 추가해주면 또 잘 된다고 합니다. 트랜스포머에 곱셈을 수행하기 위한 구조가 어느 정도 형성되어 있다는 의미 같은데, 동시에 그걸 바로 활용하도록(extrapolation) 학습되지는 않는다는 것을 시사하는 듯 하네요.

#transformer 