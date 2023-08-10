https://arxiv.org/abs/2304.11062

Scaling Transformer to 1M tokens and beyond with RMT (Aydar Bulatov, Yuri Kuratov, Mikhail S. Burtsev)

context length가 중요하다는 것이 인지되기 시작해서인지...엄청나게 회자되고 있군요. 기반은 Recurrent Memory Transformer에서 왔습니다. (https://arxiv.org/abs/2207.06881) 간단하게 요약하자면 memory token을 입력으로 받고, memory token을 출력해서 다음 스텝으로 넘겨주는 방식입니다. 선택적으로 BPTT도 하고요.

그 많은 context가 모두 쓸모 있지는 않겠지만 context의 증가에 따라 쓸모 있는 정보의 양은 증가할 것이고, recurrent memory를 쓰는 접근은 이 계속해서 증가하는 정보들을 고정된 크기의 임베딩으로 압축해야 한다는 문제에서 벗어나기 힘들긴 하죠. 그렇다면 반대로 계속해서 증가하는 context를 감당 가능한 수준으로 다룰 수 있는 방법이 무엇인가? 라는 문제로 다시 돌아가게 된다고 봅니다.

#transformer 