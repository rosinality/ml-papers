https://arxiv.org/abs/2304.13013

Stable and low-precision training for large-scale vision-language models (Mitchell Wortsman, Tim Dettmers, Luke Zettlemoyer, Ari Morcos, Ali Farhadi, Ludwig Schmidt)

8 bit training이 가능할까 싶었는데 이런 결과들을 보니 가능할 것 같기도 하네요. int8 (추가적으로 fp8) 학습입니다. 학습 안정성을 챙기는 것이 중요한데 대응 방법은 Adam에서 update가 치솟는 케이스에 대한 방지(Adafactor와의 결합), 그리고 계속 말썽을 부리는 임베딩은 그냥 고정해버리기네요. 저자 직강(?)을 참조해보시는 것도 좋을 것 같습니다.

https://twitter.com/Mitchnw/status/1651253867517206531?s=20

#quantization #optimizer 