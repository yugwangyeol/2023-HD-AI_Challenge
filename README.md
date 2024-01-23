# HA AI CHALLENGE

<br/>

## 1. 배경 & 목적
 
- 예선 : 항만 內 선박 대기 시간 예측을 위한 선박 항차 데이터 분석 AI 알고리즘 개발
- 본선 : 센서 데이터를 활용하여 건설 현장 운용 효율화를 위한 작업자의 운전 성향과 숙련도에 영향을 받지 않고 정확한 작업 중량을 예측할 수 있는 모델을 개발

<br/>

## 2. 주최/주관 & 팀원 & 수상

- 주최/주관: HD한국조선해양 AI Center/DACON
- 참가인원 : 1,439명
- 수상 : 에선(10등) 본선(1등)
<br/>
![스크린샷 2024-01-23 195930](https://github.com/yugwangyeol/HD-AI_Challenge/assets/72298825/f8d18849-a5b3-48d9-b0e0-c7ad9867e934)

<br/>

## 3. 프로젝트 기간

- 2023.09. ~ 2023.11. (3개월)

<br/>

## 4. 프로젝트 소개

**[예선]**
 HD-AI-CHALLENGE 예선에서는 선박 데이터를 가지고 항만 내 선박 대기시간 에측을 휘안 AI 알고리즘 개발을 진행하였다.
 다음과 같은 데이터가 주어졌다

<Data info>
- train.csv
Rows : 391,939개
SAMPLE_ID : 학습 샘플의 고유 ID
[수정] 유가 정보 Feature Drop ['DUBAI', 'BRENT', 'WTI', 'BDI_ADJ'] (이전 버전 데이터 사용 시 실격)
CI_HOUR : 대기시간


- test.csv [파일]
Rows : 220,491개
[수정] 유가 정보 Feature Drop ['DUBAI', 'BRENT', 'WTI', 'BDI_ADJ'] (이전 버전 데이터 사용 시 실격)
SAMPLE_ID : 추론 샘플의 고유 ID


- sample_submission.csv [파일] - 제출 양식
Rows : 220,491개
SAMPLE_ID : 추론 샘플의 고유 ID
CI_HOUR : 예측한 대기시간
 


<br/>

## 5. 프로젝트 팀원 및 담당 역할

**[팀원]**

- 학부생 3명

**[담당 역할]**

- 데이터 전처리 및 EDA
- 인사이트 도출
- 모델링&알고리즘 개발
- 발표 자료 제작

<br/>

## 6. 발표 자료

[HD-AI-CHALLENGE 본선 발표 자료](https://drive.google.com/file/d/1LucNwGaHszsWa-NIxNpl8cFeIRABim0f/view)  
