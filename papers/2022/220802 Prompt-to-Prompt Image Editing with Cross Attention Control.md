https://arxiv.org/abs/2208.01626

Prompt-to-Prompt Image Editing with Cross Attention Control (Amir Hertz, Ron Mokady, Jay Tenenbaum, Kfir Aberman, Yael Pritch, Daniel Cohen-Or)

text-to-image generation이 가능해지니 추가적으로 text를 사용해 결과 이미지를 편집하고 싶어지죠. 그런데 편집을 하자면 이미지의 전반적인 구조를 유지하면서 국소적으로 이미지를 수정해야 하기 때문에 까다롭습니다.

이 논문에서는 이미지의 구조적인 배치 정보가 이미지-텍스트 사이의 cross attention의 attention weight의 분포/구조에 의존한다는 것을 포착했네요. 따라서 원 이미지의 cross attention weight를 그대로 가져다 쓰고 텍스트의 임베딩만 갈아끼우면 된다는 아이디어입니다.

텍스트 입력을 잘 지정하는 것이 문제였는데 이 결과는 그걸 훨씬 쉽게 만들어줄 수 있겠네요.

#image_editing 