# 원본 기록과 정리 범위

정리일: 2026-10-06. 분석 기간: 2026년 7월.

## 대표 노트북의 출처

| 공개 파일 | 원본 | 반영 범위 |
|---|---|---|
| 01_cabin_eda.ipynb | Titinic Notebook 01.ipynb | 데이터 요약, 복합 Cabin 24행, Deck 분포, Pclass 교차표, 등급 내 비교의 코드·저장 출력 |
| 02_feature_comparison.ipynb | titanic_workflow_part2_github_revised.ipynb | 일곱 feature 조합의 5-fold 비교까지. 뒤의 다른 모델 비교는 이 파일에서 제외 |
| 03_threshold_class_weight.ipynb | 2026-07-21-titanic-threshold-class-weight.ipynb | threshold·class weight 비교와 저장 출력 |
| 04_model_submission.ipynb | 05_titanic-feature-model-submission.ipynb | Fare·Embarked, Gradient Boosting, threshold, 제출 기록 |

01의 본문에는 초기 `titanic-practice.ipynb`의 질문·잠정 판단과 이후 교차표의 관계를 설명했다.
초기 단일 분할 모델 비교는 Age/AgeGroup, Pclass의 수치형/범주형 처리까지 바뀌는 부분이 있어
변수 하나의 효과를 보여 주는 대표 결과로 사용하지 않았다.

## 수정한 내용

- 학습용 안내를 질문·관찰·다음 비교 중심으로 정리했다.
- 데이터 경로를 로컬과 Kaggle에서 찾도록 바꾸고 사용하지 않는 gender_submission 입력을 없앴다.
- 실행 번호를 초기화했다. 원본의 저장된 표·그림은 과거 출력임을 표시하고 보존했다.
- 02와 03·04의 AgeGroup 결측 처리 차이를 명시했다. 과거 결과에 맞추어 처리법을 몰래 통일하지 않았다.
- 03의 "0.45가 가장 균형적"이라는 결론을 지표별 비교로 바꾸었다.
- 04의 "0.50에서 precision도 최대"라는 오류를 수정했다. precision은 0.55에서 더 높다.
- 04의 제출 파일 경로를 정리했다. 제출 파일명에 모델과 threshold가 들어가게 했다.
- 원본 코드와 출력이 일치하지 않는 옛 제출 셀, 과거 CSV와 제출 점수의 연결은 확정 근거로 쓰지 않았다.

## 제출 CSV를 포함하지 않은 이유

| 첨부 파일 | 행 수 | 생존 예측 수 | 판단 |
|---|---:|---:|---|
| submission_logistic_regression45.csv | 418 | 166 | 옛 코드에는 threshold 0.50, 파일명에는 45가 적혀 있음. 저장된 출력만으로 실행 당시 조건 확정 불가 |
| submission_logistic_regression.csv | 418 | 145 | 파일명만으로 생성 모델의 설정과 제출 이력 연결 불가 |
| Titanic ML submission.csv | 418 | 151 | GB 저장 출력의 생존 예측 수와 같지만, 개수가 같다는 이유만으로 동일 파일이라고 확정 불가 |

세 CSV는 모두 PassengerId 418개가 중복 없이 있고 정답 예측 열을 갖춘 제출 형식이다.
그러나 형식 확인은 모델·threshold·Kaggle 점수의 출처 검증과 다르다.
새로 실행한 04의 출력과 대조하기 전에는 대표 결과로 배치하지 않는다.

## 실행 상태

정리본은 원본 데이터로 전체 재실행하지 않았다. 현재 결과 표는 저장된 과거 출력에서 추출했다.
노트북 JSON, Python 코드 문법, 내부 링크, 요약 수치와 원본 표의 대응을 점검했다.
학습 결과 재현을 검증한 것은 아니다. 원본 노트북의 Python 메타데이터는 3.12.13이나,
패키지 버전은 기록되어 있지 않다. 재실행 시 각 노트북 끝에서 환경 버전을 함께 기록한다.

04의 정리 전 버전에도 일부 준비 셀과 제출 생성 셀의 실행 기록이 없었다.
따라서 남아 있는 출력만으로 새 커널에서 처음부터 정상 실행됐다고 주장하지 않는다.
