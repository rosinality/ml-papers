https://arxiv.org/abs/2302.06646

Simple Hardware-Efficient Long Convolutions for Sequence Modeling (Daniel Y. Fu, Elliot L. Epstein, Eric Nguyen, Armin W. Thomas, Michael Zhang, Tri Dao, Atri Rudra, Christopher Ré)

Flash Attention으로 유명한 팀의 state space model 연구. ssm 효율적인 구현에는 결국 convolution을 사용하니 처음부터 convolution을 쓰면 되지 않을까 하는 아이디어. 적절하게 convolution kernel을 regularize 해주면 가능하다는 결과군요. 추가로 Flash Butterfly라는 최적화된 커널도 만들었습니다.

결과는 흥미롭네요. 역시 long range 문제에서 성능이나 효율성에 강점이 있고요. state space model은 scaling 연구가 나오면 채택율이 높아질 것 같은데 scaling 실험 자체를 할 수 있는 자원이 있는 곳이 드무니...아쉽네요.

#state_space_model 