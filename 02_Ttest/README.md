# 통계 분석 (T-test)
`python`

목차
- [통계 분석](#통계-분석)
  * [데이터의 정규성 검정](#데이터의-정규성-검정)
  * [T-test를 통한 통계적 가설 검정](#t-test를-통한-통계적-가설-검정)
    + [가설1. 가격과 성공 점수는 서로 영향을 준다.](#가설1-가격과-성공-점수는-서로-영향을-준다)
    + [가설2. 하의는 입어보고 구매해야 성공 점수가 높을 것이다.](#가설2-하의는-입어보고-구매해야-성공-점수가-높을-것이다)
    + [가설3. 겉옷은 입어보고 구매해야 성공 점수가 높을 것이다.](#가설3-겉옷은-입어보고-구매해야-성공-점수가-높을-것이다)
    + [가설4. 유행하는 디자인의 상의는 성공 점수가 낮을 것이다.](#가설4-유행하는-디자인의-상의는-성공-점수가-낮을-것이다)
    + [가설5. 유행하는 디자인의 원피스는 성공 점수가 낮을 것이다.](#가설5-유행하는-디자인의-원피스는-성공-점수가-낮을-것이다)
    + [가설6. 브랜드가 있는 겉옷은 성공 점수가 높을 것이다.](#가설6-브랜드가-있는-겉옷은-성공-점수가-높을-것이다)
    + [가설7. 구매처에 따라 성공점수가 차이날 것이다.](#가설7-구매처에-따라-성공점수가-차이날-것이다)
  * [결론](#결론)
    + [추가로 확인할 내용](#추가로-확인할-내용)


# 통계 분석

상관계수 및 **t-검정**을 통해 **두 집단 간의 평균의 차이가 유의미한 지** 검증한다.

## 데이터의 정규성 검정

직접 수집한 개인의 스몰 데이터이기 때문에  `성공점수`가 정규 분포를 따르는 지 검정하였다.

### 시각화를 통한 정규분포 확인

QQ-plot (probplot)
![image](https://user-images.githubusercontent.com/114198737/235687377-5e6bd1a2-6a64-4bee-aa8c-1df3e9507ea6.png)
성공점수 히스토그램
![image](https://user-images.githubusercontent.com/114198737/235687414-e5004d4e-cd1e-4a35-bffb-52a48ada1493.png)

데이터 행이 150개로 한정적인 것을 감았했을때 어느 정도 정규 분포 형태를 띄고 있고, 자료가 중심에 몰려 있음을 확인할 수 있다.

### 정규성 통계적 가설 검정

✅ 귀무가설: 데이터가 정규 분포를 따른다.

p-value가 유의수준(0.05)이상인 경우 데이터는 귀무가설을 기각할 수 없어 정규 분포를 따른다고 볼 수 있다.

1. Kolmogorov-Smirnov Test
![image](https://user-images.githubusercontent.com/114198737/235687502-f58174af-5c35-4ba2-ae40-7fd06fff68e7.png)
→ KS테스트 결과, p-value가 0.052로, 귀무가설을 기각할 수 없어, 데이터가 정규분포를 따른다고 볼 수 있다. 

1. Shapiro-Wilk Test
![image](https://user-images.githubusercontent.com/114198737/235687565-c67dfff4-3cff-4191-b408-2e3f760d180a.png)
→ Shapiro테스트 결과, p-value가 0.0038로, 귀무가설을 기각하여, 데이터가 정규분포를 따른다고 볼 수 없다.

→ **즉, 일부 테스트(KS테스트)에 따라 정규 분포가 충족된다고 볼 수 있기 때문에 하단 통계적 가설 검정을 신뢰할 수 있는 것으로 판단하였다.** 
다만, 데이터 표본 수의 한계와. 일부 테스트의 정규성 불충족으로 인해 추후 데이터를 추가하여 검증하는 것이 필요할 것으로 판단된다.

## T-test를 통한 통계적 가설 검정

### 가설1. 가격과 성공 점수는 서로 영향을 준다.
![image](https://user-images.githubusercontent.com/114198737/235687743-74b950cb-1037-46a9-ab98-2660ba091f4d.png)

표본 상관 계수 r값은 -0.002021로, 상관 관계가 전혀 없다.

📌 **가격과 성공점수는 상관관계가 없다.**


### 가설2. 하의는 입어보고 구매해야 성공 점수가 높을 것이다.

![image](https://user-images.githubusercontent.com/114198737/235687785-8eb047e5-30c0-4e1a-97c4-dbc4a8c0a70c.png)

집단1. 하의 중에서 구매전 착용 여부가 True인 경우 성공점수의 평균

집단2. 하의 중에서 구매전 착용 여부가 False인 경우 성공점수의 평균

p-value가 유의수준인 0.05보다 크기 때문에 두 집단은 다르지 않다.


📌 **하의는 입어보고 구매하든, 입어보지 않고 구매하든 성공 점수의 차이는 유의미하지 않다.**


### 가설3. 겉옷은 입어보고 구매해야 성공 점수가 높을 것이다.

![image](https://user-images.githubusercontent.com/114198737/235687822-09f472a4-d83a-4dde-8ab9-4c53f5dab832.png)

집단1. 겉옷 중에서 구매전 착용 여부가 True인 경우 성공점수의 평균

집단2. 겉옷 중에서 구매전 착용 여부가 False인 경우 성공점수의 평균

p-value가 유의수준인 0.05보다 크기 때문에 두 집단은 다르지 않다.

📌 **겉옷은 입어보고 구매하든, 입어보지 않고 구매하든 성공 점수의 차이는 유의미하지 않다.**


### 가설4. 유행하는 디자인의 상의는 성공 점수가 낮을 것이다.

![image](https://user-images.githubusercontent.com/114198737/235687882-68c4ec93-0a6f-45e6-be88-3cc09d74d005.png)

집단1. 상의 중에서 유행 여부가 True인 경우 성공점수의 평균

집단2. 상의 중에서 유행 여부가 False인 경우 성공점수의 평균

p-value가 유의수준인 0.05보다 크기 때문에 두 집단은 다르지 않다.


📌 상의는 **유행하는 디자인이든, 아니든 성공 점수의 차이는 유의미하지 않다.**


### 가설5. 유행하는 디자인의 원피스는 성공 점수가 낮을 것이다.

![image](https://user-images.githubusercontent.com/114198737/235687944-59e9038b-2439-47a5-9816-82cda314942b.png)

집단1. 원피스 중에서 유행 여부가 True인 경우 성공점수의 평균

집단2. 원피스 중에서 유행 여부가 False인 경우 성공점수의 평균

p-value가 유의수준인 0.05보다 크기 때문에 두 집단은 다르지 않다.


📌 원피스는 **유행하는 디자인이든, 아니든 성공 점수의 차이는 유의미하지 않다.**


### 가설6. 브랜드가 있는 겉옷은 성공 점수가 높을 것이다.

![image](https://user-images.githubusercontent.com/114198737/235687982-4286a81a-20d3-44c5-b1f1-fa58afd48fb1.png)

집단1. 겉옷 중에서 브랜드 여부가 True인 경우 성공점수의 평균

집단2. 겉옷 중에서 브랜드 여부가 False인 경우 성공점수의 평균

p-value가 유의수준인 0.05보다 크기 때문에 두 집단은 다르지 않다.

📌 겉옷은 **브랜드가 있든, 없든 성공 점수의 차이는 유의미하지 않다.**


### 가설7. 구매처에 따라 성공점수가 차이날 것이다.

![image](https://user-images.githubusercontent.com/114198737/235688041-27cfdb88-e318-4b35-af74-521c42b3bec1.png)

집단1. 온라인 구매 의류의 성공점수의 평균

집단2. 오프라인 구매 의류의 성공점수의 평균

p-value가 유의수준인 0.05보다 크기 때문에 두 집단은 다르지 않다.

📌 **구매처 구분은 성공점수 평균에 있어 유의미하지 않다.**


## 결론

**두 집단의 평균 성공 점수 차이가 유의미한 결과는 얻지 못하였다.**

데이터 표본 개수가 150개로, 한정적이었기 때문이라고 생각된다.

이후 데이터를 추가적으로 수집해서, 유의미한 결과가 나오는 지 계속해서 검증해볼 것이다.

### 추가로 확인할 내용

Bivariate Distribution Plot을 통해 시각화 해본 차이가 통계적으로 유의미한 차이인지 검증한다.