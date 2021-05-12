https://github.com/uds-lsv/bert-stable-fine-tuning
On the Stability of Fine-tuning BERT: Misconceptions, Explanations, and Strong Baselines (Marius Mosbach, Maksym Andriushchenko, Dietrich Klakow)

arXiv에 올라오지는 않았지만 재미있는 결과. BERT 파인튜닝이 불안정한 이유는 forgetting도 아니요 데이터 수 부족도 아니요 그냥 배니싱 그래디언트로 최적화 자체가 잘 안 되기 때문인 영향이 컸다. adam bias correction을 사용하는 것이 중요. warmup으로는 부족한 듯. post norm 때문일 것이라는 의심이 듦.

#bert #finetuning