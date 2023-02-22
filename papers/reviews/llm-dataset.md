# 230222 LLM 필요 데이터셋에 대한 리뷰

# Overview

## 파라미터와 필요 데이터셋의 규모

| 모델 | 파라미터 | 학습 토큰 | 비고 |
|-----|--------:|---------:|------|
| [GPT-3](https://arxiv.org/abs/2107.03374) | 175B | 300B | |
| [Gopher](https://arxiv.org/abs/2112.11446) | 280B | 300B | |
| [Chinchilla](https://arxiv.org/abs/2203.15556) | 70B | 1.4T | |
| [OPT](https://arxiv.org/abs/2205.01068) | 175B | 300B | 데이터셋은 180B 규모 |
| [BLOOM](https://arxiv.org/abs/2211.05100) | 176B | 300B | 영어는 100B 정도 샤용됨 |
| [PaLM 62B](https://arxiv.org/abs/2204.02311) | 62B | 795B | |
| [PaLM](https://arxiv.org/abs/2204.02311) | 540B | 780B | |

Chinchilla-optimal한 모델 학습을 위해서는 70B 모델에도 1.4T 토큰이 필요. PaLM에서는 좀 다른 scaling을 사용했는데 어느 쪽이 더 나은지는 분명하지 않음. 다만 분명한 것은 175B 파라미터/300B 토큰이라는 GPT-3의 세팅은 undertraining이라는 것일 듯. (Gopher vs Chinchilla/PaLM-62B, 그리고 OPT와 BLOOM의 학습 문제에서 발견됨.)

## 데이터셋 구성

### 높은 퀄리티의 웹 문서

필터링을 거친 웹 크롤링 문서를 사용함. (Common Crawl, C4, MassiveText) 퀄리티 판단을 위해서는 퀄리티 분류기를 쓰거나 혹은 휴리스틱으로 태클함. 혹은 Reddit Karma를 사용한 휴리스틱을 사용하기도 함. (WebText)

중요한 포인트로 보이는 것은 이 웹문서들에는 학술 문서들이 포함되어 있다는 것. MassiveWeb 데이터를 구성하는 도메인들 중 최상단에는 sciencedirect.com이나 gale.com 같은 도메인이 포함되어 있음. 따라서 오픈 액세스 저널의 논문들이 상당 수 포함되어 있으리라고 생각됨. 그러니 단순히 웹 포럼이나 커뮤니티 데이터로만 생각할 수는 없음. (물론 그쪽 데이터가 총량이 많겠지만.) 그러니 웹 문서라는 큰 범주의 유사성을 넘어 질적 유사성도 고려해야 하는 것이 아닐까 생각.

### 정체불명의 책

GPT-3, Gopher / Chinchilla, PaLM 모두 Books라는 이름의 데이터셋을 포함하고 있음. 다만 웹 문서에 비해 이 데이터들은 정체가 불명확함. Project Gutenberg 같은 데이터라고 추정하기엔 그 규모가 너무 큼. (The Pile V2에서 수집한 Project Gutenberg 데이터가 20 GB 정도, Bibliotik을 사용해서 책 200K 권을 사용 Books3 데이터가 100 GB 정도.) [https://twitter.com/theshawwn/status/1320282149329784833](https://twitter.com/theshawwn/status/1320282149329784833) 저작권 등의 문제가 있는 데이터일 수 있다고 추정하는 것도 이상하지는 않은 듯. 이 형태의 데이터가 구하기 가장 까다로운 형태가 아닐지 생각됨.

### 위키피디아

포함하지 않을 이유가 없으니 꼭 들어가지만 비중이 그렇게 높지는 않음. 다만 샘플링 비율 때문에 학습시 Epoch가 큼.

### GitHub

코드가 데이터로 들어가는 것이 대세가 됨. 보통 GitHub 데이터를 포함하고 있는 듯. Codex 논문에서는 파이썬만 사용했다고 하지만, 이후 MassiveText처럼 주요 언어들의 데이터가 모두 포함됐을 듯. 코드 특화된 어떤 전처리들이 쓰였는지가 잘 안 나와 있는 것 같긴 한데, 파이썬이라면 black이나 C/C++이라면 clang-format 같은 정석적인 포매터를 한 번 돌리지 않았을지?

### 기타

MassiveText, PaLM 데이터셋에는 News 데이터셋 카테고리가 따로 분리되어 있음. 뉴스를 추가로 집중적으로 수집했다는 의미일지도.

Meena/LaMDA/PaLM의 경우에는 공개 소셜 미디어 대화 데이터를 주요하게 활용하고 있음. LaMDA 논문을 참조하면 그렇다고 대화 데이터만 포함되어 있는 것은 아니고 일반적인 웹 크롤링 데이터도 많이 포함되어 있음. 다만 공개 포럼의 쓰레드가 대화 형태로 가공되어 많이 들어가 있는 것으로 보임.

절대적인 양이 중요한가? 즉 웹 크롤링 데이터셋으로 전체를 채워도 충분한가? 혹은 서적 데이터는 웹 데이터셋과는 다른 가치가 있는가? 다른 가치가 있으리라고 생각되지만 확실하지는 않음.

## 데이터 전처리

### 1단계 필터링

MassiveText 같은 경우 Google SafeSearch를 사용해서 일단 걸러냄. 또한 사용할 언어만 걸러내는 작업을 수행.

### 텍스트 추출

크롤링된 문서에서 보일러플레이트와 마크업을 제거. 그러나 마크업의 특성을 사용해 유지하고자 하는 구조가 손상되지 않도록 할 필요가 있음. 이쪽에서도 퀄리티를 올리기가 쉽지 않은 것으로 보임. The Pile에서는 Newspaper, Trafilatura, Goose3, DragNet 중 jusText를 선택함. 벤치마크 까지는 하지 못하고 결과물을 살펴보고 판단했다고 함.

### 퀄리티 필터링

GPT-3 같은 경우 WebText 데이터를 높은 퀄리티의 데이터로 임의로 선정하고 크롤링 문서 일반을 낮은 퀄리티의 문서로 지정해 학습된 분류기로 필터링함. PaLM의 경우도 비슷. 단 MassiveWeb 같은 경우는 분류기를 사용할 경우의 bias를 우려해 휴리스틱으로 태클함. 그러나 MassiveWeb의 수집 대상이 Common Crawl과 달랐기에 휴리스틱만으로 태클할 수 있는 범위가 넓었던 것이 아닐까 하는 생각도 듦.

### 반복 텍스트 제거

반복된 텍스트가 등장해서 문제를 야기하기에 필터링하는 것이 필수. BigScience에서 작업하면서 모델이 계속 터지길래 데이터를 봤더니 백슬래시가 500,000개 들어있었다는 이야기가 있음. [https://www.youtube.com/watch?v=AJwnbSP_rq](https://www.youtube.com/watch?v=AJwnbSP_rq) MassiveText의 경우 라인, 문단, n-gram 별로 문자 비율까지 고려해 제거함.

### 중복 문서 제거

문서 레벨에서 중복된 샘플들을 제거. MinHashLSH가 자주 사용되고 MassiveText의 경우에는 n-gram Jaccard similarity를 사용.

### 테스트셋 문서 제거

평가를 정확하게 하자면 (사실 불충분하겠지만) 테스트셋과 중복되는 샘플에 대한 제거 또한 필요.

### 그 외

구체적인 도메인의 데이터셋에 특화된 전처리, 프라이버시 이슈 대응을 위한 익명화 등이 필요. The Pile에 각 데이터 소스별로 사용한 전처리 도구들이 정리되어 있음.

### 코드

[https://github.com/EleutherAI/the-pile](https://github.com/EleutherAI/the-pile) [https://github.com/EleutherAI/dps](https://github.com/EleutherAI/dps) 일반적인 프로세스는 EleutherAI 쪽에서 구현된 코드들이 있다. 추가적으로 각 도메인과 데이터셋을 보면서 적절한 휴리스틱으로 퀄리티를 높여나가는 것이 중요할 듯 싶다.

# 각 모델에서의 방법들 정리

## GPT-3

[https://arxiv.org/abs/2107.03374](https://arxiv.org/abs/2107.03374)

| 데이터셋 | 토큰 | 샘플링 비율 | Epoch | 비고 |
|---|---:|---:|---:|---|
| Common Crawl | 400B | 60% | 0.44 | 2016-2019, 필터링 결과 45TB -> 570GB |
| WebText2 | 19B | 22% | 2.9 | Reddit 카르마 3 아웃바운드 링크, WebText 1: ~ 2017.12, 45M 링크, - Dragnet & Newspaper Extractor, 8M 필터링 후 문서, 40 GB, WebText2: 2018.10 ~, Newspaper3k, 20.3M 문서, 96 GB |
| Books1 | 12B | 8% | 1.9 | 정체 불명 |
| Books2 | 55B | 8% | 0.43 | 정체 불명 |
| Wikipedia | 3B | 3% | 3.4 | |

### 프리프로세싱

Spark 토크나이저 & HashingTF 피처 기반 로지스틱 분류기. MinHashLSH (10 Hash)를 사용한 퍼지 deduplication.

### 이후

[Codex](https://arxiv.org/abs/2107.03374)에서 GitHub 코드 데이터가 추가됨. 파이썬 코드만 포함했다고 하는데 이후에는 다른 언어도 마음껏 추가했을 듯.

## Gopher / Chinchilla

[https://arxiv.org/abs/2112.11446](https://arxiv.org/abs/2112.11446)
[https://arxiv.org/abs/2203.15556](https://arxiv.org/abs/2203.15556)

| 데이터셋 | 디스크 용량 | 토큰 | 문서 수 | 샘플링 비율 (Gopher) | 샘플링 비율 (Chinchilla) | Epoch (Chinchilla) | 비고 |
|------------|--------:|-----:|-----:|----:|----:|-----:|------------------|
| MassiveWeb | 1.9TB   | 506B | 604M | 48% | 45% | 1.24 | 커스텀 HTML 크롤러 |
| Books      | 2.1TB   | 560B |   4M | 27% | 30% | 0.75 |                  |
| C4         | 0.75TB  | 182B | 361M | 10% | 10% | 0.77 |                  |
| News       | 2.7TB   | 676B | 1.1B | 10% | 10% | 0.21 |                  |
| GitHub     | 3.1TB   | 422B | 142M |  3% |  4% | 0.13 | 허용적 라이센스만  |
| Wikipedia  | 0.001TB |   4B |   6M |  2% |  1% | 3.40 |                  |

### Colossal Clean Crawled Corpus (C4)

[https://arxiv.org/abs/1910.10683](https://arxiv.org/abs/1910.10683)

- 마침표, 느낌표, 물음표, 따옴표로 끝나는 라인만 사용
- 5 문장 미만인 페이지 제외, 3 단어 이상인 라인만 사용
- 단어 필터링
- Javascript로 시작하는 라인 제거 (javascript should be enabled 메시지인 케이스 대응)
- lorem ipsum이 등장하는 경우 제거
- curly bracket { 이 등장하는 경우 제거 (코드 제거)
- 3 문장 스팬을 사용해 deduplication

### 프리프로세싱

분류기 기반 필터링을 사용하지 않음 - 특정 인구 집단, 방언을 지울 수 있다고 봤음.

컨텐츠 필터링: 영어만, Google SafeSearch 필터 (단어 목록 필터링은 하지 않음 - 소수자 집단을 불균등하게 필터링함.)

텍스트 추출 (MassiveWeb): HTML 구조 기반 휴리스틱, 들여쓰기, 개행, 불릿 포인트 보존

텍스트 퀄리티 필터링 (MassiveWeb): 길이 제한 50 <= x <= 100,000 & 평균 단어 길이 3 <= x <= 10. Hash 기호 (샵?) 이나 생략 부호의 비율이 단어의 10%를 초과하면 필터링, 90% 이상의 라인이 불릿 포인트로 시작하면 필터링, 30% 이상이 생략 부호로 끝나면 필터링, 최소 80%의 단어가 알파벳을 하나 의상 포함해야함, Stop word (the, be, to, of, and, that, have, with) 중 최소 둘 이상이 포함되어야함

반복 텍스트 제거: 반복된 라인, 문단, n-gram의 비율이 높은 문서 제거. 라인과 문단에 대해서는 중복인 경우의 비율과 중복 내부의 문자의 비율을 고려. 2\~4-gram에 대해서는 가장 자주 등장하는 n-gram에 들어있는 문자의 비율, 5\~10-gram에 대해서는 모든 중복된 n-gram에 포함된 문자의 비율을 고려하되 중복되는 n-gram에 등장하는 문자를 한 번 이상 계산하지 않도록 주의. 이 비율이 특정 역치를 넘어가면 필터링.

중복 문서 제거: 13-gram Jaccard similarity. 공백과 구두점 제거. similarity가 0.8 이상은 경우 둘 중 한 문서를 랜덤하게 제거.

## PaLM

[https://arxiv.org/abs/2204.02311](https://arxiv.org/abs/2204.02311)

| 데이터셋 | 비율 | 비고 |
|---------|-----:|----|
| Social Median Conversations (Multilingual) | 50% | |
| Filtered Webpages (Multilingual) | 27% | | 
| Books (English) | 13% | |
| GitHub (Code) | 5% | Copyleft 제외, 24개 주요 언어 (196 GB), edit distance 기반 중복 제거 |
| Wikipedia (Multilingual) | 4% | |
| News (English) | 1% | |

총 780B 토큰, GLaM/LamDA 데이터 기반. Multilingual이지만 데이터셋의 78%는 영어.

### LamDA 데이터셋의 구성

[https://arxiv.org/abs/2201.08239](https://arxiv.org/abs/2201.08239)
[https://arxiv.org/abs/2112.06905](https://arxiv.org/abs/2112.06905)

문서 수 2.97B, 1.12B 대화와 13.39 utterance, 1.56T 단어. 50%는 공개 포럼의 대화 데이터, C4 데이터 12.5%, 위키피디아 12.5%, 6.25% 웹 문서, 6.25% 비 영어 문서

### Meena의 데이터셋, 전처리

[https://arxiv.org/abs/2001.09977](https://arxiv.org/abs/2001.09977)

소셜 미디어 대화를 트리 형태로 구성.

* Subword < 2 혹은 > 128인 경우 필터링. 언어 모델에는 쓰지 않았을 듯.
* 알파벳 문자가 70% 이하인 경우 필터링
* URL이 포함된 메시지는 필터링. 이쪽도 안 썼을 듯.
* 유저명에 "bot"이 포함된 경우 필터링.
* 100번 이상 반복된 경우 필터링
* 부모 텍스트와 n-gram 중복이 클 경우 필터링
* 텍스트 분류기로 위험하거나 공격적인 텍스트 필터링

Conversations에는 일자 마커가 있음. 알고리즘을 사용해 추출함.

Web documents: 퀄리티 분류기(Feature Hash 기반 선형 분류기)에서 높은 퀄리티로 분류된 경우 혹은 Colossal Clean Crawled Corpus에 있는 경우, 상용 소프트웨어로 보일러플레이트 제거, HTML 마크업 제거

## HyperCLOVA

[https://arxiv.org/abs/2109.04650](https://arxiv.org/abs/2109.04650)
[https://arxiv.org/abs/2204.13509](https://arxiv.org/abs/2204.13509)

| 데이터셋 | 토큰 |
|---------|-----:|
| Blog | 273.6B |
| Cafe | 83.3B |
| News | 73.8B |
| Comments | 41.1B |
| KiN | 27.3B |
| Modu | 6.0B |
| WikiEn, WikiJp | 5.2B |
| Others | 51.5B |
| Total | 561.8B |

### 프리프로세싱

BERT feature 기반 로지스틱 분류기, Hash를 사용한 deduplication, 자체 스팸 필터링, 너무 짧거나 반복적인 자소, 숫자, 특수문자, 너무 많은 욕설이나 슬랭, 제목과 내용 사이의 중복 문장 제거.

익명화 - 주민등록번호, 이메일, 전화번호, 계좌번호, 카드번호, 여권번호, 운전면허증 번호 등.

## The Pile

[https://arxiv.org/abs/2101.00027](https://arxiv.org/abs/2101.00027)

* 학술: arXiv, PubMed Central, NIH Explorer, PubMed Abstracts, PhilPapers
* 서적: Project Gutenberg, BookCorpus2, Books3
* 코드: Pile GitHub, StackExchange
* 대화: OpenSubtitles, Ubuntu IRC, YouTube Subtitles
* 이메일: Enron Emails
* 일반 정보: Wikipedia (English)
* 정부 기록: EuroParl, FreeLaw, DM Mathematics
* 기술 문서: USPTO Backgrounds
* 인터넷 포럼: HackerNews
* 웹 문서: Pile-CC, OpenWebText2

### Pile V2 추가 예정 문서

* 코드: Code Pile, Github Scrape
* 정부 기록: SEC, Inspectors Geenral
* 수학: AMPS
* 인터넷 포럼: Pushshift Reddit, 유즈넷

### Pile V2 추가 가능 문서

* 대화: Ubuntu IRC
* 웹 문서: Pile-CC, OpenWebText2
* 법률: Pile of Law
* 학술: Biodiversity heritage library

### Pile V2 제외 문서

* 학술: NIH Explorer
* 서적: BookCorpus2, Books3
* 대화: OpenSubtitles
* 수학: OpenAI Grade School Math
* 인터넷 포럼: HackerNews
* 법률: Case.Law

### 프리프로세싱

jusText를 사용한 텍스트 추출, pycld2 언어 분류, 2-gram fasttext 기반 퀄리티 분류기. 각 데이터셋에 특화된 전처리 존재. MinHashLSH를 사용한 deduplication.

## OPT

[https://arxiv.org/abs/2205.01068](https://arxiv.org/abs/2205.01068)

* BookCorpus
* CC-Stories
* The Pile
* Pushshift.io Reddit Dataset
* CCNewsV2

## BLOOM BigScience ROOTS

[https://arxiv.org/abs/2211.05100](https://arxiv.org/abs/2211.05100)
[https://openreview.net/forum?id=UoEw6KigkUn](https://openreview.net/forum?id=UoEw6KigkUn)

### 프리프로세싱

[https://github.com/bigscience-workshop/data-preparation](https://github.com/bigscience-workshop/data-preparation)

* 자체 구현한 HTML 추출기
* 단어 숫자 피렅링
* 문자 n-gram 반복 텍스트 필터링
* 단어 n-gram 반복 텍스트 필터링
* 특수문자 필터링
* 문법 기능을 하는 단어(closed class word)들의 비율 필터링
* 단어 목록 기반 필터링
* 언어 예측 점수 기반 필털이
* 5-gram Perplexity 필터링

단, ROOTS의 전처리는 그렇게 좋은 상황은 아니었던 것으로 보임.