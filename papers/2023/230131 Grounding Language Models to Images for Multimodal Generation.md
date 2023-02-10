https://arxiv.org/abs/2301.13823

Grounding Language Models to Images for Multimodal Generation (Jing Yu Koh, Ruslan Salakhutdinov, Daniel Fried)

오...이거 흥미롭네요. frozen visual encoder와 language 모델을 사용하면서 cross attention 없이 visual embedding을 k개의 임베딩 벡터로 변환해서 lm 입력에 바로 집어넣는 방식을 택했습니다. 추가로 retrieval token을 시퀀스에 추가해서 image retrieval이 가능하도록 했네요. 결과적으로 이미지/텍스트가 interleave된 대화를 처리할 수 있고 모델에서 이미지를 제안할 수도 있게 됐군요. 데이터는 interleave된 데이터를 따로 쓴 것은 아니고 image-caption 페어를 연달아 연결하는 방식으로 학습했습니다.

#multimodal_generation #vision-language #llm 