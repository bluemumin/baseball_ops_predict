# dongguk_university_graduate_report_baseball_OPS_end

- Background 
 <p> 현 시즌 타자 성적 기반, 다음 시즌의 타자들의 OPS(타자의 대표적 타격 지표) 성적 예측 </p>

- Summary
	<p>(1). Data Collection <br/>
		- 현역 선수 연도별 타격 성적 + 개인 정보(나이, 연봉 등) [스탯티즈] </p>
	<p>(2). Data Preprocessing <br/>
		- EDA (변수간 heatmap & 반응변수와의 barplot, boxplot & barplot, histogram & dot graph) <br/>
		- 목적, 파생변수 생성 (다음 시즌 OPS --> 반응변수 / 행운의 안타, 타자 속도 계수, 평균대비 기여율, 공 반발계수, 누적 연차 등)<br/>
		- Reduction & 변수 그룹화 (작은 타석수로 과도 or 과소로 나온 값 절단, 타석 위치 & 포지션 통합)</p>
	<p>(3). Model & Algorithms <br/>
		- RandomForestRegressor --> GridSearch 사용 후 MAE 계산 <br/>
		- xgboost Regressor, Linear Regression --> parameter 미설정 후, 메인 모델링 비교용으로 활용<br/>
		- 이전 2개년 결과 --> 누적 데이터 감소에 따른 영향 확인 및, 연도별 MAE 일정 여부 확인 </p>
	<p>(4). Report <br/>
		- 평균 MAE 0.09로 타자의 OPS 성적을 1할 미만의 값으로 예측하는 모델 구현 완료 (cf 최저/고 범위 0.55~1.1) <br/>
		- 다음 시즌의 타자 성적 예측 목표를 두고 데이터 크롤링, EDA, 모델링까지 전체 process 구현 완료 </p>
	<p>(5). Review <br/>
		- 피드백 : 직전 시즌 기록만이 아닌 더 이전 시즌의 기록, 누적 성적들도 활용 가능 예상함<br/>
		- Futher Research : 이전 기록이 없는 신규 타자 --> 고등,대학 리그의 데이터로 추가 모델 구현<br/>
		&nbsp;+ 스탯티즈 사이트 개편시, 크롤링 코드가 중단이 되므로, 코드 재활용시 개선 작업 필요 </p>

- 이미지 요약 내용
![타자 OPS 예측 요약](https://user-images.githubusercontent.com/53479967/115143904-b9e74200-a084-11eb-8b2f-fbefebcfc2bb.jpg)

cf)
[데이콘 6회 KBO OPS 예측 18위 기록](https://dacon.io/competitions/official/62540/leaderboard/)

[데이콘 6회 KBO OPS 예측 시각화 부문 1등 기록](https://dacon.io/competitions/official/235546/leaderboard/) = 푸른무민

+ 문의 후 이동 가능(private)

[데이콘 6회 KBO OPS 예측 시각화 부문 1등 파이썬 파일](https://github.com/bluemumin/six_dacon_insight)
