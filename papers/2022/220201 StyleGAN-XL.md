https://arxiv.org/abs/2202.00273

StyleGAN-XL: Scaling StyleGAN to Large Diverse Datasets (Axel Sauer, Katja Schwarz, Andreas Geiger)

GAN strikes back. gan이 다시 diffusion model을 이겼네요. stylegan3-t를 기반으로 엄청나게 깎았습니다.

1. inversion을 위해 path length regularization 부활. 단 200k 이미지 학습 후에.
2. 첫 200k 이미지에 대해서는 gaussian blur 적용. stylegan3-r에 있었던 세팅인데 이걸 전체 세팅에 대해 적용했네요.
3. latent code 차원을 512에서 64로. 데이터셋의 실제 차원보다 필요 이상으로 커서 학습을 불안정하게 만든다는 아이디어.
4. class embedding을 학습된 cnn 모델로 추출한 feature statistics를 사용해서 초기화.
5. antialiasing을 고려한 progressive growing 부활. resolution이 증가할 때마다 레이어를 5개 늘리는 식으로 레이어의 수 증가.
6. projected gans 사용
7. efficientnet과 deit-m의 조합을 projected discriminator의 feature network로 사용.
8. 생성 샘플의 클래스 예측 결과를 사용해 classifier guidance loss 첨가

결과적으로 diffusion model (adm)보다 나은 fid와 근접한 precision/recall을 얻었네요. 거기에 imagenet 1024px에서도 성공적인 모델이 나왔습니다. 드디어 biggan을 대체할 수 있는 모델이 나온 것인가 싶네요.

#gan 