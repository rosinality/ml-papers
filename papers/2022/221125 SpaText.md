https://arxiv.org/abs/2211.14305

SpaText: Spatio-Textual Representation for Controllable Image Generation (Omri Avrahami, Thomas Hayes, Oran Gafni, Sonal Gupta, Yaniv Taigman, Devi Parikh, Dani Lischinski, Ohad Fried, Xi Yin)

이미지 생성 모델에서 텍스트 프롬프트만으로는 결과물을 통제하기 어려우니 스케치나 레이아웃 같은 것을 입력으로 쓸 수 있는 방향으로 나아가는 것도 자연스럽다 싶긴 하네요. 학습시에는 이미지에서 panoptic segment mask를 뽑은 다음 이미지를 clip 임베딩해서 이 임베딩을 공간적으로 배치하는 방식으로 사용하고 추론 시에는 텍스트를 clip 임베딩한 다음 이 임베딩을 이미지 임베딩으로 변환하고, 사용자가 입력한 레이아웃에 따라 공간 내에 배치하는 방식이군요. 사실 이런 layout to img는 꽤 이전부터 나왔던 주제인데 이런 접근 방식의 변화도 꽤 흥미롭다 싶네요.

#text2img 