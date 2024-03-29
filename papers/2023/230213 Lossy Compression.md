# 언어의 손실 압축에 대하여

https://www.newyorker.com/tech/annals-of-technology/chatgpt-is-a-blurry-jpeg-of-the-web

LM을 다음 단어를 예측할 뿐이라거나 학습 데이터를 기억할 뿐이라는 식으로 묘사하는 것은 폄하를 위한 언어이지 LM의 실체나 실제 한계에 대해서 논하기에 적절한 방식은 아니라고 생각한다. 그런 점 때문에 테드 창의 사설이 별로 내키지는 않았다. 그렇지만 이 내키지 않음에 대해 무언가 정리된 의견을 만들 수 있을 것인가? 그런 생각을 하다 보니 보통 하지 않는 생각에까지 다다르게 되었는데, 그런 의미에서 이 사설은 내게 (내가 처음 예상했던 것과는 달리) 의미가 있었다고 할 수 있을 것 같다. (다른 분들에게도 그럴 수 있을 것 같아 읽어보시기를 추천하고 싶다.)

다음 단어를 예측할 뿐이라는 식의 묘사를 걷어내고, 나는 현재 Transformer LLM의 한계에 대해서 논하자면 언어 모델이라는 것의 본질에서 시작해야 한다고 생각한다. 그런 점에서 다음과 같은 측면을 논할 수 있을 것이다.

1. 언어에 대한 통계 모델, 즉 언어의 확률 분포라는 것이 말이 되는 것인가? 혹은 쓸모 있는 것인가?
2. 언어 모델을 Autoregressive 모델로 모델링하는 것이 적절한가? 예를 들어, 우리는 Autoregressive 모델의 학습 vs 추론 문제에 대해 해결책을 갖고 있는가?
3. 그 언어 모델을 Transformer로 모델링하는 것이 적절한가? Transformer의 표현력의 한계가 문제가 되진 않는가?

사실 이런 문제들이 말끔히 해소된 상태라고는 말할 수 없을 텐데, 지금 Transformer LLM이 보여주는 엄청난 결과 때문에 (그리고 위 문제들을 해소하기 위해 제안된 방법들이 아직 괄목할만한 향상을 보여주지 못하고 있기 때문에) 이 문제들을 무심코 건너 뛰게 되는 경향이 있는 것 같다.

## 여하간, 언어 모델이란 대체 무엇인가?

언어 모델, 즉 텍스트 시퀀스의 확률 분포라는 것이 도대체 어떤 의미일까? 텍스트에 확률을 부여한다는 것은 어떤 의미일까?

한쪽 극단으로는 무손실 압축처럼 주어진 텍스트에 대해서는 확률을 부여하고 그 밖의 텍스트에 대해서는 확률을 부여하지 않는 모델을 생각할 수 있다. 다른 쪽 극단에서는 가능한 모든 텍스트 시퀀스에 대해 동일한 확률을 부여하는 바벨의 도서관 같은 것을 생각할 수 있다.

전자를 택한다면 그 확률 분포 모델에서는 한발짝도 밖으로 나갈 수 없다. 넉넉잡아 토큰 100개만 고려해도 그 토큰 100개가 동일하게 다른 곳에 나타날 확률은 없다. (복붙한 것이 아니라면) 그러니 지금까지 발화된 텍스트의 분포는 아무리 많더라도 텅 빈 공간(support)에 대한 분포일 것이다. 마치 푸네스와 같이. 모든 것이 다르고 그 모든 것을 똑똑히 기억할 수 있다. 그러나 그 밖으로는 나아갈 수 없고 그 다른 모든 것들 사이를 건너뛰거나 혹은 그 중간 지점을 발견할 수 없다. (interpolation?)

가능한 모든 텍스트에 대한 분포는 쓸모가 없다. 우리가 그런 분포를 갖게 된다면 바벨의 도서관의 사서들이 그러했던 것처럼 그 모든 가능한 시퀀스들 중에서 쓸모 있는 시퀀스들만을 알려주는 가이드 같은 것을 찾는 불가능한 시도에 매달려야 할 것이다. 그러니 우리가 상상하는 쓸모 있는 모델이란 대충 이 두 극단 사이에서 어딘가에 있는 모델인 것이다. 그러나 대체 그 지점이 어디인가? 혹은 어디여야만 하는가?

