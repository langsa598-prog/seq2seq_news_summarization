# Transformer-based Korean News Summarization

본 프로젝트는 Transformer 기반 Seq2Seq 모델을 활용하여  
한국어 뉴스 기사에 대한 자동 요약 모델을 구현한 미니 프로젝트입니다.  

1주일 동안 모델 학습부터 성능 평가, 간단한 웹 데모 구현까지 진행했습니다.

---

## 📌 Project Overview

뉴스 기사와 같은 긴 문서는 핵심 내용을 빠르게 파악하기 어렵습니다.  
이를 해결하기 위해 Pretrained Transformer 모델을 Fine-tuning하여  
한국어 뉴스 요약(Abstractive Summarization) 모델을 구현했습니다.

프로젝트 범위는 다음과 같습니다:

- 모델 Fine-tuning
- Validation 기반 성능 평가 (ROUGE)
- Gradio 기반 요약 데모 구현

---

## Dataset

- Input: 뉴스 기사 본문
- Target: 해당 기사 요약문
- Train / Validation 분리 후 학습 진행
- 최대 입력 길이 제한 및 토큰 truncation 적용

---

## Model

- Transformer 기반 Encoder–Decoder 구조
- Pretrained Seq2Seq 모델 Fine-tuning
- Beam Search 기반 텍스트 생성

### Training Settings

- Max input length: 384
- Max output length: 128
- Batch size: 16
- Beam size: 4
- Validation 기반 성능 평가

---

## Evaluation

Validation Set 기준 ROUGE 지표를 사용하여 성능을 평가했습니다.

- ROUGE-1
- ROUGE-2
- ROUGE-L

이를 통해 모델의 핵심 단어 재현 능력과 문장 유사도를 확인했습니다.

---

## Demo (Gradio)

Gradio를 활용하여 웹 기반 요약 데모를 구현했습니다.  
사용자가 텍스트를 입력하면 모델이 요약 결과를 생성합니다.


```bash
pip install transformers gradio torch
python app.py
