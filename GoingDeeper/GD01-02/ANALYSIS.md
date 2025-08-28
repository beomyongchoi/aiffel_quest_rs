# 네이버 영화리뷰 감정분석 모델 성능 비교 분석

---

## 1. 최종 결과 요약

다양한 토크나이저(Okt, Mecab, SentencePiece)와 모델(BiLSTM, 1D CNN)을 조합한 네이버 영화리뷰 감정분석 수행 결과

| 토크나이저 | 모델 | 정확도 (Accuracy) | 관련 노트북 |
| :--- | :--- | :--- | :--- |
| **Mecab** | **BiLSTM** | **`0.8551`** | [nsmc_with_mecab.ipynb](./nsmc_with_mecab.ipynb) |
| **Mecab** | **1D CNN** | `0.8534` | [nsmc_with_mecab.ipynb](./nsmc_with_mecab.ipynb) |
| SentencePiece (Unigram) | 1D CNN | `0.8484` | [nsmc_with_sentencepiece_v3.ipynb](./nsmc_with_sentencepiece_v3.ipynb) |
| Okt | BiLSTM | `0.8486` | [nsmc_with_okt.ipynb](./nsmc_with_okt.ipynb) |
| SentencePiece (BPE) | 1D CNN | `0.8476` | [nsmc_with_sentencepiece_v3.ipynb](./nsmc_with_sentencepiece_v3.ipynb) |
| Okt | 1D CNN | `0.8474` | [nsmc_with_okt.ipynb](./nsmc_with_okt.ipynb) |
| SentencePiece (Unigram) | BiLSTM | `0.8458` | [nsmc_with_sentencepiece_v3.ipynb](./nsmc_with_sentencepiece_v3.ipynb) |
| SentencePiece (BPE) | BiLSTM | `0.8434` | [nsmc_with_sentencepiece_v3.ipynb](./nsmc_with_sentencepiece_v3.ipynb) |

## 1-1. 추가 실험

`vocab_size` 변경에 따른 성능 분석

| Vocab Size | BiSLTM Accuracy | 1D CNN Accuracy |
| :--- | :--- | :--- |
| 4000 | 0.8449 | 0.8471 |
| 8000 | 0.8445 | 0.8472 |
| 16000 | 0.8440 | 0.8461 |
| 32000 | 0.8384 | 0.8382 |

1. 성능 포화 
- 이미 Vocab 8,000개 수준에서 핵심단어나 서브워드는 대부분 포함된 것으로 보임

2. SentencePiece 의 장점이 보임
- `vocab_size` 크기에 따라 서브워드를 모델이 알아서 조절해 OOV문제에 강한 것 처럼 보임
- 위 실험에서 `vocab_size`에 따른 변화를 볼거였으면 차라리 사이즈를 더 줄여보는게 실험적으로 유의미 했을 것으로 보임
- 네이버 영화 리뷰는 8,000개면 충분한 `vocab_size`여서 32,000 까지 늘리더라도 체감되는 효과는 없었음 

## 2. 분석

### 결론 1: 토크나이저의 선택이 모델 성능에 가장 큰 영향
모델 구조(LSTM vs CNN)를 변경했을 때보다 토크나이저를 교체했을 때 정확도 변화가 생겼다.
한국어의 언어적 특성을 잘 반영한 **Mecab**이 모든 조합 중 가장 뛰어난 성능을 보여줌

### 결론 2: Mecab 이 SentencePiece 보다 우세
리뷰 데이터 처럼 문법적으로 잘 정제된 데이터의 경우, 단어의 의미 단위인 형태소를 정확히 분리하는 것이 통계적으로 분리하는 것보다 감정 분석에 더 효과적으로 보임
모델이 문장의 문법적 구조를 이해하도록 더 잘 돕는 것으로 판단

### 결론 3: SentencePiece는 뛰어난 범용성과 가능성을 보여줌
Mecab보다 성능은 낮았지만, SentencePiece는 언어학적 지식이나 설치 과정 없이도 비슷한 성능 기록
언어에 구애받지 않고 다양한 데이터에 빠르게 적용할 수 있는 장점


## 3. 전체 실험 과정 노트북

- **SentencePiece 최초 학습 모델**
  - `[nsmc_with_sentencepiece.ipynb](./nsmc_with_sentencepiece.ipynb)`
- **SentencePiece 리팩토링 버전**
  - `[nsmc_with_sentencepiece_v2.ipynb](./nsmc_with_sentencepiece_v2.ipynb)`
- **KoNLPy (Okt) 비교 모델**
  - `[nsmc_with_okt.ipynb](./nsmc_with_okt.ipynb)`
- **KoNLPy (Mecab) 비교 모델**
  - `[nsmc_with_mecab.ipynb](./nsmc_with_mecab.ipynb)`
- **SentencePiece (Unigram vs BPE) 비교 모델**
  - `[nsmc_with_sentencepiece_v3.ipynb](./nsmc_with_sentencepiece_v3.ipynb)`
- **SentencePiece (vocab_size) 성능 테스트**
  - `[nsmc_sp_vocab_test.ipynb](./nsmc_sp_vocab_test.ipynb)`