현재 모델의 한계를 차치하고, 우리가 정말로 텍스트의 완벽한 확률 분포 함수를 갖게 된다면 우리는 그것으로 어디까지 나아갈 수 있을까? 그 완벽한 확률 분포 함수는 대체 무엇에 대한 확률 분포일까? 지금까지 말해진 모든 것에 대한 확률 분포일까 혹은 앞으로 말해질 모든 것을 모두 포함하는 확률 분포일까? 지금까지 말해진 모든 것에 대한 분포라면 그것은 과히 쓸모가 없을 것이다. 앞으로 말해질 모든 분포는 좀 더 매력적이다. 그 분포에는 지금까지 쓰여진 적 없는 명작 같은 것들이 들어 있을 것이다. 그러나 그만큼, 혹은 그 이상으로 많은 수의 졸작 또한 쓰여져 있을 것이다. 그렇다면 우리는 어떻게 그 분포 함수에서 졸작 대신 명작을 찾아낼 수 있을까? 다른 도구가 없는 이상 그 확률 분포 하나에서 할 수 있는 것은 처음부터 충분히 작성된 명작의 텍스트에서 시작해 conditioning 하는 것 밖에 없지 않을까 싶다. 즉 이 분포를 사용해 할 수 있는 것은 (테드 창이 지적한 것처럼) 썩 잘 쓰여지지 않은 독창적인 아이디어를 교정하는 정도일 것이다.

그러니 이상적인 언어 모델이란 지금까지 쓰여지지 않은 모든 텍스트들 중 쓸모 있고 유용하거나 정확한 텍스트에 대한 확률 분포일 것이다. 그런데 대체 그 쓸모 있는 지점과 그렇지 않은 지점의 한계는 어떻게 결정할 수 있을 것인가? 그것을 결정했다고 하더라도 그 경계선을 모델에 어떻게 주입할 수 있을 것인가?

