https://arxiv.org/abs/2107.05768

Combiner: Full Attention Transformer with Sparse Computation Cost (Hongyu Ren, Hanjun Dai, Zihang Dai, Mengjiao Yang, Jure Leskovec, Dale Schuurmans, Bo Dai)

efficient attention. 상당히 복잡하게 기술했는데...요약하자면 시퀀스를 쪼갠 다음 full attention을 하는 구간(direct expectation)과 구간 내의 query/key들을 요약한 다음 이 요약들을 사용해 attention을 구하는 구간(local expectation)의 합으로 attention을 구성했다는 느낌이군요. 요약하자면 어쨌든 요약하는 attention이라는 느낌입니다.

#efficient_attention #sparse_attention #local_attention 