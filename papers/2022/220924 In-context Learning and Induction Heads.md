https://arxiv.org/abs/2209.11895

In-context Learning and Induction Heads (Catherine Olsson, Nelson Elhage, Neel Nanda, Nicholas Joseph, Nova DasSarma, Tom Henighan, Ben Mann, Amanda Askell, Yuntao Bai, Anna Chen, Tom Conerly, Dawn Drain, Deep Ganguli, Zac Hatfield-Dodds, Danny Hernandez, Scott Johnston, Andy Jones, Jackson Kernion, Liane Lovitt, Kamal Ndousse, Dario Amodei, Tom Brown, Jack Clark, Jared Kaplan, Sam McCandlish, Chris Olah)

in-context learning을 유발하는 구조로 induction head라는 것을 제안(했었고) 그에 대한 분석이군요. 분석에 따르면 in-context learning은 induction head의 다음과 같은 기능에 의해 구현됩니다:

1. prefix matching. 현 시점의 토큰과 같은 토큰이 등장하는 패턴을 과거 시퀀스에서 찾아냄.
2. copying. 찾아낸 토큰을 복사함.

트랜스포머 학습 과정에서 이러한 기능을 수행하는 induction head가 학습되는 순간 in-context learning 성능이 급격히 향상되고, induction head의 학습을 유도하거나 방해하는 것에 따라 in-context learning 능력을 학습할 수 있는가가 달라진다는 보고군요.

#in_context_learning #transformer 