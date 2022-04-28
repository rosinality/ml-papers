https://arxiv.org/abs/2202.04200

MaskGIT: Masked Generative Image Transformer (Huiwen Chang, Han Zhang, Lu Jiang, Ce Liu, William T. Freeman)

autoregressive generation 대신 mask prediction 기반 이미지 생성. vq-vae 토큰 위에서 일정한 mask probability schedule에 따라 학습시키고 샘플 시에는 mask schedule과 모델의 confidence를 사용해서 mask들을 채워나가는 접근이네요. nonautoregressive generation이나 discrete diffusion 같은 곳에서 나오는 형태의 아이디어인데 이걸 이미지에 쓴 결과가 지금까지 뚜렷하게 없긴 했습니다.

이미지넷 fid나 precision/recall은 꽤 괜찮네요. stylegan-xl보다는 밀리긴 하는데 이쪽이 여러모로 단순한 방법이긴 하겠습니다.

#autoregressive_model #non-autoregressive #vq #generative_model 