https://arxiv.org/abs/2306.09782

Full Parameter Fine-tuning for Large Language Models with Limited Resources (Kai Lv, Yuqing Yang, Tengxiao Liu, Qinghui Gao, Qipeng Guo, Xipeng Qiu)

lora 대신 full parameter finetuning을 메모리를 아끼면서 할 수 있는가. sgd를 써서 optimizer state를 없애고 그래디언트가 들어오면 파라미터를 업데이트하고 그래디언트를 지우는 방식으로 처리 + activation checkpointing 조합이군요. sgd를 써야 한다는 것이 제약이고 global grad norm clipping을 못 쓴다는 것이 제약인데...괜찮은 결과를 보고하고 있긴 하네요.

#finetuning #llm