https://openai.com/blog/whisper/

openai에서 asr 모델을 만들었군요. 68만 시간 분량의 multilingual 데이터로 multitask (transcription, translation, language identification, voice activity detection) 학습을 했습니다. 1.5B 모델까지 scaling 했는데 인간에 가까운 수준의 정확성과 robustness를 달성했다고 하네요.

윤하의 오르트 구름을 speech translation한 샘플도 있는데 굉장합니다.

#asr

[https://openai.com/blog/whisper/](https://openai.com/blog/whisper/?fbclid=IwAR0oV6028YU1Wb4Y89iE3cEWJ_-SuY4_lPlbpyulVMuov4klmuzKBdQXM5M)

(ASR 안 해 본 사람이 하는 소리이므로 주의 요망.)

OpenAI Whisper에서 개인적으로 흥미롭다고 생각하는 점. scaling의 끝이 보이는 것 같은 사례라는 것. 즉 LLM 같은 케이스에서 모델 10배, 데이터 10배, 연산량 10배면 성능이 향상될 것이라는 것이 거의 분명한 것과는 다르게 이 사례에서는 데이터의 증가와 모델 크기의 증가가 명백한 성능 향상으로 나타나지 않을 수도 있겠다는 것이 나타난다는 것이다.

예를 들어 768M -> 1.5B로 모델 크기를 키웠을 때에나 데이터를 12.5배 증가시켰을 때의 transcription 성능 향상은 그렇게 커 보이진 않는다. (물론 transcription에만 주목한 것이긴 하다.)

따라서 아마 더 scaling을 했을 때 성능 향상이 그렇게 나타나지 않을 수도 있겠다는 추측을 할 수 있지 않을까 싶다. 물론 논문에서 제안하는 것처럼 더 큰 모델을 더 오래 학습한다면 이 경향을 돌파할 수 있을 수도 있긴 하다.

Robustness나 Accuracy 측면에서 사람과 상당히 비슷한 수준까지 도달한 사례가 나타난 것으로 볼 때 이건 어쩌면 모델 성능이 bound에 근접했다는 것을 의미할 수도 있겠다.

조금 더 과장하자면 english transcription의 최종 도착 지점이 얼마 남지 않은 것일지도 모르겠다는 생각을 한다.

물론 대부분의 딥 러닝 모델이 맞닥뜨리는 문제인 더 넓은 도메인에서 발생하는 문제들을 커버하는 것은 더 까다로운 작업이겠지만, 어쨌든.

[https://www.youtube.com/watch?v=TqFLIZG_aXA](https://www.youtube.com/watch?v=TqFLIZG_aXA&fbclid=IwAR23ScIs30460wXwBk85puiD0IoCylvfcshZ2LBuiU3b5GbG7HJoNThCrN0)