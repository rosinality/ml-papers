https://rosinality.github.io/2021/05/%EB%A8%B8%EC%8B%A0-%EB%9F%AC%EB%8B%9D-%EC%8B%9C%EC%8A%A4%ED%85%9C%EC%97%90%EC%84%9C-%EC%84%A4%EC%A0%95-%EA%B4%80%EB%A6%AC%ED%95%98%EA%B8%B0/

과거에도 쓴 글이 있는데, 여하간 머신 러닝을 위한 프레임워크, 구체적으로는 계속해서 실험을 하기 위한 프레임워크에서 가장 중요한 것 중 하나가 설정 관리라고 생각한다. 실험을 계속하다 보면 정말 온갖 곳에서 수정이 필요한 경우들이 생기고 (데이터소스, 데이터셋과 구조, 모델 구조, 학습 루프 등등등...) 그런 잠재적인 수정에 대해서 열려 있는 코드가 필요하다. 꼭 이런 모든 잠재적인 수정을 미리 예측해서 추상화한다기보다도, 수정이 필요해졌을 때 큰 부수효과나 자잘한 작업 없이도 수정할 수 있는가 하는 것이 중요한 부분이다.

그리고 이런 유연성에서 가장 기본적이면서도 큰 도움이 되는 것이 설정 파일이다.

사실 설정 파일 포맷 자체도 유의미한 차이를 만들어내지만 (예를 들어 여러 설정 파일을 조합할 수 있는가 등) 그보다는 설정 파일을 어떻게 사용하는가 하는 것이 중요하다 할 수 있겠다. 어쨌든 설정 파일은 그 형식이 어떻건 원칙적으로는 값의 나열이라는 점에서는 동일하므로.

예를 들어, 트랜스포머의 feedforward의 activation 함수를 바꾸고 싶다고 하자. 그렇다고 하면 보통 어떻게 할까? 가장 기본적으로는 if를 사용하는 것이다.

if conf.model.activation == 'relu':
    activation = nn.ReLU()

흔히 쓰이는 방법이지만 두 가지 문제가 있다. 새로운 activation 함수를 추가하고 싶다면 이 if 문이 있는 곳까지 이동해서 새로운 조건을 추가해야 한다. 거기다 ReLU 같은 경우 특별한 파라미터가 없어서 간단하지만 LeakyReLU 같이 추가 파라미터가 필요하다면 그에 따른 옵션도 추가되어야 한다.

거기다 보통 모델 선언은 Transformer(Blocks(FeedForward)) 같은 식으로 중첩되어 있으므로 위와 같은 조건문이 등장하는 지점까지 설정값을 넘겨줘야 한다. 그냥 값을 넘기자니 중첩 때문에 설정값이 누적되어 증가한다는 것도 문제다. (예를 들어 Transformer는 FeedForward을 위한 설정값 activation도 넘겨받아야 하고, dropout을 위한 설정값도 넘겨받아야 한다.) 그래서 그냥 여러 설정들을 묶은 객체를 (위의 conf 같은) 넘겨주는 경우도 많다. 좋긴 하지만 그렇다면 그 모듈을 쓰기 위해서는 conf 객체를 생성해서 전달해야 한다. 그 자체도 번거롭지만 conf 객체에서 실제 사용되는 설정값을 코드를 보기 전에는 알 수 없다는 것도 문제가 된다.

그 다음으로 인기 있는(혹은 인기 있었던?) 방법은 registry를 쓰는 방법이다. 예를 들면 이런 식이다.

@registry
def relu():
	return nn.ReLU()

activation = get_registry(conf.model.activation)

if문을 추가해야 한다는 문제가 사라진다는 점은 유용하다. 그렇지만 registry에 추가해줘야 한다는 문제가 생겨나고, 설정을 어떻게 넘겨줄 것인가라는 문제는 아직 해소되지 않았다.

그렇다면 아예 설정값에 nn.ReLU라는 객체를 넣을 수는 없을까? 이 문제를 해결하는 것이 hydra의 instantiate이다.

