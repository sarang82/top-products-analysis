# 네이버 쇼핑 인기 상품과 상관관계에 대한 분석
### 프로젝트 주제
- **네이버 쇼핑 인기 상품에 가장 유의미한 영향을 끼치는 요소가 무엇인지**를 알아보고자 한다.
- 상품의 인기라는 척도는 리뷰 수로 설정한다. 평점이라는 요소도 크롤링을 통해 수집할 수 있지만,
  리뷰가 곧 구매를 의미하기에 이와 같이 설정했다.

#### 주제 설정 이유
- 인기 상품의 요인이 마케팅 및 sns 노출빈도 등이 아닌 상품 그자체에 있다면 무엇일지,
인기 상품의 패턴이 있을지, 일반적으로 생각하는 가격(할인) 등은 얼마나 유의미한 연관이 있을지 파악하고자 했다.
소비자의 입장에서 상품을 볼 때 어떠한 요소가 중요하고, 어떻게 구매로 이끌 수 있는지 궁금했다.
  
***
### 사용 데이터
- 키워드 설정 방법
  - 네이버 데이터랩을 통해 네이버 쇼핑에서 분야별 상위 키워드를 확인할 수 있다.
  - 그 중 해당 키워드가 특정 브랜드 및 상품을 바로 떠올릴 수 있는 것을 제외하고,
제품명과 브랜드, 디자인 등을 다양하게 떠올릴 수 있는 키워드를 추려
    임의로 설정한 후 상품의 정보를 크롤링한다.
- 독립변수(취소선으로 표시한 항목은 모든 상품이 동일한 값을 가지거나 무의미함)
  - isAd
  - productName
  - productId
  - productPageUrl
  - productImageUrl
  - sellerName
  - sellerPageUrl
  - sellerId
  - isBrandStore
  - originalPrice
  - discountedPrice
  - discountRate
  - shippingFee
  - averageRating
  - stock
  - orderCutoffTime
  - authenticationType
  - naverPaySellerId
  - isNewProduct
  - isGroupProduct
  - ~~isFreshProduct~~
  - isOverseaProduct
  - ~~hasGift~~
  - ~~isSuperPointProduct~~
  - ~~searchKeyword~~
  - ~~crawledAt~~
- 종속변수
  - totalReviews

***
### 사용 기술
- 데이터 수집 : Apify '네이버 쇼핑 상품 스크래퍼' (https://console.apify.com/actors/VgqaheU2MH21OqcZ5/input)
  를 통해 해당 키워드의 **상위 500개의 상품**을 크롤링한다.
- 데이터 전처리 : Python (pandas, numpy)
- 상관관계 분석 : Python

***

### 프로젝트 범위
- 데이터 수집일: 9월 4주차
- 독립변수: 가격, 할인, 혜택, 브랜드, 상품 속성, 노출 키워드
- 상관관계 분석: 리뷰 수에 영향 주는 변수를 탐색하는 것이 목표다.
- 산출물: 각 요소별 리뷰수와의 상관관계. 총 5개의 상품으로 비교한 시각적 자료.
  
***
### GPT-5 모델의 예측
1️⃣ 상품/판매자 식별 관련
- productId: 직접 영향 없음
- productPageUrl:	직접 영향 없음
- productImageUrl: 이미지 품질/노출이 리뷰 수에 간접 영향 가능
- sellerName:	브랜드 인지도에 따라 리뷰 수 증가 가능
- sellerPageUrl: 직접 영향 없음
- sellerId:	직접 영향 없음
- isBrandStore: 리뷰 수 증가 가능

2️⃣ 가격 관련
- originalPrice: 높으면 리뷰 수 감소 가능
- discountedPrice: 높으면 리뷰 수 증가 가능
- discountRate: 높으면 리뷰 수 증가 가능
- shippingFee: 높으면 리뷰 수 증가 가능

3️⃣ 상품 평가 관련
- averageRating: 높으면 리뷰 수 증가 가능
- stock: 영향 없음
- orderCutoffTime: 리뷰 수에 간접 영향 가능

4️⃣ 상품 특징/속성
- authenticationType: True일시 리뷰 수 증가 가능
- isNewProduct: True일시 리뷰 수 감소 가능
- isGroupProduct: True일시 리뷰 수 증가 가능
- isFreshProduct: 특수 패턴 존재
- isOverseaProduct: True일시 리뷰 수 감소 가능
- hasGift: True일시 리뷰 수 증가 가능
- isSuperPointProduct: True일시 리뷰 수 증가 가능
- searchKeyword: True일시 리뷰 수 증가 가능

### GPT가 생각한 리뷰 수에 영향 가능성이 높은 요소
리뷰 수(즉, 판매량)와 가장 연관이 높을 가능성이 있는 한 가지 요소를 고른다면 **averageRating**입니다.
