# Linear Regression Project - Used Car Price Prediction

- Andy(김영진), qkrckdgus1015(박창현), Gilbert(김기성)
- monitoring by PinkWink(민형기 강사님) & FLY-CODE77(정현석 클래스 매니저님)
- 사용언어 및 패키지
  - [![Python Badge](http://img.shields.io/badge/-Python%20-blue?style=flat-square&&logoColor=yellow&logo=python&link=https://www.python.org/)](https://www.python.org/) [![Pandas Badge](http://img.shields.io/badge/-Pandas%20-blue?style=flat-square&logoColor=yellow&logo=pandas&link=https://pandas.pydata.org/)](https://pandas.pydata.org/) [![Matplotlib Badge](http://img.shields.io/badge/-Matplotlib%20-blue?style=flat-square&logoColor=yellow&logo=matplotlib&link=https://matplotlib.org/)](https://matplotlib.org/) [![Pyecharts Badge](http://img.shields.io/badge/-Pyecharts%20-blue?style=flat-square&logoColor=yellow&logo=pyecharts&link=https://pyecharts.org/#/en-us/)](https://pyecharts.org/#/en-us/) [![Seaborn Badge](http://img.shields.io/badge/-Seaborn%20-blue?style=flat-square&logoColor=yellow&logo=seaborn&link=https://seaborn.pydata.org/)](https://seaborn.pydata.org/) [![Sklearn Badge](http://img.shields.io/badge/-Sklearn%20-blue?style=flat-square&logoColor=yellow&logo=scikit-learn&link=https://scikit-learn.org/stable/)](https://scikit-learn.org/stable/)

<img src="https://user-images.githubusercontent.com/80456601/119268747-4b6f4400-bc2f-11eb-835e-65dcbf6a2a59.png" width="80%" height="80%">

## 1. 개요
### 1-1. 프로젝트 주제
- 인도 중고차 자료를 바탕으로 실제 중고차 가격과 선형회귀 모델을 통한 중고차 예측값을 비교하여, 어느지역에 중고차를 좋은 값에 거래할 수 있는지 알아보고자 합니다.
- 본 프로젝트는 kaggle에 있는 [인도 중고차 예측하기](https://www.kaggle.com/avikasliwal/used-cars-price-prediction)의 자료를 바탕으로 진행하였습니다.

### 1-2. 프로젝트 목적
#### 1) 인도 중고차 시장 탐색 
- 인도 중고차 시장을 파악하기 위해 EDA를 진행하여 데이터 분석 및 시각화를 나태보고자 합니다.
#### 2) 모델링 구축
- 인도 중고차 시장을 파악 후 여러기지 모델링을 구상해 봅니다. 
- 여기서는 Linear Regression과 RandomForest Regressor 방식을 사용하고자 합니다.
#### 3) 예측값 결론 
- 우리가 구축한 모델링을 바탕으로 과연 어느 지역에서 중고차를 판매해야 좋은 가격을 받을 수 있는지 결론을 내보고자 합니다.

### 1-3. 프로젝트 진행순서
#### 1) 데이터 탐색과 전처리를 진행합니다.
#### 2) 회귀 모델을 구축하고 검증해봅니다.
#### 3) 예측한 중고차 가격을 바탕으로 결론을 도출해봅니다.

## 2. 데이터 탐색 및 전처리
### 2-1. 데이터 탐색
- 브랜드별 거래량을 기준으로 인도 시장에서는 Maruti & Suziki 19.44%로 1위 Hyundai 18.45%로 2위 Honda가 10.22%로 3위 순으로 거래가 이루어지고 있습니다.
- 지역별로는 Mumbai 지역 13.11%로 중고차 거래가 가장 활발한 지역임을 나타낼 수 있습니다. 

<img src="https://user-images.githubusercontent.com/80456601/119268253-12ce6b00-bc2d-11eb-987e-9ea0534c778e.png" width="50%" height="50%"/><img src="https://user-images.githubusercontent.com/80456601/119268438-f848c180-bc2d-11eb-82f2-9430a68cd6b2.png" width="50%" height="50%"/>

