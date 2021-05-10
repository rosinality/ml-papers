https://arxiv.org/abs/2008.00623

DeLighT: Deep and Light-weight Transformer (Sachin Mehta, Marjan Ghazvininejad, Srinivasan Iyer, Luke Zettlemoyer, Hannaneh Hajishirzi)

DeLighT: Very Deep and Light-weight Transformer (Sachin Mehta, Marjan Ghazvininejad, Srinivasan Iyer, Luke Zettlemoyer, Hannaneh Hajishirzi)

트랜스포머 파라미터 줄이기. grouped linear로 구성된 inverted bottleneck 형태의 블록(DExTra)을 추가해 상대적으로 너비를 좁게, 깊이를 깊게 만듦. 그리고 ffn의 hidden dim을 줄임. 파라미터 수와 MACs이 감소하지만 실제 레이턴시는 어떨지. #nlp #transformer