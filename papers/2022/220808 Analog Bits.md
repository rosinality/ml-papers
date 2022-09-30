https://arxiv.org/abs/2208.04202

Analog Bits: Generating Discrete Data using Diffusion Models with Self-Conditioning (Ting Chen, Ruixiang Zhang, Geoffrey Hinton)

discrete diffusion 모델인데 discrete 데이터를 처리하는 방식이 아주 단순합니다. integer 데이터를 bit sequence (0, 1)^n으로 바꾼 다음 이 bit sequence를 real array로 취급해서 모델에 입력으로 줍니다. 이미지 생성도 가능하지만 이걸로 텍스트 생성도 시도했네요.

#ddpm 