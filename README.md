# 프로젝트 주제
- 네이버 쇼핑 인기 상품의 상관관계가 있는 요인 분석
- 상품의 인기라는 척도는 리뷰 수로 설정
- 요인: 가격, 할인, 혜택, 브랜드, 상품 특성, 셀러명 등
  
***
# 사용 데이터
- 키워드 설정 방법
  - 네이버 데이터랩 분야별 상위 키워드
  - 그 중 다양한 가격대와 디자인 등이 떠오를 수 있는 키워드로 임의 5개 설정
- 데이터 수집 방법: Apify '네이버 쇼핑 상품 스크래퍼'
- 수집 항목:
| 카테고리        | 데이터 항목                                                                 | 설명                          |
|-----------------|---------------------------------------------------------------------------|-------------------------------|
| 상품/판매자 정보 | productId, productPageUrl, productImageUrl, sellerName, sellerId, isBrandStore | 상품 및 판매자 식별, 브랜드 여부 |
| 가격/혜택        | originalPrice, discountedPrice, discountRate, shippingFee, hasGift, isSuperPointProduct | 가격, 할인, 배송비, 혜택 정보 |
| 상품 특성       | isNewProduct, isGroupProduct, isFreshProduct, isOverseaProduct, authenticationType | 상품 특성 정보                |
| 리뷰/평점       | totalReviews                                                              | 인기 척도로 사용              |



- 제외되는 항목:
  
***
# 사용 기술

***

# 프로젝트 범위

- 산출물:
- 
