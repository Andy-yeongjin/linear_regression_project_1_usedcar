# Linear Regression Project - Used Car Price Prediction

- Andy(김영진), qkrckdgus1015(박창현), Gilbert(김기성)
- monitoring by PinkWink(민형기 강사님) & FLY-CODE77(정현석 클래스 매니저님)
- 사용언어 및 패키지
  - [![Python Badge](http://img.shields.io/badge/-Python%20-blue?style=flat-square&&logoColor=yellow&logo=python&link=https://www.python.org/)](https://www.python.org/) [![Pandas Badge](http://img.shields.io/badge/-Pandas%20-blue?style=flat-square&logoColor=yellow&logo=pandas&link=https://pandas.pydata.org/)](https://pandas.pydata.org/) [![Matplotlib Badge](http://img.shields.io/badge/-Matplotlib%20-blue?style=flat-square&logoColor=yellow&logo=matplotlib&link=https://matplotlib.org/)](https://matplotlib.org/) [![Pyecharts Badge](http://img.shields.io/badge/-Pyecharts%20-blue?style=flat-square&logoColor=yellow&logo=pyecharts&link=https://pyecharts.org/#/en-us/)](https://pyecharts.org/#/en-us/) [![Seaborn Badge](http://img.shields.io/badge/-Seaborn%20-blue?style=flat-square&logoColor=yellow&logo=seaborn&link=https://seaborn.pydata.org/)](https://seaborn.pydata.org/) [![Sklearn Badge](http://img.shields.io/badge/-Sklearn%20-blue?style=flat-square&logoColor=yellow&logo=scikit-learn&link=https://scikit-learn.org/stable/)](https://scikit-learn.org/stable/)

<img src="https://user-images.githubusercontent.com/80456601/119268747-4b6f4400-bc2f-11eb-835e-65dcbf6a2a59.png" width="80%" height="80%"/>

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
#### 1) 컬럼명칭
<img src="https://user-images.githubusercontent.com/80456601/119280709-8abc8580-bc6d-11eb-947f-8e8d28dba700.png" width="50%" height="40%"/>

- Name : 자동차 브래드와 모델명 
- Location : 자동차를 판매하는 위치 
- Year : 자동차 모델 연도 
- Kilometers Driven : 이전 소유자가 사용한 주행거리 (단위 : KM)
- Fuel Type : 자동차에서 사용하는 연료 유형 (가솔린, 디젤, 전기, CNG, LPG) 
  * CNG: 가정 및 공장 등에서 사용하느 도시가스를 약 200 기압으로 압축한 연료
  * LPG: 석유성분 중 끓는점이 낮은가스를 상온에 기입하여 액화한 연료 
- Transmission : 변속기 유형 (Automatic: 자동 / Manual: 수동)
- Owner Type : First(첫번쨰 오너), Second(두번쨰 오너), Third(세번째 오너), Fourth & Above(4번쨰 이상 오너)
- Mileage : 연비 (자동차 회사에서 제공하는 표준 연비)
- Engine : 엔진 배기량 (단위: cc)
- Power : 엔진 최대 출력 (bnp: 제동마력 - 실제로 엔진이 돌아가는 힘)
- Seats : 자동차 좌석수
- New Price : 해당 모델 새차 가격
- Price : 중고차 가격(인도화페 루피 Lakh(라크) - 100,000 루비)

#### 2) 분석
- 브랜드별 거래량을 기준으로 인도 시장에서는 Maruti & Suziki 19.44%로 1위 Hyundai 18.45%로 2위 Honda가 10.22%로 3위 순으로 거래가 이루어지고 있습니다.
- 지역별로는 Mumbai 지역 13.11%로 중고차 거래가 가장 활발한 지역임을 나타낼 수 있습니다. 

<img src="https://user-images.githubusercontent.com/80456601/119268253-12ce6b00-bc2d-11eb-987e-9ea0534c778e.png" width="50%" height="50%"/><img src="https://user-images.githubusercontent.com/80456601/119268438-f848c180-bc2d-11eb-82f2-9430a68cd6b2.png" width="50%" height="50%"/>

- 연도별 거래량은 2014년이 797 건으로 가장 많았고, 1999년은 2건으로 가장 적었습니다. 추가가로 거래량은 2014년 까지 늘었다가 2015년 부터 거래량이 줄어 중고차 시장 침채기가 계속된 것으로 볼 수 있습니다. (참고로 인도 자동차 시장이 요즘 부진한 이유는 '그림자 금융[일반 은행이 아닌 규제를 받지 않는 비은행의 금융 상품]'으로 위기에 빠져 자동차를 사기 위한 재원 조달이 어려지고, 최근 배기가스 기준이 염격해지고, 배터리 전기차 개발 경쟁으로 투자에 부담을 느껴 판매 감소까지 이어져 타격을 받고 있다고 합니다. [참조: 다나와뉴스커뮤니티](http://auto.danawa.com/news/?Tab=N1&Work=detail&no=4029265))

<img  src="https://user-images.githubusercontent.com/80456601/119281298-2b13a980-bc70-11eb-8cd5-cdc06d541ec3.png" width="80%" height="80%"/>

- 인도시장은 Disel-53.25%, Petrol-45.62%로 디젤차의 거래량이 가장 많았습니다. (인도시장은 디젤차가 저렴하고 디젤차에 대한 규제가 강하지 않아 거래량이 많은 것으로 팍악됩니다.)

<img src="https://user-images.githubusercontent.com/80456601/119283756-f9eba700-bc78-11eb-8075-b23f42f3eaab.png" width="70%" height="70%"/>

- 기어타입 수동기어 자동차가 71.45%으로 거래량이 많았습니다 (가격이 저렴한 것과 관련이 있습니다.) 

<img src="https://user-images.githubusercontent.com/80456601/119283859-3ae3bb80-bc79-11eb-9af4-b2d94f3de441.png"  width="70%" height="70%"/>

- 오너타입은 첫번쨰 오너가 가장 많았습니다.

<img src="https://user-images.githubusercontent.com/80456601/119284662-36200700-bc7b-11eb-9898-e6063095679a.png" width="70%" height="70%"/>

