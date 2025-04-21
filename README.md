# 💬 ABSA 감정분석 트랜스포머 프로젝트

> 트랜스포머 아키텍처를 감정 분석용으로 리팩토링하여 **속성 기반 감정 분석(ABSA)** 수행  
> 📂 학습 및 실험 데이터 출처: [Korean-ABSA-Dataset (GitHub)](https://github.com/lydiahjchung/Korean-ABSA-Dataset/tree/main)

---

## 📌 프로젝트 개요

이 프로젝트는 트랜스포머 모델의 구조를 학습하고, 이를 감정 분석 문제에 최적화된 형태로 리팩토링하여 적용해본 **개인 실습 프로젝트**입니다.  

기존 챗봇용 트랜스포머에서 **디코더를 제거**하고, **인코더 기반 구조만을 활용**해 **감정 분류에 적합한 경량 모델**로 재구성하였습니다.  

모델은 **TensorFlow / Keras**로 구현되었으며, 약 **5,000개의 한국어 리뷰 데이터셋**을 기반으로 감정 분석을 수행했습니다.

---

## 🛠️ 기술 스택

| 구분 | 내용 |
|------|------|
| **Framework** | TensorFlow / Keras |
| **NLP 라이브러리** | Hugging Face Transformers, Datasets |
| **토크나이저** | AutoTokenizer |
| **언어** | Python 3.9 |

---

## 🎯 핵심 목표

1. 트랜스포머 구조의 핵심 요소를 직접 구현하며 구조에 대한 이해도 향상  
2. 감정 분석에 적합한 **커스텀 트랜스포머 아키텍처** 설계  
3. **소규모 데이터셋 기반**의 성능 실험 및 한계 체험  

---

## 🧪 프로젝트 과정

### 1️⃣ 데이터셋 전처리 및 토크나이징
- Hugging Face의 `AutoTokenizer`를 사용해 **텍스트를 토큰화**
- `Datasets` 구조를 이해하고, 모델 학습에 맞는 형태로 변환
- 데이터 전처리의 효율성과 구조적 이해도 향상

### 2️⃣ 모델 리팩토링
- **기존 트랜스포머 챗봇 모델**에서 디코더 제거
- 인코더만 활용한 구조로 **감정 분석에 적합한 경량 모델 구현**

### 3️⃣ Distillation 시도
- 성능과 효율성 향상을 위해 **Knowledge Distillation**을 시도
- 하지만 **Teacher 모델을 fine-tuning**하는 것부터 난관이 있었고, 시간과 리소스 부족으로 최종적으로 포기
- 이를 통해 **Fine-tuning의 난이도와 중요성**을 실감함

---

## 🧩 프로젝트 중 겪은 어려움과 배운 점

### 🔧 하이퍼파라미터 튜닝
- 트랜스포머 모델의 특성상 **작은 변경도 성능에 큰 영향**
- 적절한 learning rate, batch size, optimizer 선정에 많은 실험이 필요했음

### 📦 Hugging Face 생태계 이해
- `AutoTokenizer`와 `Datasets` 구조를 직접 다루면서 **Hugging Face의 생태계 전반에 대한 이해도 향상**

### 🧪 Distillation의 한계 체험
- `Distillation`은 매력적인 기법이지만, **teacher 모델 fine-tuning 자체가 어려웠음**
- 리소스 부족 및 복잡성으로 인해 학습이 쉽지 않았고, **모델 압축의 실질적인 어려움**을 체감함

---

## 🔭 향후 개선 방향

- 🔄 **대규모 데이터셋**으로 재학습하여 구조의 일반화 성능 평가  
- 🔁 **사전 학습 임베딩 / 전이학습** 활용한 성능 개선 실험  
- 📉 다양한 **정규화 기법 / 학습률 스케줄링** 적용  

---

## 📎 참고
- 데이터셋: [Korean ABSA Dataset](https://github.com/lydiahjchung/Korean-ABSA-Dataset/tree/main)  
- 개발 환경: Python 3.9, TensorFlow 2.0


![loss그래프](https://github.com/user-attachments/assets/38bc3e1d-8721-4cf9-a931-e844560562ea)

![acc그래프](https://github.com/user-attachments/assets/0edd306b-a6cb-4903-a89f-97119752ba85)


