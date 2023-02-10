https://arxiv.org/abs/2302.03027

Zero-shot Image-to-Image Translation (Gaurav Parmar, Krishna Kumar Singh, Richard Zhang, Yijun Li, Jingwan Lu, Jun-Yan Zhu)

captioning model로 이미지를 invert 한 다음, source/target 텍스트를 lm으로 증폭시켜서 mean clip embedding을 추출하고 이 embedding을 사용해서 edit 하면서 cross attention에 guidance를 줘서 structure를 보존하는 접근이군요.

https://pix2pixzero.github.io/

#image_editing #ddpm 