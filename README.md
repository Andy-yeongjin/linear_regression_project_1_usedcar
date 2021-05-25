# Linear Regression Project - Used Car Price Prediction

- Facilitator: [Andy](https://github.com/Andy-yeongjin)(김영진), [qkrckdgus1015](https://github.com/qkrckdgus1015)(박창현), [Gilbert](https://github.com/Ki-Sung)(김기성)
- Supervisor: [PinkWink](https://github.com/PinkWink)(민형기 강사님) & [FLY-CODE77](https://github.com/FLY-CODE77)(정현석 클래스 매니저님)
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

<img src="https://user-images.githubusercontent.com/80456601/119350278-1c61dc80-bcda-11eb-8b3a-8dbc300b36c6.png" width="80%" height="50%"/>


#### 2) 분석
- 브랜드별 거래량을 기준으로 인도 시장에서는 Maruti & Suziki 19.44%로 1위 Hyundai 18.45%로 2위 Honda가 10.22%로 3위 순으로 거래가 이루어지고 있습니다.
- 지역별로는 Mumbai 지역 13.11%로 중고차 거래가 가장 활발한 지역임을 나타낼 수 있습니다. 

<img src="https://user-images.githubusercontent.com/80456601/119268253-12ce6b00-bc2d-11eb-987e-9ea0534c778e.png" width="50%" height="50%"/><img src="https://user-images.githubusercontent.com/80456601/119268438-f848c180-bc2d-11eb-82f2-9430a68cd6b2.png" width="50%" height="50%"/>

- 연도별 거래량은 2014년이 797 건으로 가장 많았고, 1999년은 2건으로 가장 적었습니다. 추가가로 거래량은 2014년 까지 늘었다가 2015년 부터 거래량이 줄어 중고차 시장 침채기가 계속된 것으로 볼 수 있습니다. (참고로 인도 자동차 시장이 요즘 부진한 이유는 '그림자 금융[일반 은행이 아닌 규제를 받지 않는 비은행의 금융 상품]'으로 위기에 빠져 자동차를 사기 위한 재원 조달이 어려지고, 최근 배기가스 기준이 염격해지고, 배터리 전기차 개발 경쟁으로 투자에 부담을 느껴 판매 감소까지 이어져 타격을 받고 있다고 합니다. [참조: 다나와뉴스커뮤니티](http://auto.danawa.com/news/?Tab=N1&Work=detail&no=4029265))

<img  src="https://user-images.githubusercontent.com/80456601/119281298-2b13a980-bc70-11eb-8cd5-cdc06d541ec3.png" width="80%" height="80%"/>

- 인도시장은 Disel-53.25%, Petrol-45.62%로 디젤차의 거래량이 가장 많았습니다. (인도시장은 디젤차가 저렴하고 디젤차에 대한 규제가 강하지 않아 거래량이 많은 것으로 악됩니다.)

<img src="https://user-images.githubusercontent.com/80456601/119283756-f9eba700-bc78-11eb-8075-b23f42f3eaab.png" width="70%" height="70%"/>

- 기어타입 수동기어 자동차가 71.45%으로 거래량이 많았습니다 (가격이 저렴한 것과 관련이 있습니다.) 

<img src="https://user-images.githubusercontent.com/80456601/119283859-3ae3bb80-bc79-11eb-9af4-b2d94f3de441.png"  width="70%" height="70%"/>

- 오너타입은 첫번쨰 오너가 가장 많았습니다.

<img src="https://user-images.githubusercontent.com/80456601/119284662-36200700-bc7b-11eb-9898-e6063095679a.png" width="70%" height="70%"/>

- EDA를 바탕으로 내용을 정리하자면 인도 중고차 시장은 2015년까지 상승하였다가 2016년부터 거래량이 꾸준히 하락하여 감소추세를 보이고 있고, 인도에서 가장 거래가 많은 브랜드는 'Maruti Suziki', 'Hyundai', 'Honda', 인도의 중고차 중 연료 타입은 Disel이 53.25%를 차지하고 있고, 기어타입은 수동이 71.45%로 수동기어 타입을 선호하는 것으로 나타났습니다. 마지막으로 오너 타입은 첫번째 오너가 가장 많은 것으로 나타났습니다.
- '그림자 금융'으로 자동차를 사기 위한 재원 조달이 어려워지고, 최근 배기가스 기준이 엄격해지고, 배터리 전기차 개발 경쟁으로 투자에 부담을 느껴 판매 감소까지 이어져 타격을 받은 원인으로 중고차를 넘어 인도 자동차 시장 자체가 침채기 인 것은 확실 합니다. 그럼에도 불구하고 인도 자동차 시장의 견조한 성장세가 기대되는 이유는 이미 세계 4위 규모인 자동차 판매 시장 보유국이라는 점과 강력한 경제성장에 따른 소득 증가가 자동차 수요확대로 이어질 것으로 예상되기 때문입니다.
- 만약 인도 중고차에대해 더 다양한 정보를 원하시는 경우 [KOTRA 인도 자동차 시장 전망](https://www.kita.net/cmmrcInfo/cmmrcNews/overseasMrktNews/overseasMrktNewsDetail.do?pageIndex=1&nIndex=1799052&type=0) 자료를 참고 부탁드립니다. 
