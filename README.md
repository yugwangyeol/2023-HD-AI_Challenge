# HD-AI-CHALLENGE

<br/>

## 1. 배경 & 목적
 
- 예선 : 항만 內 선박 대기 시간 예측을 위한 선박 항차 데이터 분석 AI 알고리즘 개발
- 본선 : 센서 데이터를 활용하여 건설 현장 운용 효율화를 위한 작업자의 운전 성향과 숙련도에 영향을 받지 않고 정확한 작업 중량을 예측할 수 있는 모델을 개발

<br/>

## 2. 주최/주관 & 성과

- 주최/주관: HD한국조선해양 AI Center/DACON
- 참가인원 : 1,439명
- 성과 : 에선(10등) 본선(1등,대상 수상)
<br/>

![170000790063290](https://github.com/yugwangyeol/HD-AI_Challenge/assets/72298825/6e58aaa6-6a8a-4ede-8dde-a1828ef08482)

<br/>

## 3. 프로젝트 기간

- 예선 : 2023년 9월 25일 ~ 10월 30일
- 본선 문제 모델링 진행 : 2023년 11월 06일 ~ 11월 09일
- 오프라인 본선 진행 : 2023년 11월 10일
- 최종 결과 발표 : 2023년 11월 15일
- 시상식 : 2023년 11월 30일 (HD 현대 포럼)

<br/>

## 4. 프로젝트 소개

**[예선]**  
<br/>
&nbsp;&nbsp;&nbsp;&nbsp; HD-AI-CHALLENGE 예선에서는 **선박 데이터를 가지고 항만 내 선박 대기시간 에측을 위 AI 알고리즘 개발**을 진행하였다. 데이터는 약 39만 개의 train data와 약 22만 개의 test data가 주어졌다. 예선 대회 도중 특이한 점은 대회 마감 13일 전에 대회 데이터가 수정되었다. 1차적으로 주어진 데이터에서는 유가 정보인 ['DUBAI', 'BRENT', 'WTI', 'BDI_ADJ']와 날짜 정보만으로 항만 대기 시간을 구할 수 있었다. 이는 **유가 정보가 target의 정보를 포함하고 있어서 Data Leakage**로 데이터 수정되었다.  

&nbsp;&nbsp;&nbsp;&nbsp; 유가 정보를 제외한 데이터로 13일 동안 대회를 진행하였다. 남은 데이터로 target과 관련된 EDA를 진행하였고, **날씨 데이터가 target과 유사한 패턴**을 보임을 확인하였다. 이후 항만 데이터, 날짜 데이터, 날씨 데이터를 바탕으로 Feature 생성을 진행하였고, 짧 시간 내에 성능을 대기 위해 AutoML모델인 Autogluon을 사용하여 기본적인 target 값을 구다. 이후 EDA에서 파악한 패턴을 바탕으로 **후처리 알고리즘을 생성하여 target을 새롭게 생성**하였다. 알고리즘 적용 여부에 따라 성능이 크게 차이 남을 보였다. 해당 후처리 방법론을 통해 예선을 **[Public score 9th(0.6%) 32.05994 | Private score 10th(0.6%) 32.45594]**으로 통과하였다.  

**[본선]**
<br/>

![스크린샷 2024-01-23 203817](https://github.com/yugwangyeol/HD-AI_Challenge/assets/72298825/f8ae4b47-d6c4-46ac-9c74-5961eda52f3c)

&nbsp;&nbsp;&nbsp;&nbsp; 본선에서는 **4개의 sensor 데이터와 3개의 sinal 데이터**를 가지고, 사용자의 숙련도에 상관없이 작업 중량을 예측하는 AI 알고리즘을 개발하였다. 먼저 4개의 sensor 데이터와 3개의 signal 데이터를 EDA 하여 해당 데이터 값이 어떤 건설 기계에서 생성된 데이터 인지 파악하였다. 위 그림과 같은 EDA를 통해 해당 데이터가 **포크레인 데이터에서 생성**됨을 확인하였다. 이를 바탕으로 먼저 LSTM, CNN-LSTm과 같은 시계열 모델들을 시도하였다. 그러나 시계열 모델들이 해당 데이터의 특성과 맞지 않아 ML 기반의 모델을 시도하였다. 시계열적 특성과 운전자의 숙련도에 영향받지 않도록 **Widow를 사용하여 데이터를 변형**하였다. 해당 데이터를 가지고 3일 안에 많은 실험을 하기 위해 예선에서 사용한 Autogluon을 사용하여 성능을 향상시켰다. 해당 방법론 등을 통해 **본선 1등, 발표 1등으로 최종 대상**을 수상하였다. 

<br/>

## 5-1. 예선 Process

### ch.1 EDA  

- 나라별, 항구별, 배의 타입별 등등의 특성 확인
- 각 배의 카테고리컬한 피처들의 조합의 통계값들 확인
- **기상정보에 대한 Target값 로직 파악**

---

### ch.2 Feature Engineering  

- 시간 feature들은 inherently cyclical 하다는 특징을 활용하기 위해 sin/cos 변환
- 특정 피처들의 target 값의 평균으로 파생 변수 생성
- Clustering

---

### ch.3 Modeling

- Autogluon
- 기상정보에 따른 후처

<br/>

## 5-2. 본선 Process

### ch.1 EDA  

- Signal, Sensor 관계 파악
- **Signal, Sensor를 통한 건설 기계 추정**

---

### ch.2 Feature Engineering  

- Fourier transform 등 다양한 피쳐 변환
- 부하 토크, 동적 반응 피쳐 생성
- ML에 맞게 Widow를 통한 피쳐 변환

---

### ch.3 Modeling

- LSTM
- CNN_LSTM
- Autogulon

<br/>

## 6. 프로젝트 팀원 및 담당 역할

**[팀원]**

- 학부생 3명

**[담당 역할]**

- 데이터 전처리 및 EDA
- 인사이트 도출
- 모델링&알고리즘 개발
- 발표 자료 제작

<br/>

## 6. 발표 자료&참고 자료

[HD-AI-CHALLENGE DACON](https://dacon.io/competitions/official/236158/overview/description)  
[HD AI Challenge 본선 발표 자료](https://github.com/yugwangyeol/HD-AI_Challenge/blob/main/Presentation/%5BHD%5D%ED%98%84%EB%8C%80_%EC%B5%9C%EC%A2%85.pdf)
