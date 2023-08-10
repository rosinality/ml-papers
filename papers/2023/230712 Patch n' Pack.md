https://arxiv.org/abs/2307.06304

Patch n' Pack: NaViT, a Vision Transformer for any Aspect Ratio and Resolution (Mostafa Dehghani, Basil Mustafa, Josip Djolonga, Jonathan Heek, Matthias Minderer, Mathilde Caron, Andreas Steiner, Joan Puigcerver, Robert Geirhos, Ibrahim Alabdulmohsin, Avital Oliver, Piotr Padlewski, Alexey Gritsenko, Mario Lučić, Neil Houlsby)

aspect ratio를 보존하면서 vit 학습. 패딩 없이 이미지 패치들을 1d로 쭉 붙이고 이미지 경계를 침범하지 않도록 attention masking, 그리고 각 이미지별로 pooling 하는 방법입니다. lm 학습에 쓰이는 방법을 채택한 것이라고 할 수 있겠네요.

구글 딥마인드에서 했으니 Gemini 학습용으로 테스트해본 것이겠네요.

#vit 