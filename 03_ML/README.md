# 머신 러닝
`scikit-learn`

# 머신러닝: 분류 모델

머신러닝 모델을 활용하여 성공 여부를 예측하는 분류 모델을 만든다.

기존 150개의 데이터셋을 120:30으로 나누어서 자체 검증해본다.

### 분류 모델의 Label값

성공 여부 (성공점수가 3점을 초과하면 성공:1, 3점 이하면 실패:0로 본다.)

기존 150개 데이터셋의 성공 여부 분포

성공여부 예측 **정확도(accuracy)**를 평가 지표로 설정했다.

머신러닝 모델 **베이스라인 점수: 0.53**
성공 여부를 모두 1로 예측했을때, 정확성은 0.53이기 때문이다.
![image](https://user-images.githubusercontent.com/114198737/235691310-b9a6cd35-0e92-4f8b-bc55-2f3f8c887625.png)

### 데이터 전처리

- 피처 선택, 원핫인코딩
![image](https://user-images.githubusercontent.com/114198737/235690786-ff8ff87a-be97-46d2-95b8-c7c92ca88f38.png)

v3 데이터는 일부 피처가 0과 1로 라벨인코딩이 되어 있는 상태이다.
여기에 해당 하지 않는 `구매 목적`, `카테고리`,`색상그룹` 피처를 원핫인코딩하였다.

![image](https://user-images.githubusercontent.com/114198737/235690839-12e3d9f6-01b3-4e08-bf6e-ce33a0998e57.png)

### 분류 모델 실행 결과

모델1. 결정트리모델(DecisionTreeClassifier)

`0.733`

![image](https://user-images.githubusercontent.com/114198737/235690890-df914fbd-ec21-45d5-a299-750d570eccc6.png)

모델2. 랜덤포레스트 모델 (RandomForestClassifier) ⭐️

`0.8333`

![image](https://user-images.githubusercontent.com/114198737/235690926-78f6c79a-45be-4e30-9659-e227d761e71c.png)

모델3. CatBoost 모델

`0.6333`

![image](https://user-images.githubusercontent.com/114198737/235690960-8780b2ae-b365-43fd-b90b-35c9ab56cc21.png)

⭐️ Best Score 모델의 피처 중요도
![image](https://user-images.githubusercontent.com/114198737/235691008-a49865b1-7ac8-456a-952b-dfb6c9c428ca.png)
![image](https://user-images.githubusercontent.com/114198737/235691078-d13c69c4-1cf9-4bfd-bdde-f81e2b54bd37.png)

최근 1년 내 착용여부, 구매목적_일상, 가격, 구매목적_행사, 카테고리_상의, 색상그룹_블랙계열 순으로 피처중요도가 높았음을 알 수 있으며, 
그중에서도 `최근 1년 내 착용여부`의 중요도가 매우 높았음을 확인할 수 있다.

### 추가 개선해볼 점

1. 하이퍼 파라메터 튜닝 (랜덤서치, 그리드 서치)
2. ****XGBoost, LightGBM 모델 추가****
3. 딥러닝 모델 적용 시도
