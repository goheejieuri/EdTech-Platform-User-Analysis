# 구독 기반 교육 콘텐츠 서비스 회원 행동 분석  
**Subscription-based Education Service User Behavior Analysis**

## 📌 Introduction  
본 프로젝트는 **구독 기반 교육 콘텐츠 서비스의 구독 회원 확대 전략**을 수립하기 위해 회원 행동 데이터를 분석하는 것을 목표로 한다.  
특히 *첫 구독 전환*과 *재구독 행동*, *고객 세분화*를 중심으로 데이터 기반 인사이트를 도출하였다.

### 🎯 목적 및 문제 정의
- **첫 구독 전환 분석**: 회원가입 → 첫 결제까지의 행동 여정 파악  
- **재구독 분석**: 구독 경험 회원의 재구독 패턴 분석  
- **고객 세분화(RFM)**: 그룹별 특성 파악 및 전략적 타겟팅

---

## 📊 현황 분석 요약
- **전체 회원 대비 구독 비율:** 약 11%  
- **재구독율:** 약 40%
<img width="809" height="363" alt="image" src="https://github.com/user-attachments/assets/25ee50c1-e584-4f95-9a8e-2dc4d2580d17" />


---

## 🧹 Data Processing

### 🛠 전처리 요약
1. 무료 체험: user_id 기준 첫 event만 사용  
2. 결제: 3개 테이블 병합 → 중복 제거 → 28일 미만 결제 제거  
3. 콘텐츠: 시작/종료 중복 제거, 콘텐츠 완료 여부 매핑  

---

## 📐 Analysis Methodology

### 1) 퍼널 분석  
- 회원가입 → 레슨 시작 → 결제 페이지 진입 → 첫 결제 완료  
- 단계별 전환율 계산

### 2) 통계적 검정  
- 카이제곱 검정: 무료 체험 효과, 완료율-재구독 관계  
- Mann-Whitney U test: 재구독 여부에 따른 콘텐츠 수강량 비교  

### 3) RFM 분석  
- **Recency**: 최근 콘텐츠 시작일  
- **Frequency**: 콘텐츠 시작 횟수  
- **Monetary**: 실제 지불 금액  

---

# 📈 Data Analysis

## 🔹 첫 구독 전환 퍼널 분석
**결제 페이지 → 첫 결제 완료 전환율: 약 24% (최저 단계)**

<img width="537" height="265" alt="image" src="https://github.com/user-attachments/assets/ae382915-c9d6-4182-9ed7-2db78813c17c" />

### A/B테스트 제안
- 목표 : 결제 수단 다양화를 통한 첫 구독 전환율 개선
- 방법 : 결제 수단에 카카오 페이와 페이코 결제 추가
- 예상 효과 : 첫 구독 전환율 24% -> 26.93%로 상승

<img width="926" height="426" alt="image" src="https://github.com/user-attachments/assets/fe5f963a-873d-4ec8-ad2a-dec80b4a036c" />

---

## 🔹 무료 체험 효과성 분석
- 무료 체험 그룹 전환율: **42.4%**  
- 비체험 그룹 전환율: **15.0%**  
- 카이제곱 검정 결과: p-value < 0.05 → **유의미한 효과 있음**

콘텐츠 페이지 방문 횟수 증가 시 무료 체험 신청 비율도 상승  
→ **4회 방문이 무료 체험 유도 최적 지점**

<img width="609" height="266" alt="image" src="https://github.com/user-attachments/assets/2146825b-c2e3-443c-9b50-b4380b65d304" />


---

## 🔹 재구독 분석
- **1회 구독:** 평균 수강 3.72개, 완료율 25%  
- **2회 이상 구독:** 평균 수강 5.90개, 완료율 36.1%  

난이도별 특징:  
- 재구독 그룹은 **중급 이상 콘텐츠 비중 증가**

<img width="588" height="244" alt="image" src="https://github.com/user-attachments/assets/d59cccd6-702e-461b-afda-894af16615ba" />


- 고급 콘텐츠는 레슨 수가 많아 완료율 저해 가능성
  
<img width="572" height="230" alt="image" src="https://github.com/user-attachments/assets/9c795a5d-ff06-4816-a80f-2e43e836d598" />


- Beginner난이도는 타 난이도에 비해 콘텐츠의 절대적 수가 부족하므로 콘텐츠의 다양화가 요구된다.
- Advanced난이도는 콘텐츠 당 레슨 수가 타 난이도에 비해 많아 학습 부담이 될 수 있으므로 레슨 수 조절이 필요하다.


  

---

## 🔹 RFM 세그먼트 분석

<img width="941" height="208" alt="image" src="https://github.com/user-attachments/assets/c836320f-174d-4858-b81c-3bfd87aad04e" />

- 충성고객 : 콘텐츠 시작 개수가 가장 많고, 실 지불 금액도 높다.
- 단기 성취형 고객 : 비교적 최근에 콘텐츠 페이지를 방문하였고, 콘텐츠 시작 개수도 두번째로 많지만 실 지불금액은 낮다.
- 이탈 위험 고객 : 실 지불 금액은 단기 성취형 고객보다 많지만 비교적 방문 경과일이 길고, 콘텐츠 시작 개수도 적다.

### 세그먼트별 마케팅 방안

<img width="925" height="338" alt="image" src="https://github.com/user-attachments/assets/7eaf2762-0877-4480-9e46-e3a09c79fd72" />

---

# 🎯 Conclusion & Strategy

### 🔹 첫 구독 전환 최적화
- 결제 페이지 UI/UX 개선 필요   
- 콘텐츠 페이지 **4회 방문** 시점 무료 체험 유도

### 🔹 재구독 촉진 전략
- 초급 콘텐츠 완강률 개선  
- 고급 콘텐츠 레슨 수 재조정  
- 세그먼트별 개인화 전략 활용 (RFM 기반)


---

# 🚀 Recommendations

## ✔️ 장기적 과제
- 인구통계학적 정보 수집  
- 콘텐츠 영역 세분화  
- 결제 패턴 데이터 확보  

---

# 🏁 Summary
본 프로젝트는 구독 기반 서비스의 **구독 확대 전략**을 체계적으로 도출하기 위해  
퍼널 분석, 통계 검정, RFM 분석을 수행하였으며 **실행 가능한 실무 중심 전략**을 제시했다.
