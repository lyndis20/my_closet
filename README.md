# 스몰 프로젝트 - 옷 구매 가이드
 
## 프로젝트 개요
기간: 2023.04.01 ~ 2023.04.26
### 주제


👗 스마트한 옷 구매를 위한 옷장 데이터 분석 및 구매 가이드라인 제작



### 주제 선정 배경

계절이 바뀔 때마다 옷장을 열어보면 옷은 많지만, 막상 입을 옷이 없다! 🤔

매년 옷을 구매하는 데도 왜 이런 현상이 반복되는지에 주목해보았습니다. 
많은 옷들 중에서도 유독 손이 많이 가고 애정이 가는 옷 (구매 성공한 옷)은 어떤 특징이 있고, 어떤 경로로, 어떻게 구매한 옷인지 분석해본다면 앞으로 구입을 할 때 돈을 낭비하거나, 반품하게 될 확률을 줄일 수 있지 않을까? 하는 발상에서 출발하게 되었습니다. 

지금은 개인 구매 경험에 기초한 데이터를 분석했지만, 같은 기준으로 누구나 자신의 옷장의 데이터를 수집하고 분석한다면 각자 자신만의 옷 구매 가이드를 만들 수 있는 서비스로 발전이 가능할 것으로 생각합니다.

### 데이터 분석 TOOL
`Python` `Tableau` `ML`

### 사용할 데이터

#### 수집 방법

- 개인 옷장을 들춰보며, 모든 옷의 구매처, 구매 방법, 특징(사이즈, 색상, 스타일)을 정리한다.
- 각 옷에 대해 3가지 기준으로 **성공 점수**를 매긴다. (1️⃣ 옷에대한 선호도, 2️⃣ 입는 빈도, 3️⃣ 주변 사람의 평가)
- **성공 점수**와 다른 요인간의 상관 관계를 분석하고, 데이터 분석 결과를 시각화한다.

ex) 가설 예시

- 하의는 입어보고 구매한 것이 성공 점수 평균이 높다.
- 상의는 유행하는 디자인이 성공 점수 평균이 낮다.
- 제품의 가격과 성공 점수는 비례한다.

#### 데이터 샘플
<img width="1044" alt="image" src="https://user-images.githubusercontent.com/114198737/230853285-99a4e30c-8a60-489d-a027-7c550be1c05c.png">

2023.04.10 데이터 수집 완료
- v1: 입력 완료한 그대로의 옷장 데이터
- v2:  수기로 보정을 마친 데이터 (띄어쓰기 및 오타 수정)
- v3: 통계 및 머신러닝을 위해, 일부 컬럼 값을 0과 1로 보정한 데이터

데이터셋 정의서 (closet_data_v3.csv 기준)
<img width="653" alt="image" src="https://user-images.githubusercontent.com/114198737/232987977-e97e22a0-0de5-4134-87fb-d4a42fda4361.png">
<img width="621" alt="image" src="https://user-images.githubusercontent.com/114198737/232988412-63101a3e-3c8f-4146-9e6d-ddc89a91be02.png">

### 데이터 살펴보기 (with Tableau) (closet_data_v2 기준)
#### 카테고리 대시보드
![카테고리 대시보드](https://user-images.githubusercontent.com/114198737/234517110-4409d916-e6b8-4b54-8fe5-7e4111532d50.png)
링크: https://public.tableau.com/views/my_closet_category_dashboard/sheet18?:language=ko-KR&:display_count=n&:origin=viz_share_link

<img width="989" alt="태블로1" src="https://user-images.githubusercontent.com/114198737/231694364-d1ac28ea-cb77-418a-8a42-078656babd9a.png">
<img width="984" alt="태블로2" src="https://user-images.githubusercontent.com/114198737/231694394-292b11a6-5a09-4d71-8935-fba0ab350337.png">
<img width="945" alt="태블로3" src="https://user-images.githubusercontent.com/114198737/232975937-313431e2-a287-42aa-ba17-b8136a180ade.png">
<img width="986" alt="태블로4" src="https://user-images.githubusercontent.com/114198737/231694444-13c29615-8002-4c31-831a-da7188ee4cc0.png">
