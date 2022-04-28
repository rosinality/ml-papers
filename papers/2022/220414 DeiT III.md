https://arxiv.org/abs/2204.07118

DeiT III: Revenge of the ViT (Hugo Touvron, Matthieu Cord, Hervé Jégou)

이미지에 대한 self supervised training이 효과적이라는 보고들이 나오고 있지만 self supervised training에 쓰이는 레시피들은 supervised training과는 또 달라서 직접 비교가 어렵죠. vit에 대한 supervised training에서 학습 레시피들을 재조정해서 실험한 연구입니다. 전반적으로는 regularization과 augmentation을 약화시켰다고 할 수 있겠네요.

1. 낮은 weight decay: 0.05 -> 0.02
2. label smoothing 제거 (imagenet-1k)
3. dropout 제거 (imagenet-1k)
4. random resized crop -> random crop (imagenet-21k)
5. randaugment 제거, grayscale, solarize, gaussian blur augment로 대체
6. cutout 제거
7. colorjitter 사용
8. 학습시 추론 시보다 더 작은 이미지 크기 사용 (192x192)

이런 레시피들로 이전보다 더 나은 성능과 scaling이 나타났다...그런 보고입니다.

#vit