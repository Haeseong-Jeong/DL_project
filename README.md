# DL_project
딥러닝 프로젝트

## - 개요
배달 어플에서 리뷰 사진을 올리면 적립금을 부여한다. 하지만 연관없는 사진을 올려도 적립금을 받는 문제가 있다.

## - 목표
1. 이에 음식사진이 아닌 (연관없는사진) 사진들을 올린 리뷰에는 적립금을 주지 않는 기능을 딥러닝을 활용해 구현
2. 1번이 구현 됐을 경우 음식 카테고리에도 맞게 올릴 경우에만 적립금을 부여 ( ex> 치킨집에 족발사진 올리면 적립금 x)

## - Data_test
먼저 짜장면, 짬뽕, 탕수육으로 test 진행.

1. 구글 이미지 사이트에서 짜장면, 짬뽕, 탕수육 사진을 300개 크롤링.
2. 각 음식 사진 라벨링, (100개 이상이 되도록)
3. 요기요에서 중국집 업체를 하나 선정해서 사진리뷰자 100명 크롤링.
4. Yolo 예측에서 나온 이미지 라벨이 짜장면, 짬뽕, 탕수육 중 있다면 1, 없다면 0 으로 예측.

## - Data_total
15개의 음식 클래스를 모두 진행.

1. 각 음식 사진 300개씩 크롤링.
2. 각 음식 사진 라벨링, (100개 이상이 되도록)
3. 요기요에서 해당메뉴를 파는 음식점을 골라서 사진리뷰자 100명 크롤링.

## - result 및 한계점

- 예측시 음식점에서 하나의 음식만 판다고 가정하면 정확도가 매우 낮은 음식이 나옴.
  - 요기요 카테고리 별로 음식점의 구분이 애매모호함.
  - 치킨집이지만 떡볶이, 피자 등등 같이 파는 경우 처럼 이 모든 메뉴를 고려해야 정확한 정확도가 나옴.

- 중국집(짜장면/짬뽕/탕수육), 족발/보쌈 처럼 같이 묶어 업체 사진리뷰를 예측해야 정확도가 상승.

- 음식점마다 메뉴를 크롤링하고 같이 매칭하는 작업을 했으면 더 정확하고 더 높은 정확도가 나올 것이라는 아쉬움, 한계를 느낌.
