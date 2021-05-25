# Linear Regression Project - Used Car Price Prediction

- Facilitator: [Andy](https://github.com/Andy-yeongjin)(김영진), [qkrckdgus1015](https://github.com/qkrckdgus1015)(박창현), [Gilbert](https://github.com/Ki-Sung)(김기성)
- Supervisor: [PinkWink](https://github.com/PinkWink)(민형기 강사님) & [FLY-CODE77](https://github.com/FLY-CODE77)(정현석 클래스 매니저님)
- Date : 2021.04.20 ~ 2021.05.20
- 사용언어 및 패키지
  - [![Python Badge](http://img.shields.io/badge/-Python%20-blue?style=flat-square&&logoColor=yellow&logo=python&link=https://www.python.org/)](https://www.python.org/) [![Pandas Badge](http://img.shields.io/badge/-Pandas%20-blue?style=flat-square&logoColor=yellow&logo=pandas&link=https://pandas.pydata.org/)](https://pandas.pydata.org/) [![Matplotlib Badge](http://img.shields.io/badge/-Matplotlib%20-blue?style=flat-square&logoColor=yellow&logo=matplotlib&link=https://matplotlib.org/)](https://matplotlib.org/) [![Pyecharts Badge](http://img.shields.io/badge/-Pyecharts%20-blue?style=flat-square&logoColor=yellow&logo=pyecharts&link=https://pyecharts.org/#/en-us/)](https://pyecharts.org/#/en-us/) [![Seaborn Badge](http://img.shields.io/badge/-Seaborn%20-blue?style=flat-square&logoColor=yellow&logo=seaborn&link=https://seaborn.pydata.org/)](https://seaborn.pydata.org/) [![Sklearn Badge](http://img.shields.io/badge/-Sklearn%20-blue?style=flat-square&logoColor=yellow&logo=scikit-learn&link=https://scikit-learn.org/stable/)](https://scikit-learn.org/stable/)

<img src="https://user-images.githubusercontent.com/80456601/119268747-4b6f4400-bc2f-11eb-835e-65dcbf6a2a59.png" width="80%" height="80%"/>

## 1 프로젝트 주제선정 이유 
<img src="https://user-images.githubusercontent.com/80456601/119459744-ee7fa500-bd78-11eb-84b6-f7c45ecaa8e2.png" width="80%" height="70%"/>

- 한국 소비자 76.4%가 '국내중고차 시장'에 대한 인식으로 '불투명', '혼탁', '낙후하다' 등 부정적으로 인식하고 있습니다. 부정적 인식의 원인으로는 품질 불신, 가성비, 판매자 불신 3가지로 꼽을 수 있습니다.       이런 부정적인 인식으로 만약 한국에서 중고차 거래를 하게 되면 손해볼 것이라는 생각이 들었고, 혹시 다른 나라에서 중고차 거래를 하면 어떨까? 라는 생각을 하게 되었습니다. 그래서 세계 4위 중고차 시장인 인도로 가서   한국 중고차 시장과 얼마나 차이가 있는지 비교해보기로 했습니다. 

### 1-2. 프로젝트 목적
#### 1) 인도 중고차 시장 탐색 
- 인도 중고차 시장을 파악하기 위해 EDA를 진행하여 데이터 분석을 하고자합니다.
- EDA 파트를 보시고 싶으시면 'used_car_EDA.ipynb'파일을 참조 부탁드립니다.
#### 2) 모델링 구축
- 인도 중고차 시장을 파악 후 여러기지 모델링을 구상해 봅니다. 
- 여기서는 Linear Regression과 RandomForest Regressor 방식을 사용하고자 합니다.
#### 3) 예측값 검증 
- 우리가 구축한 모델링을 바탕으로 과연 어느 지역에서 중고차를 판매해야 좋은 가격을 받을 수 있는지 검증하고자 합니다.

#### 자료 : 본 프로젝트는 kaggle에 있는 [인도 중고차 예측하기](https://www.kaggle.com/avikasliwal/used-cars-price-prediction)의 자료를 바탕으로 진행하였습니다.



## 2. 프로젝트 진행순서
#### 1) 데이터 탐색과 전처리를 진행합니다.
#### 2) 회귀 모델을 구축하고 검증해봅니다.
#### 3) 예측한 중고차 가격을 바탕으로 결론을 도출해봅니다.

## 3. 프로젝트시 사용한 패키지 및 모델
### 3-1. 컬럼명칭

<img src="https://user-images.githubusercontent.com/80456601/119350278-1c61dc80-bcda-11eb-8b3a-8dbc300b36c6.png" width="80%" height="50%"/>

### 3-2 비쥬얼라이제이션 패키지 

<img width="1113" alt="스크린샷 2021-05-25 오후 4 26 05" src="https://user-images.githubusercontent.com/80456601/119462773-115f8880-bd7c-11eb-9418-4fecdff3c6bc.png">

- 시각화의 가독성을 위해 그래프는 'pyecharts' 패키지를 사용하였습니다. 
- github 파일 중 'used_car_Visualization.ipynb'을 참고 부탁드립니다.
