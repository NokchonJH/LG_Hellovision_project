# HV Project  
**AI 기반 셋톱박스 장애 사전 감지 및 경고 시스템**

---

## 📁 Repository 구조
Display_SensorData ├── 📁 src │ ├── 📁 1. 데이터 탐색 및 전처리 │ │ ├── 📃 EDA&preprocessing_df.ipynb │ ├── 📁 2. 데이터 시각화 │ │ ├── 📃 Visualization.ipynb │ ├── 📁 3. 모델링 수행 및 비교 │ │ ├── 📃 train.jpynb │ └── 📁 4. 모델을 통한 예측결과 확인 │ └── 📃 prediction_temp.ipynb ├── 📁 img (README.md 관련 이미지) └── 📁 old_code (시행착오 소스코드)

---

## 📚 목차

1. [분석 환경 및 도구](#-분석-환경-및-도구)
2. [프로젝트 개요](#-프로젝트-개요)
   - [프로젝트 목적](#프로젝트-목적)
   - [프로젝트 배경](#프로젝트-배경)
3. [프로젝트 수행내용 요약](#-프로젝트-수행내용-요약)
   - [데이터 탐색](#데이터-탐색)
   - [데이터 전처리](#데이터-전처리)
   - [모델 학습](#모델-학습)
   - [분류 모델 수행](#분류-모델-수행)
4. [프로젝트 결론](#-프로젝트-결론)

---

## 💻 분석 환경 및 도구

- **HW/Server**
  - Windows 11 (AMD Ryzen 7 7730U, RAM 16GB)
  - Amazon Linux 2023
- **Language**
  - Python 3.11.5
- **Tools**
  - Docker 25.0.3
  - GitHub, AWS, Slack, Notion, JIRA
- **IDE**
  - Jupyter Notebook 7.0.8
- **Libraries**
  - Pandas 2.2.2, Numpy 1.26.4, Sklearn 1.5.0, Matplotlib 1.3.0, Seaborn 0.13.2, SHAP 0.45.1

---

## 🌿 프로젝트 개요

### 프로젝트 목적
- 셋톱박스 데이터 분석을 통해 **장애 발생 사전 예측**  
- Flask를 활용하여 **장애 알림 웹 시스템 개발**  
- 장애 사전 탐지 및 신속한 유지보수를 통해 **고객 만족도 향상**  

### 프로젝트 배경
- **과학기술정보통신부의 유료방송서비스 품질평가**에 따르면, LG헬로비전의 이상 화면 발생 빈도는 2022년 대비 2023년에 약 3배 증가.  
- 이로 인해 고객 만족도가 감소했으며, 평균 이하의 평가를 기록함.  

---

## 🌟 프로젝트 수행내용 요약

### 데이터
- **셋톱박스 데이터**: 8 columns × 2,708,818 rows  
- **장애 데이터**: 3 columns × 472 rows  

### 주요 활동
1. **데이터 탐색 (EDA)**  
   - 데이터 통합 및 주요 변수 정의  
   - 중복 데이터 및 결측치 처리  

2. **데이터 전처리**  
   - 비정상/정상 레이블 생성  
   - 시계열 특성 반영을 위한 `lag` 변수 추가  

3. **모델 학습**  
   - 분류 모델: XGBoost, Logistic Regression, SVM, Random Forest, CatBoost  
   - 교차검증(OOF) 및 하이퍼파라미터 튜닝  

4. **분류 모델 평가**  
   - **ROC AUC** 및 F1 Score 기반 성능 평가  
   - AUC 기준 **0.81** 이상 성능 달성  

---

## 📊 프로젝트 상세 수행내용

<details>
<summary><b>데이터 탐색</b></summary>

- 데이터 출처: LG Hellovision의 1개월간 셋톱박스 데이터 및 장애 발생 로그  
- 주요 확인사항:  
  - 중복 데이터: 분산 기준으로 처리  
  - 장애 발생 시점 정합성 확인 및 시간 간격 조정  

</details>

<details>
<summary><b>데이터 전처리</b></summary>

- 컬럼 값 통일 (대소문자 변환 등)  
- 결측치 제거 및 레이블링  
- 시계열 데이터 처리: `lag` 변수 추가  

</details>

<details>
<summary><b>모델 학습 및 평가</b></summary>

- **사용 모델**: XGBoost, Logistic Regression, Random Forest, CatBoost 등  
- **성능 평가**:  
  - ROC AUC 기준 최적 모델 선정  
  - 교차검증(OOF) 기법 활용  

</details>

---

## 📌 프로젝트 결론

- XGBoost 모델을 활용하여 **최적의 장애 예측 성능** 확보  
- 시스템 기대 효과:  
  1. **경제적 이익**: 고객 이탈 방지 및 수익 손실 감소  
  2. **기술적 혁신**: 장애 탐지 및 알림 시스템 구축  
  3. **사회적 가치**: 정보 취약계층의 접근성 향상  

