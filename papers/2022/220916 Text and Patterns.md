https://arxiv.org/abs/2209.07686

Text and Patterns: For Effective Chain of Thought, It Takes Two to Tango (Aman Madaan, Amir Yazdanbakhsh)

chain of thought prompt를 구성하는 부분들의 역할에 대한 분석이군요. 일단 프롬프트를 세 가지 요소로 나눕니다.

1. 심볼. 모델이 과제를 수행하기 위해 추론하는 토큰. 
2. 패턴. 과제에 대한 이해를 촉진시켜주는 심볼과 연산자의 결합 방식과 구조.
3. 텍스트. 심볼도 패턴도 아닌, 이 두 요소들을 결합시켜주는 토큰.

예를 들어 Jamal Murray is a basket player. Being perfect from the line is part of baseball이라는 텍스트가 있으면,

1. 심볼: Jamal Murray, Being perfect from the line
2. 패턴: is (a) basketball (player), is (part of) basketball
3. 텍스트: (is) a (basketball) player, (is) part of (basketball)

같은 구조가 됩니다. 논문에서는:

1. 심볼을 다른 토큰으로 바꾸는 것은 큰 문제가 없다.
2. 패턴이 올바른 것은 정확한 intermediate thought를 생성하기 위해 중요하다.
3. 텍스트는 패턴에 대해 과제에 필요한 추가적인 정보와 의미를 부여해주기 때문에 중요하다.

라고 주장하고 있습니다. 이 원칙을 토대로 chain of thought prompt를 간략화해서 더 나은 성능과 더 짧은 프롬프트를 만들어내는 것에도 성공했네요.

#prompt 