https://arxiv.org/abs/2112.10740

Are Large-scale Datasets Necessary for Self-Supervised Pre-training? (Alaaeldin El-Nouby, Gautier Izacard, Hugo Touvron, Ivan Laptev, Hervé Jegou, Edouard Grave)

mask prediction/denoising autoencoder 기반 self supervision은 샘플 효율적이고, 효율적이다 못해 imagenet 레벨의 프리트레이닝도 필요하지 않다는 결과. 그냥 타겟 데이터셋에 대해 프리트레이닝해도 imagenet 프리트레이닝한 것 만큼 성능이 나오거나 오히려 더 잘 나온다는 것. coco에서 디텍션을 할 것이라면 그냥 coco에 대해 프리트레이닝하는 것이 맞다고 할 수 있겠네요.

#pretraining #self_supervised #transfer 