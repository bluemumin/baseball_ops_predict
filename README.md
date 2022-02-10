## 1. 이전 성적 기준, 다음 시즌 타자 OPS 예측 모델 구현

  - Member : 김경록
  - Status : Complete
  - Tag : Competition, Toy Project
  - 사용언어 / 핵심 라이브러리 :  python / Pandas, matplotlib, seaborn, plotly, BeautifulSoup, sklearn

## 2. Why

프로야구에는 정규 시즌도 중요하지만, 스토브 리그라는 선수들을 영입/방출 하면서 팀을 재정비 하는 프리 시즌이 존재한다.

크게 선수들을 투수/타자로 나눌수 있고 이번 프로젝트에서는 타자의 지난 시즌 성적들로 현 시즌 타격 능력(OPS)를 예측 해보려고 한다.

현재는 정규 시즌을 뛴 선수들만 가지고 모델을 만들지만, 향후에는 미출전 선수, 고등/대학 리그 선수들로 확대하여

KBO의 팀들이 타자의 다음시즌 타격 능력을 미리 확인할 수 있는 모델로 만들어보고자 한다.

## 3. Data

[웹 페이지(사이트 명 : 스탯티즈) 크롤링] --> 현역 선수 연도별 타격 성적 + 개인 정보(나이, 연봉 등)

## 4. 분석 방법

 (a). Data Preprocessing
 
	- EDA : 변수간 heatmap & 반응변수와의 barplot, boxplot & barplot, histogram & dot graph
	
	- 목적, 파생변수 생성 : 다음 시즌 OPS --> 반응변수 / 행운의 안타, 타자 속도 계수, 평균대비 기여율, 공 반발계수, 누적 연차 등
	
	- Data Reduction & 변수 그룹화 : 작은 타석수로 과도 or 과소로 나온 값 절단, 타석 위치 & 포지션 통합
	
 (b). Model & Algorithms
 
	- RandomForestRegressor --> GridSearch 사용 후 MAE 계산
	
	- xgboost Regressor, Linear Regression --> parameter 미설정 후, 메인 모델링 비교용으로 활용
	
	- 이전 2개년 결과 --> 누적 데이터 감소에 따른 영향 확인 및, 연도별 MAE 일정 여부 확인
	
 (c). Report & Review
 
	- 최종 등수 : 모델링 18/93위 기록 / 시각화 1등 기록
	
	- MAE 0.09로 타자의 OPS 성적을 1할 미만으로 예측하는 모델 구현 (cf 예측변수 평균 범위 0.55 ~ 1.1)
	
	- 긍정적 사항 : 데이터 크롤링, EDA, 모델링까지 전체 process 단독 구현
	
	- 피드백 : 직전 시즌 기록만이 아닌 더 이전 시즌의 기록, 누적 성적들도 활용 가능 했음
	
	- Futher Research : 이전 기록이 없는 신규 타자 --> 고등,대학 리그의 데이터 보유시, 추가 모델 구현 가능

## 5. 이미지 요약 내용

![타자 OPS 예측 요약](https://user-images.githubusercontent.com/53479967/115143904-b9e74200-a084-11eb-8b2f-fbefebcfc2bb.jpg)

### cf) 대회 기록 링크

[데이콘 6회 KBO OPS 예측 18위 기록](https://dacon.io/competitions/official/62540/leaderboard/)

[데이콘 6회 KBO OPS 예측 시각화 부문 1등 기록](https://dacon.io/competitions/official/235546/leaderboard/) = 푸른무민

+ 문의 후 이동 가능(private)

[데이콘 6회 KBO OPS 예측 시각화 부문 1등 파이썬 파일](https://github.com/bluemumin/six_dacon_insight)
