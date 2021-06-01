# Linear Regression Project - Used Car Price Prediction

- Dataset : 본 프로젝트는 kaggle에 있는 [인도 중고차 예측하기](https://www.kaggle.com/avikasliwal/used-cars-price-prediction)의 자료를 바탕으로 진행하였습니다.
- Facilitator: [Andy](https://github.com/Andy-yeongjin)(김영진), [qkrckdgus1015](https://github.com/qkrckdgus1015)(박창현), [Gilbert](https://github.com/Ki-Sung)(김기성)
- Supervisor: [PinkWink](https://github.com/PinkWink)(민형기 강사님) & [FLY-CODE77](https://github.com/FLY-CODE77)(정현석 클래스 매니저님)
- Date : 2021.04.20 ~ 2021.05.20
- 사용언어 및 패키지
  - [![Python Badge](http://img.shields.io/badge/-Python%20-blue?style=flat-square&&logoColor=yellow&logo=python&link=https://www.python.org/)](https://www.python.org/) [![Numpy Badge](http://img.shields.io/badge/-Numpy%20-013243?style=flat-square&&logoColor=white&logo=numpy&link=https://numpy.org/)](https://numpy.org/) [![Pandas Badge](http://img.shields.io/badge/-Pandas%20-150458?style=flat-square&logoColor=white&logo=pandas&link=https://pandas.pydata.org/)](https://pandas.pydata.org/) [![Matplotlib Badge](http://img.shields.io/badge/-Matplotlib%20-2350A9?style=flat-square&logoColor=white&logo=matplotlib&link=https://matplotlib.org/)](https://matplotlib.org/) [![Seaborn Badge](http://img.shields.io/badge/-Seaborn%20-212E50?style=flat-square&logoColor=white&logo=seaborn&link=https://seaborn.pydata.org/)](https://seaborn.pydata.org/) [![Pyecharts Badge](http://img.shields.io/badge/-Pyecharts%20-34E0A1?style=flat-square&logoColor=black&logo=pyecharts&link=https://pyecharts.org/)](https://pyecharts.org/) [![Sklearn Badge](http://img.shields.io/badge/-Sklearn%20-F7931E?style=flat-square&logoColor=black&logo=scikit-learn&link=https://scikit-learn.org/stable/)](https://scikit-learn.org/stable/)


<img src="https://user-images.githubusercontent.com/80456601/119268747-4b6f4400-bc2f-11eb-835e-65dcbf6a2a59.png" width="80%" height="80%"/>


## 1. 프로젝트 주제선정 이유 
<img src="https://user-images.githubusercontent.com/80456601/119459744-ee7fa500-bd78-11eb-84b6-f7c45ecaa8e2.png" width="80%" height="70%"/>

- 한국 소비자 76.4%가 '국내중고차 시장'에 대한 인식으로 '불투명', '혼탁', '낙후하다' 등 부정적으로 인식하고 있습니다. 부정적 인식의 원인으로는 품질 불신, 가성비, 판매자 불신 3가지로 꼽을 수 있습니다.       이런 부정적인 인식으로 만약 한국에서 중고차 거래를 하게 되면 손해볼 것이라는 생각이 들었고, 혹시 다른 나라에서 중고차 거래를 하면 어떨까? 라는 생각을 하게 되었습니다. 그래서 세계 4위 중고차 시장인 인도로 가서   한국 중고차 시장과 얼마나 차이가 있는지 비교해보기로 했습니다. 


## 2. 프로젝트 프로세스 & 목적 

<img src="https://user-images.githubusercontent.com/80456601/120065225-2e14fc80-c0ab-11eb-9950-fe65f884bf64.png" width="80%" height="80%"/>


## 3. 프로젝트시 사용한 모델

<img src="https://user-images.githubusercontent.com/80456601/120070388-40039900-c0c5-11eb-8611-8aaaf61746b6.png" width="80%" height="80%"/>

- 본 프로젝트에서 사용한 모델은 몇 번의 반복적인 모델링을 돌려 본 결과 'LinearRegression'과'RandomForestRegressor' 정확도가 높아  두 모델을 사용하였습니다.
- 참고로 'LinearRegression'는 R2 score가 0.78%, MSE: 27.08 / 'RandomForestRegressor'는 R2 score가 0.92%, MSE: 10.53으로 'RandomForestRegressor'의 정확도가 높습니다.
- 모델의 정확도를 올리기위해 log를 씌워 보았는데, 놀랍게도 'LinearRegression'는 R2 score가 0.78% -> 0.92, MSE: 27.08 -> 0.01 / 'RandomForestRegressor'는 R2 score가 0.92% -> 0.94, MSE: 10.53 -> 0.008로 정확도가 높게 상승하였습니다. 
- 더 자세한 사항은 '**used_car_modeling.ipynb**'자료를 참고 부탁드립니다.

## 4. EDA
### 4-1. 컬럼명칭

<img src="https://user-images.githubusercontent.com/80456601/119350278-1c61dc80-bcda-11eb-8b3a-8dbc300b36c6.png" width="80%" height="50%"/>

### 4-2 분석

<img width="1113" alt="스크린샷 2021-05-25 오후 4 26 05" src="https://user-images.githubusercontent.com/80456601/119462773-115f8880-bd7c-11eb-9418-4fecdff3c6bc.png">

- 시각화의 가독성을 위해 그래프는 'pyecharts' 패키지를 사용하였습니다. 
- github 파일 중 'used_car_Visualization.ipynb'을 참고 부탁드립니다.
- EDA를 바탕으로 내용을 정리하자면 인도 중고차 시장은 2015년까지 상승 하였다가 2016년부터 거래량이 꾸준히 하락하여 감소추세를 보이고 있고, 인도에서 가장 거래가 많은 브랜드는 'Maruti Suziki', 'Hyundai', 'Honda', 인도의 중고차 중 연료 타입은 Disel이 53.25%를 차지하고 있고, 기어타입은 수동이 71.45%로 수동기어 타입을 선호하는 것으로 나타났습니다. 마지막으로 오너 타입은 첫번째 오너가 가장 많은 것으로 나타났습니다.
- '그림자 금융'으로 자동차를 사기 위한 재원 조달이 어려워지고, 최근 배기가스 기준이 엄격해지고, 배터리 전기차 개발 경쟁으로 투자에 부담을 느껴 판매 감소까지 이어져 타격을 받은 원인으로 중고차를 넘어 인도 자동차 시장 자체가 침채기 인 것은 확실 합니다. 그럼에도 불구하고 인도 자동차 시장의 견조한 성장세가 기대되는 이유는 이미 세계 4위 규모인 자동차 판매 시장 보유국 이라는 점과 강력한 경제성장에 따른 소득 증가가 자동차 수요확대로 이어질 것으로 예상되기 때문입니다.
- 만약 인도 중고차에대해 더 다양한 정보를 원하시는 경우 [KOTRA 인도 자동차 시장 전망](https://www.kita.net/cmmrcInfo/cmmrcNews/overseasMrktNews/overseasMrktNewsDetail.do?pageIndex=1&nIndex=1799052&type=0) 자료를 참고 부탁드립니다.


<img src="https://user-images.githubusercontent.com/80456601/120257485-4ebb9d00-c2cb-11eb-92bf-98fd7330ee2c.png" width="60%" height="50%"/>

- 히트맵에서는 엔진과 마력 : 0.86, 마력과 가격 : 0.77, 엔진과 가격 : 0.66, 마력과 자동변속기 0.64로 나타나 엔진과 마력의 상관관계가 가장 높다고 나왔습니다. 
- 하지만 엔진과 연비 : -0.64, 변속기 수동과 가격 : -0.59, 연비와 마력 : -0.54로 엔진과 연비는 상관이 있을 것이다 라는 저희의 생각과 달리 의외로 엔진과 연비가 관계가 없는 것으로 나왔습니다.
