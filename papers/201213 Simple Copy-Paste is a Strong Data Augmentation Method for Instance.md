https://arxiv.org/abs/2012.07177

Simple Copy-Paste is a Strong Data Augmentation Method for Instance
  Segmentation (Golnaz Ghiasi, Yin Cui, Aravind Srinivas, Rui Qian, Tsung-Yi Lin, Ekin D. Cubuk, Quoc V. Le, Barret Zoph)

instance segmentation에 대한 augmentation. (instaboost 같은 방법과는 다르게) 복잡하게 생각할 것 없이 instance를 잘라다가 다른 데 붙여넣는 것만으로도 1.5 mAP 정도의 성능 향상. 구글이니 self supervision을 붙여보면 2.5 mAP까지. cutmix 같은 방법이 효과적인 것을 생각해보면 충분히 자연스러운 결과일지도? Cascade EfficientNet-B7 NAS-FPN이라는 기괴한 조합으로 57 mAP 달성! 내년에는 디텍터들이 다들 60 mAP를 찍고 있을 듯.

#augmentation #instance_segmentation 