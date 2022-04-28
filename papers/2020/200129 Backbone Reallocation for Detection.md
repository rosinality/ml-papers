https://arxiv.org/abs/1912.11234

stride 4, stride 8 레벨의 레이어를 줄이고 stride 32 레벨의 레이어를 추가하는 패턴이 나타나는데 이건 DetNAS와 [[200129 DetNAS]] 유사한 듯.

그런데 stride 4 레벨은 freeze 하기 때문에 발생하는 문제일 수도 있지 않을지?

dilation은 의미가 있을 듯 한데 dilated conv 커널은 언제 빨라질지...

#backbone #object_detection #nas