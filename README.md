# 💱 환율 예측 모델 개발 프로젝트

<p align="center">
  <img src="https://i.pinimg.com/736x/35/65/45/3565455fb9a97d8cc3366d9623861799.jpg" width="600"/>
</p>

## 📌 프로젝트 개요
본 프로젝트는 **원화의 환율(대미달러)**을 예측하기 위한 머신러닝 기반 모델을 개발하고,  
정책 변수와 거시경제 변수의 영향력을 분석함으로써 **실제 환율 결정 요인에 대한 인사이트**를 도출하는 것을 목표로 합니다.

---

## 🎯 예측 목표
- **Target (타겟):**  
  - `KRW/USD` (원/달러 환율)  

- **예측 방식:**  
  - 회귀 기반 시계열 예측  
  - 머신러닝/딥러닝 모델 (LSTM, Bidirectoinal LSTM, Arima, Prophet, XGBoost, LightGBM, RandomForest 등) 적용

---

## 📊 주요 활용 데이터

| 구분 | 변수 | 설명 |
|------|------|------|
| 🔹 거시경제 지표 | GDP, GNI, GDP성장률, KOSPI, NASDAQ, 경제심리지수, 뉴스심리지수, 한국실업률, 미국실업률, 미국소비자심리지수 | 중장기 환율 흐름 반영 |
| 🔸 금융시장 지표 | 기준금리, 미국기준금리, CD(91일), 무담보콜금리(1일, 전체거래), 국고채(3년), 국고채(10년), 대외채권, 대외채무, 순대외채권, 이ㅗ환보유액 | 금융시장 지표로서 환율에 영향끼치는 요소 반영 |
| 🔹 물가 및 가격 지표 | CPI, PPI, 미국CPI, 미국PPI | 시장 흐름 반영 |
| 🔸 수출입 관련 지표 | 수출물가지수(원화기준/계약통화기준/달러기준), 수입물가지수(원화기준/계약통화기준/달러기준), 경상수지(계절조정), 수출금액지수, 수입금액지수 | 무역 시장 흐름 반영 |
| 🔹 환율 및 외환시장 | 원/미국달러(매매기준율), 일본엔/달러, 달러/유로, 중국위안/달러, 본원통호(달러 발행량) | 실제 환율 흐름 반영 |
| 🔸 원자재 가격 | 금, 은, 원유 | 원유와 같은 필수 원자재 가격 반영 |

> ※ 데이터 출처: 한국은행 ECOS Open API, 통계청, 기획재정부, 연준, 외부 금융 포털 등

---

## 🔧 사용 기술

- **Language**: Python 3.11+
- **Library**:
  - `pandas`, `numpy`, `scikit-learn`, `tensorflow`, `keras`  
  - `xgboost`, `lightgbm`  
  - `matplotlib`, `seaborn`  
  - `requests` (API 연동)

---

## 📈 모델링 전략

1. **전처리**
   - 분기/월별 데이터를 일자별로 확장 (interpolation 활용)
   - 결측치 보간 및 스케일링

2. **특징 선택 및 생성**
   - 시차 변수(lag), 이동평균(ma3), 변화율(pct), 차이(diff) 등의 파생 변수 생성

3. **모델 학습**
   - 다양한 머신러닝 모델 비교 적용
   - 시계열에 적합한 cross-validation

4. **모델 평가**
   - RMSE, MAE, R² 등 평가 지표
   - 변수 중요도 분석 → 정책 vs 거시경제 영향력 평가

---

## 🔍 기대 효과
- **환율 움직임에 대한 정량적 해석 제공**
- **국내외 경제 지표 변화에 따른 환율 반응 예측**
- **정책 결정 및 환위험 관리에 실질적 도움**

---

## 👥 프로젝트 기여자

| 이름 | 역할 |
|------|------|
| 박효은 | 데이터 분석, 모델링 |
| 이상기 | 데이터 수집 및 전처리 |
| 허세은 | 시각화 및 인사이트 도출 |
| 문규빈 | 데이터 통합 및 API 연동 |
| 조성준 | 분석 자동화, 리서치 |

---
