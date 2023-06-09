# [my_closet] 나의 옷장 스몰 데이터 분석 프로젝트

## 프로젝트 개요

### 주제


👗 **성공적인 옷 구매를 위한 개인 옷장 스몰 데이터 수집 및 분석**


### 주제 선정 배경
<img width="40%" src="https://user-images.githubusercontent.com/114198737/235662873-79185329-738b-41aa-b333-a95d3a91011c.png"/>

계절이 바뀔 때마다 옷장을 열어보면 옷은 많지만, 막상 입을 옷이 없다! 🤔

많은 옷들 중에서도 **유독 손이 많이 가고 애정이 가는 옷 (구매 성공한 옷)**은 어떤 특징이 있고, 어떤 경로로, 어떻게 구매한 옷인지 분석해본다면 앞으로 구입을 할 때 돈을 낭비하거나, 반품하게 될 확률을 줄일 수 있지 않을까? 하는 발상에서 출발하게 되었습니다.

수집한 옷장 데이터를 바탕으로 **1) 데이터시각화 2) 통계적 가설검정 3) 머신러닝 모델 제작**을 수행했습니다.

### 진행 기간

2023.04.01 ~ 2023.04.28

### 데이터 분석 TOOL

`Python` `Tableau` `ML`

## 사용한 데이터

직접 기록한 개인의 옷장 데이터 (small data)

### 수집 방법

- 개인 옷장을 들춰보며, 모든 옷의 구매처, 구매 방법, 특징(사이즈, 색상, 유행여부 등)을 기록한다.
- 각 옷에 대해 3가지 기준의 점수를 평균 내어 **성공 점수**를 매긴다. (1️⃣ 옷에대한 선호도, 2️⃣ 입는 빈도, 3️⃣ 주변 사람의 평가)
- **성공점수 계산 기준**

<img src="https://user-images.githubusercontent.com/114198737/235663134-aa135c75-7cf2-4fc3-a44c-4e378ae21359.png"/>

ex) 가설 예시

- 하의는 입어보고 구매한 것이 성공 점수 평균이 높다.
- 상의는 유행하는 디자인이 성공 점수 평균이 낮다.
- 제품의 가격과 성공 점수는 비례한다.

### 데이터 샘플

2023.04.10 데이터 수집 완료 (150건)


<img src="https://user-images.githubusercontent.com/114198737/235662940-20fb67ce-5965-49a5-bd40-053d1f249416.png"/>
데이터 v1

### 데이터 버전

- v1: 입력 완료한 그대로의 옷장 데이터
- v2:  수기로 보정을 마친 데이터 (띄어쓰기 및 오타 수정)
- v3: 통계 및 머신러닝을 위해, 일부 컬럼 값을 0과 1로 보정한 데이터

<img src="https://user-images.githubusercontent.com/114198737/235663084-995eb65d-db6c-45ea-8d87-cde22af0288f.png"/>
데이터 v3

### 데이터셋 정의서 (closet_data_v3.csv 기준)

<img src="https://user-images.githubusercontent.com/114198737/235663111-30b2457c-3c70-41ea-a923-2b8cd5f87635.png"/>

## 카테고리 대시보드 확인하기 (태블로)

### [📊 대시보드 링크) 웹에서 확인하기](https://public.tableau.com/views/my_closet_category_dashboard/sheet18?:language=ko-KR&:display_count=n&:origin=viz_share_link)

<img src="https://user-images.githubusercontent.com/114198737/235662841-b5e39234-efc1-4828-b410-9535f23c3139.png"/>

## 분석결과 요약

**시각화 결과 요약**
전체 결과 링크: https://github.com/lyndis20/my_closet/tree/main/01_EDA

**가격**

- 가격과 성공 점수는 상관이 없다. 따라서 굳이 비싼 옷을 고를 필요가 없지만, 16만원을 초과하는 경우에는 평균 성공점수가 가장 높다

**구매 목적**

- 생존, 여행 목적의 옷을 구매할 때는 신중하게 구매해야 한다
- 출근 목적의 경우 오프라인에 구매하는 것이 온라인으로 구매하는 것에 비해 평균 성공점수가 높다

**브랜드 여부**

- 브랜드 여부에 따른 성공점수의 차이는 크지 않기 때문에 보세를 사는 것이 현명한 소비이다.
- SPA 제품을 구매하는 경우 10만원을 초과하지 않는 가격대를 사는 것이 현명하다.
- 겉옷의 경우 SPA 제품을 구매했을때 성공점수가 0.5점 이상 낮은 것을 확인할 수 있다.

**카테고리**

- 원피스의 경우 보세 제품을 구매했을때 성공점수가 0.5점이상 낮은 것을 확인할 수 있다.
- 원피스의 경우 유행하는 디자인의 평균 성공점수가 1.5점 이상 크게 낮은 것을 확인할 수 있다.

**계절**

- 여름 제품은 오프라인에서 브랜드 제품을 구매하는 것이 평균 성공점수가 높다

**통계적 가설 검정 결과 요약**
분석 결과 링크: https://github.com/lyndis20/my_closet/tree/main/02_Ttest

- 하의와 겉옷은 입어보고 구매하든, 입어보지 않고 구매하든 성공 점수의 차이는 유의미하지 않다.
- 상의와 원피스는 유행하는 디자인이든, 아니든 성공 점수의 차이는 유의미하지 않다.
- 겉옷은 브랜드가 있든, 없든 성공 점수의 차이는 유의미하지 않다.
- 구매처 구분은 성공점수 평균에 있어 유의미하지 않다.

→ 추후 표본의 개수를 늘려서 재분석이 필요하다.

**머신러닝 요약**
모델 결과 링크: https://github.com/lyndis20/my_closet/tree/main/03_ML

- 분류 모델(RandomForestClassifier) accuracy score `0.833`
- 가장 중요도가 높았던 피처는 `최근 1년 내 착용 여부` 이다.

✅ 더 자세한 결과는 분석 결과별 링크에서 확인해주세요


## 프로젝트 **회고 및 개선할점**

### Keep

- 공부했던 다양한 데이터분석 기법을 **스스로 직면하고 있는 현실적인 문제**를 해결하는 데 활용할 수 있어 의미있었다.
- 데이터를 직접 수집할때 DB의 컬럼과 컬럼에 들어갈 값을 설계하는 작업이 중요하고, 분석 결과에도 높은 영향을 미칠 수 있다는 점을 배울 수 있었다.
- 태블로로 대시보드를 구성해보면서 어떤 데이터를 어떤 도표로 보여주는 것이 효과적인지 수없이 고민하고 적용해볼 수 있었다.

### Problem

- 데이터 표본의 개수가 적어 의미있는 분석 결과를 얻지 못해 아쉬웠다
- T-test외의 범주형 데이터를 좀 더 제대로 검증할 수 있는 다양한 통계 분석 기법을 공부하고 적용해보고 싶다.

### Try

- 앞으로도 지속적으로 옷장 데이터를 수집하여 검증을 계속 시도해 볼 것이다.
- 기회가 된다면 기업 데이터로 특정 연령대와 성별의 패션 트렌드를 분석하는 것에 접목시켜보고 싶다.
- 테이블을 여러개로 쪼개서 수집하고, SQL을 통해 불러와서 더욱 자세한 브랜드별, 판매 쇼핑몰에 따른 분석을 시도해보고 싶다.

## 참고자료

- [2017 데이터야 놀자 - 최규민](https://www.slideshare.net/ssuser2fe594/2107-80754131)
