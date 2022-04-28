https://arxiv.org/abs/2007.01289

Deep Single Image Manipulation (Yael Vinker, Eliahu Horwitz, Nir Zabari, Yedid Hoshen)

입력을 수정해 생성 이미지를 수정할 수 있는 모델. 단 하나의 이미지로 학습하는데 singan 계통의 patch 기반 방법이 아니라 pix2pixHD를 그대로 사용. 대신 thin plate spline을 사용한 warp를 augmentation으로 적용. 그리고 semantic map과 edge를 결합한 입력을 활용. 흥미로운 결과.

#single_image #img2img #image_editing 