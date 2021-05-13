https://arxiv.org/abs/2105.05837

When Does Contrastive Visual Representation Learning Work? (Elijah Cole, Xuan Yang, Kimberly Wilber, Oisin Mac Aodha, Serge Belongie)

contrastive learning으로 학습된 모델이 transfer에서 얼마나 유용한가?

1. pretraining에 사용된 데이터의 양에 대해 성능 향상은 감쇄한다. (이 경우에는 50만 장)
2. 레이블된 데이터가 적다면 유용하다. 단 레이블이 많은 상황에서 supervised training과 대등한 성능을 내려면 supervised training과 동등한 규모의 레이블이 필요하다.
3. 도메인 일치가 중요하다. 다른 도메인의 데이터가 추가되는 것은 별 도움이 되지 않는다.
4. 프리트레이닝 데이터셋의 퀄리티가 supervised training에서보다 더 중요하다. 특히 이미지 크기!
5. fine grained classification에서 contrastive learning의 성능이 취약해보인다.

요약하자면 self supervision의 시대에도 데이터셋을 잘 챙기는 것은 여전히 중요하다는 것.

#contrastive_learning #self_supervised #transfer #review 