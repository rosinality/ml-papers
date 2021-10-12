https://arxiv.org/abs/2109.03810

Scaled ReLU Matters for Training Vision Transformers (Pichao Wang, Xue Wang, Hao Luo, Jingkai Zhou, Zhipeng Zhou, Fan Wang, Hao Li, Rong Jin)

vit에서 stem에 conv를 써주면 좋다는 건 이제 잘 알려진 사실일 것 같긴 합니다. 이 논문은 추가로 scaled relu, 그러니까 일반적으로는 normalization + relu가 conv stem에 들어가는 것이 중요하다는 이야기를 합니다. 음 activation과 normalization이 들어가면 안정화되는 것/성능이 향상되는 것은 자연스럽지 않나 싶긴 한데요. 반대로 patch stem에 scaled relu가 들어갔을 때의 변화 등으로 효과가 나타나면 좋았을 듯 한데 그 부분은 강하지 않은 것 같네요.

어쨌든 conv stem이 고성능/학습 안정성에 도움이 된다는 건 이제 분명해보이네요. dino에 대해 실험한 결과도 있어서 유용하네요.

#vit #cnn