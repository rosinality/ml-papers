https://arxiv.org/abs/2304.08109

A Comparative Study between Full-Parameter and LoRA-based Fine-Tuning on Chinese Instruction Data for Instruction Following Large Language Model (Xianghui Sun, Yunjie Ji, Baochang Ma, Xiangang Li)

instruction tuning에서 lora vs full parameter finetuning. 이 문제가 궁금하던 상황이라 눈에 띄어서 봤는데...일단 논문에서는 full parameter tuning이 낫다고 보고하고 있지만 lora 세팅이 충분히 최적화된 것이었는지는 잘 모르겠네요. rank 8을 사용했는데, deepspeed chat에서는 의도한 것인지는 모르겠지만 128을 사용하더군요.

#llm #instruct 