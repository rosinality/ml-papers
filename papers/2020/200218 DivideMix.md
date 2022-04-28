https://arxiv.org/abs/2002.07394

DivideMix: Learning with Noisy Labels as Semi-supervised Learning (Junnan Li, Richard Socher, Steven C.H. Hoi)

제목처럼 노이지한 레이블들을 unlabeled로 취급하고 semi supervision (mixmatch)을 해보겠다는 아이디어. GMM으로 loss distribution을 fitting해서 깨끗/노이지를 구분하는데 네트워크 하나로 이 과정을 수행하면 네트워크 자신의 정답에 고착될 수 있으니 네트워크 두 개를 사용한다는 것이 중요한 부분인 듯.

#mixup #noise #dataset #semi_supervised_learning 