가장 쉽게 생각해볼 수 있는 것은 쓸모 있는 텍스트에 대한 정보를 제공하는 expert나 critic 같은 것을 상정하는 것이다. 그건 인간일 수도 있겠고 어떤 모델일 수도 있겠다. 바로 이 문제 때문에 스스로 생성한 증거와 실제 증거를 구분하는 시그널을 제공하는 expert를 사용하는 방법(https://arxiv.org/abs/2110.10819) 과 생성된 텍스트를 ranking해서 시그널을 전달하는 방법(https://arxiv.org/abs/2110.10819) 이 필요해지는 것일 수도 있다. 이런 방법들은 unsupervised training이라는 케이크 위에 얹힌 체리 정도로 여겨지거나 사소한 튜닝으로 간주되기도 하지만 어쩌면 이것이 쓸모 있는 분포를 만드는 것에는 결정적인 장치일 수도 있다.

예를 들어 명작을 찾고 있는 한 사람을 생각해보자. 그는 수많은 후보 텍스트들, 혹은 그 텍스트들의 얼개, 플롯을 구상할 것이다. 이런 공상은 어쩌면 언어 모델의 그것(hallucination)과 흡사할 수도 있다. 그 수많은 후보 시퀀스들 중 그는 어떻게 명작을 찾아낼 것인가? 그것은 그가 내적으로 갖고 있는 이야기의 질을 평가하는 기준, 어떤 검토기(checker)에 의존할 것이다. 즉 좋은 시퀀스와 그렇지 않은 시퀀스를 구분하는 장치가 필요할 것이다. 또한 그 시퀀스는 그의 검토기를 통과한 이후에도 세상에 나와 수많은 다른 사람들의 검토기를 거쳐야만 할 것이다. 편집자, 혹은 독자들에게. 명작 시퀀스란 그런 과정을 거쳐서 생성된다. 좀 더 나은 시퀀스 생성기라면 더 명작의 가능성이 높인 시퀀스들을 생성할 것이다. 그렇지만 여전히 후보 시퀀스들이 생성될 뿐이다. 그것이 명작인지는 독자들에게까지 도달한 이후에만 확인될 수 있다. (물론, 독자들이 읽으면 명작인지 아닌지가 결정된다는 것은 너무나 거친 근사이다. 그렇지만 더 나은 근사를 통해 이 문제가 해소될 것 같지는 않다.)

과학적 사실에 대해서라면 어떨까? 우리는 수많은 가설 시퀀스들을 생성할 수 있다. 좀 더 나은 시퀀스 생성기라면 좀 더 가능성이 높은 가설을 생성할 수도 있을 것이다. 그러나 그것이 진실인지 아닌지를 확인하는 것은 실험으로 자연에 대해서 확인한 이후에만 가능하다. 이렇게 보면 AI 과학자가, 인간 과학자보다는 좀 더 나을 수 있겠지만 속도가 압도적으로 더 빠를 수는 없으리라는 생각도 할 수 있다. 자연과학적 문제에 대해서는 여전히 실험이 필요하다. 우리가 흥미로워하는 사회과학적인 문제에 대해서는 실험이 불가능하거나 정보가 영영 충분하지 않을 수도 있다. 따라서 다음과 같이 AI 과학자가 무궁무진한 속도로 스스로 발전할 수 없는 이유에 대해 생각해볼 수 있다.

1. AI 과학자가 가설 시퀀스를 생성한다.
2. 실험을 수행하고 자연의 검토기에 대해 확인을 요청한다. 어쩌면 실험이 불가능할 수도 있고, 불확실할 수도 있다. 그렇지 않더라도 상당한 시간이 필요하다.
3. 어쩌면 우리는 자연의 검토기를 대신하는 인공적인 검토기를 생각해볼 수도 있다. 그렇지만 AI 과학자보다 더 나은 검토기라면, 시퀀스를 생성하는 모델보다 시퀀스를 점검하는 모델을 만드는 것이 더 쉬울 것이라는 것을 고려하더라도, 우리는 이미 지금 가진 모델보다 더 나은 모델을 갖고 있는 것이다. 따라서 모순적인 상황이다.

위와 같이 생각해본다면, 우리가 원하는 모델을 만들기 위해서는 검토기가 필요한데, 그 검토기를 만드는 것이 만만하지 않을 것이라는 것을 추측해볼 수 있다. 우리가 이미 친숙하고 잘 알고 있는 것과 배치되는지 아닌지를 검토하는 모델은 만들 수 있을 것이고 이미 성공적으로 만들어져서 사용되고 있는 것 같다. 그리고 이 정도만으로도 충분히 유용할 것이다. 그렇지만 우리가 쉽게 상상하는 창조적인 아이디어와 새로운 사실들을 생성하고 검토하는 모델을 만들기는 쉽지 않을 것이다. 어쩌면 거의 불가능한 일일 수도 있다.

## Smoothing

위에서 언급했듯 가능한 텍스트들의 공간이라는 막대한 고차원의 공간에서는 이미 생성된 모든 텍스트들을 모아도 그 텍스트들이 점유하는 공간은 거의 없다고 해도 마찬가지이다. 잠재적으로 쓸모 있는 텍스트들의 공간으로 좁히더라도 마찬가지로 그러할 것이다. 점이나 콤마만이 다른 사실상 동일한 텍스트들이 무궁무진하게 있더라도.

그러니 주어진 텍스트를 동일하게 인출해줄 것이 아니라면, 또 만들어진 텍스트 분포 모델이 새로운 텍스트들에도 쓸모 있게 작동하려면 주어진 데이터의 분포 이외의 영역에도 확률을 가져야 한다고 생각할 수 있다. 따라서 Smoothing은 언어 모델의 학습에 필수불가결하다. n-gram 시절에는 Kneser-Ney smoothing 같은 도구가 있었고 뉴럴넷의 시대에는 주어진 학습 텍스트의 확률을 1로 만들라고 학습해도 알아서 다른 시퀀스들에 확률을 부여하고 있는 뉴럴넷 모델들이 그 역할을 하고 있다.

주어진 텍스트에만 확률을 부여하는 모델과 가능한 모든 텍스트들에 확률을 부여하는 모델의 중간 어딘가 쓸모 있는 지점에 구획을 설정하는 것이 바로 이 Smoothing이라고 생각할 수 있다. 그런데 뉴럴넷 시대에 우리는 모델이 어떤 지점에서 이러한 경계선을 긋는 혹은 Smoothing 작업을 하고 있는지를 잘 알고 있지 못하다. 오히려 의미 있는 방식으로 작동하지 못할 수도 있다는 증거들도 있다. (turing-complete 하지 않다거나, 처리할 수 있는 문법에 한계가 있다거나 등.) 그러나 지금까지 뉴럴넷 모델은 너무나 성공적인 것처럼 보인다.

확실히 언어 모델은 손실 압축이다. (언어 모델의 확률 추정을 통해 텍스트를 무손실 압축한다거나 하는 것은 일단 차치하고.) 그러나 제국과 1:1 대응하는 크기의 지도가 쓸모 없이 버려졌던 것처럼 우리에게는 적절한 축척, 즉 적절한 손실도의 지도가 필요할 것이다. 그러나 그 적절한 축척이 무엇인지 혹은 어떻게 도달할 수 있는지 우리는 잘 알고 있지는 않다. 우리가 지금 알고 있는 것은 더 많은 데이터와 더 큰 데이터가 더 나은 손실도를 보여준다는 것을 알고 있을 뿐이다. 아니, 사실 그 손실도가 어떠한지에 대해 알고 있다고 할 수도 없고 그저 더 유용하다는 것을 알고 있을 뿐이다.