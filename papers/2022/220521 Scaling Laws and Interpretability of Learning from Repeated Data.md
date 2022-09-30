https://arxiv.org/abs/2205.10487

Scaling Laws and Interpretability of Learning from Repeated Data (Danny Hernandez, Tom Brown, Tom Conerly, Nova DasSarma, Dawn Drain, Sheer El-Showk, Nelson Elhage, Zac Hatfield-Dodds, Tom Henighan, Tristan Hume, Scott Johnston, Ben Mann, Chris Olah, Catherine Olsson, Dario Amodei, Nicholas Joseph, Jared Kaplan, Sam McCandlish)

lm 학습에서 중복된 텍스트 데이터가 치명적이라는 결과. 일부 데이터를 복사해서 중복 데이터를 만들었더니 학습된 모델의 성능이 더 작은 모델의 성능 수준으로 격하되는 것을 관찰했네요. 중복된 텍스트들이 모델이 텍스트를 외워버리게 만들고 이 외워버리는 과정에서 generalizability와 모델 capacity를 외우는 것 자체에 쓰게 만드는 것이 아닐까 하는 설명입니다.

여러모로 https://arxiv.org/abs/2107.06499 이 논문이 생각나네요. llm을 학습할 일이 생기시면 deduplication에 시간을 많이 쓰는 것으로.

#llm