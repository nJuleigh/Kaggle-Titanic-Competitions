# 데이터 준비

원자료: [Kaggle Titanic — Data](https://www.kaggle.com/competitions/titanic/data)

Kaggle에서 제공하는 `train.csv`, `test.csv`를 내려받아 이 폴더에 둡니다.
원자료 CSV는 저장소에 포함하지 않습니다. `gender_submission.csv`는 실행에 필요하지 않습니다.

- train: 891행, `Survived` 정답 포함
- test: 418행, `Survived` 정답 없음
- 결측·파생변수 처리 방법은 각 노트북에 기재했습니다.

노트북은 저장소 루트 또는 `notebooks/`에서 실행합니다.
다른 경로를 사용할 때는 `TITANIC_DATA_DIR` 환경변수로 CSV 폴더를 지정할 수 있습니다.
Kaggle에서는 Titanic 데이터를 연결한 뒤 `/kaggle/input/competitions/titanic` 또는
`/kaggle/input/titanic` 경로를 자동으로 찾습니다.
Google Colab에서는 `train.csv`, `test.csv`를 `/content`에 올리면 자동으로 찾습니다.

2026-10-06 재실행에는 위 Kaggle 페이지에서 받은 `train.csv`, `test.csv`를 그대로 사용했습니다.
