https://arxiv.org/abs/2209.05442

Soft Diffusion: Score Matching for General Corruptions (Giannis Daras, Mauricio Delbracio, Hossein Talebi, Alexandros G. Dimakis, Peyman Milanfar)

이쪽은 linear corruption, 즉 
x_t = C_t x_0 + s_t n_t
C_t: linear operator, n_t: brownian motion인 케이스에 대한 diffusion이군요. deterministic linear operator로 blur를 사용하고 약간의 노이즈를 더하는 방식으로 (결과적으로 Blurring Diffusion Models와 비슷해졌습니다.) CelebA sota를 달성했습니다.

#ddpm 