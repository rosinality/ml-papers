https://arxiv.org/abs/2111.14330

Sparse DETR: Efficient End-to-End Object Detection with Learnable Sparsity (Byungseok Roh, JaeWoong Shin, Wuhyun Shin, Saehoon Kim)

deformable self attention이 key-value를 sparse하게 만들어서 효율성을 추구하는데 query는 여전히 dense하다. 따라서 query를 sparse하게 만들어보자는 아이디어네요. sparse하게 만들기 위해 decoder cross attention map을 사용해 쓸 query 토큰만 골라내도록 만들기. deformable detr류의 multiscale feature 사용을 효율화할 수 있는 흥미로운 방향인 것 같습니다.

#detr #object_detection 