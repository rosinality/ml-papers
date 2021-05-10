https://arxiv.org/abs/2012.01300

Learning from others' mistakes: Avoiding dataset biases without modeling
  them (Victor Sanh, Thomas Wolf, Yonatan Belinkov, Alexander M. Rush)

데이터셋의 bias를 보완하는 방법. weak learner가 bias를 활용한다는 점을 이용해 weak learner을 학습시키고, 메인 모델에 weak learner를 연결해 product of experts로 학습시켜서 메인 모델이 weak learner의 문제를 보완하도록 만듦.

#bias #product_of_experts