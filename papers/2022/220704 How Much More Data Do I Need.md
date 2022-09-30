https://arxiv.org/abs/2207.01725

How Much More Data Do I Need? Estimating Requirements for Downstream Tasks (Rafid Mahmood, James Lucas, David Acuna, Daiqing Li, Jonah Philion, Jose M. Alvarez, Zhiding Yu, Sanja Fidler, Marc T. Law)

이거 재미있는 결과네요. minimal seed 데이터셋으로 시작해서 (전체의 10% 정도) 데이터 양에 따른 성능 곡선을 피팅한 다음 그 예측 결과를 사용해서 목표 성능을 달성하기 위한 만큼의 데이터를 확보하고 다시 학습시키는 작업을 T 번 반복한다고 했을 때 목표 성능에 필요한 양의 데이터를 확보할 수 있는지에 대한 연구입니다.

함수를 피팅했을 때 필요 데이터 양을 underestimate하는 경향이 있어서 목표 성능을 좀 더 높게 잡을 수 있다면 그럭저럭 데이터 양을 예측 가능하고, 초기 데이터 양이 충분하다면 필요 데이터 양의 바운드를 구할 수 있다는 결론입니다.

시계열의 초기값만을 가지고 sigmoid를 피팅하는 게 어렵다는 이야기를 하는데 이 경우는 시작 부분이 exponential한 꼬리가 아니라서 그럭저럭 피팅이 잘 되는 것 같네요. https://gorelik.net/2020/04/19/why-is-forecasting-s-curves-hard/

#dataset 