https://arxiv.org/abs/2011.04946

When Do You Need Billions of Words of Pretraining Data? (Yian Zhang, Alex Warstadt, Haau-Sing Li, Samuel R. Bowman)

lm 프리트레이닝에 왜 그렇게 많은 데이터가 필요할까? probing으로 찔러보면 syntactic/semantic한 정보는 단 1억 단어 정도면 충분히 인코딩되는 것으로 보임. 더 많은 데이터가 필요한 이유는 이 정도로는 이 정보를 다른 과제에 쓰기에는 충분치 않아서일 수도 있고, 아니면 추가적인 commonsense 정보를 학습하는 것이 성능에 유용해서일 수도 있음. winograd coreference 과제로 probing을 해보면 commonsense 정보는 10억 토큰이 넘어가야 제대로 학습되는 것으로 보임.

#pretraining #language_model