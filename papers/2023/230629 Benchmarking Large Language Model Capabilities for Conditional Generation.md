https://arxiv.org/abs/2306.16793

Benchmarking Large Language Model Capabilities for Conditional Generation (Joshua Maynez, Priyanka Agrawal, Sebastian Gehrmann)

llm의 generation task들에 대한 테스트군요. encoder-decoder vs decoder-only, multilinguality, few-shot vs finetuning 등의 조건에서 data to text, english generation, crosslingual generation, multilingual summarization 등의 과제에 대해 테스트해봤군요.대체로 기대할만한 결과가 나온 것 같긴 합니다. (finetuning이 few shot보다 강하긴 함, encoder-decoder 모델이 이점이 있긴 하지만 decoder only 모델이 커지면 따라잡을 수 있음, multilingual input보다 output이 어려움 등.) 그나저나 code-davinci-002가 새삼 강한 모델이구나 싶네요.

#llm #evaluation 