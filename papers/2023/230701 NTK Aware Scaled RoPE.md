https://www.reddit.com/r/LocalLLaMA/comments/14lz7j5/ntkaware_scaled_rope_allows_llama_models_to_have

rope scaling에 대한 진전이 더 나오고 있군요. linear interpolation이 아니라 nonlinear interpolation으로 에러를 줄일 수 있다는 결과입니다. ntk를 이런 곳에서 보게 될 줄은 몰랐네요.

결과적으로 perplexity에서 손해를 보는데 파인튜닝으로 개선될 수 있을 것 같네요.

https://twitter.com/Teknium1/status/1674546147409682432?s=20

이쪽은 mpt-7b에 대해 passphrase test를 했을 때 실질 context length가 3000 토큰 정도라는 실험 결과입니다.

https://lmsys.org/blog/2023-06-29-longchat

rope interpolation + finetuning으로 16k 모델을 만들어서 retrieval 과제로 평가해본 결과가 나왔군요. mpt-7b나 chatglm2 같이 long context에 대해 파인튜닝된 모델들이 잘 작동하지 않는 반면 interpolation 모델이 좀 더 나은 특성을 보여주는군요. 그런데 claude 100k나 gpt-3.5-turbo-16k는 16k 내에서 거의 완벽한 수치가 나오네요.