https://hydra.cc/docs/advanced/instantiate_objects/overview/

activation:
  _target_: torch.nn.ReLU

activation = instantiate(conf.model.activation)

registry 등록이 필요 없이 파이썬 객체나 함수를 그대로 설정값으로 추가하고, 그 설정값을 사용해서 파이썬 객체를 생성할 수 있다. 여기서 약간 불편한 점은 YAML을 사용하기 때문에 함수 호출을 위한 구문이 좀 자연스럽지 않다는 것이다. import 경로도 모두 써줘야 하고.

https://detectron2.readthedocs.io/en/latest/tutorials/lazyconfigs.html

이 문제에 대해서 detectron2에서는 파이썬 코드를 설정 파일로 쓰는 방식으로 해결했다.

activation = L(nn.ReLU)()

일반적인 파이썬 코드를 사용해서 호출하되, L()을 사용해서 실제로 코드를 실행하는 것이 아니라 설정값을 생성하도록 한 것이다. 비슷한 접근을 구글에서 공개한 fiddle (https://github.com/google/fiddle) 에서도 채택하고 있는데, 여기서는 더 나아가 AST를 패치해서 L()을 제거하기도 했다.

@auto_config
def activation():
  return nn.ReLU()

이 접근을 채택하면 예컨대 optimizer 하이퍼파라미터 조정 같은 일상적인 문제도 간단해진다. 예를 들어 AdamW 같은 경우 learning rate, beta1, beta2, eps, weight decay 같은 하이퍼파라미터가 필요한데, 이 모든 값을 설정으로 추가한다고 생각하면,

if conf.optimizer == 'adamw':
  return AdamW(parameters(), lr=conf.lr, betas=(conf.adam_beta1, conf.adam_beta2), eps=conf.adam_eps, weight_decay=conf.weight_decay)

이런 형태가 될 것이다. 그렇지만 instantiate를 사용한다면,

optimizer = L(AdamW)(lr=3e-4, betas=(0.9, 0.98), eps=1e-5, weight_decay=0.1)
optimizer = instantiate(optimizer)(parameters)

같은 식으로 사용이 가능하다.

더 나아가, instantiate가 중첩된 객체나 함수 선언을 생성할 수 있다고 하면 설정값을 전달하는 방식이 아예 달라질 수 있다. 예를 들어 위의 activation 변경 같은 문제는 이렇게 접근할 수 있다.

model = L(Transformer)(
  block=L(Block)(
    feedforward=L(FeedForward)(
      activation=L(ReLU)() 
    )
  )
)

model = instantiate(model)

FeedForward 같은 모델에서 activation을 생성하는 것이 아니라, 그냥 activation을 설정값 자체에서 FeedForward에 넘겨주는 것이다. 뭐 요새는 전부 비슷비슷한 트랜스포머를 쓰다보니 이런 형태의 모듈화가 필요한 경우가 많지 않긴 하지만, 그렇지 않다면 문제를 훨씬 쉽게 만들어주는 경우가 있다.

이러한 설정 관리 방법의 유연성과 강력함을 보여주는 사례로 detectron2에서 설정 변경으로 본업도 아닌 이미지넷 분류기를 학습시키는 예제도 참고할만할 것 같다. https://github.com/facebookresearch/detectron2/blob/main/configs/Misc/torchvision_imagenet_R_50.py

더 나은 방법과 디자인, 접근이 있을 수 있겠지만, 이 방법이 hydra, detectron2, fiddle에서 공통적으로 등장한 것을 보면 그럭저럭 쓸만한 수준이라고는 할 수 있을 것 같다. 개인적으로도 계속 써오고 있는데, 물론 머신 러닝 시스템에서 정말 온갖 수정에 대한 필요가 발생하기에 그 모두를 커버하기는 어려운 경우도 있긴 했지만 대체로 나쁘지 않았다. 그렇게 흔한 접근과 도구가 아니라는 것에서 발생하는 문제들은 있었지만.