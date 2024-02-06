# Tobigs20-conference

(아직 정리가 안됨...)
## 도와줘 소상공인! : 신입 소상공인을 위한 시장 매력도 제공 서비스 :chart_with_upwards_trend: :chart_with_downwards_trend:

투빅스 20기 Time_Series 프로젝트로 시장 매력도를 통해 소상공인을 도와주기 위한 상품 시계열 예측 프로젝트를 진행했습니다.

![1](https://github.com/choitaesoon/Tobigs20_conference/assets/113870266/33818a15-eb74-4378-8ec7-c510be79fd73)

크게 시계열을 활용한 미래 예측과 DA(Domain Adaptation)을 이용한 예측으로 분석을 진행했습니다.
시계열 예측에는 기본 baseline model로
1. LSTM
2. LTSF-DLinear
을 사용하였으며
DA에서는 LSTM을 활용하여 모델을 새롭게 정의했습니다.

각 파트별로 코드를 정리해두었습니다.

## 발표 🙋

컨퍼런스 발표 ppt입니다. 자세한 분석 내용은 아래 링크를 통해 확인해주세요!  
- [Slide](https://docs.google.com/viewer?url=https://github.com/choitaesoon/Tobigs19-conference/files/13938902/tobigs20_conference_time_series.pdf?raw=True)

## 멤버 🧑‍🤝‍🧑

- 본 프로젝트에는 [빅데이터 분석 및 인공지능 대표 연합동아리 ToBig's](http://www.datamarket.kr/xe/) 멤버들이 참여하였습니다.

|기수|이름|
|:-----:|:-----:|
|19기|[이동준]|
|18기|[임지영]|
|19기|[최태순]|
|20기|[김지우]|
|20기|[정준호]|
|20기|[조미현]|
|20기|[황민정]|

## 내용 정리

### Data load  
1. LG-Aimers data  
  1-1. sales_cnt  
  1-2. sales_prc  
  1-3. brand_keyword_cnt  
* 링크 : [DACON LG-Aimers](https://dacon.io/competitions/official/236129/codeshare)

### time_series model  
1. LSTM  
2. LTSF-DLinear  
3. parameter  
  3-1. window_size = 30  
  3-2. forcast_size = 10  
  3-3. batch_size = 32  
  3-4. MSELoss  
  3-5. Adam optimizer  
  
### DA(domain adaptation)  
1. DA(Domain Adaptation)  
   1-1. ADDA(Adversarial Discriminative Domain Adaptation) model  
   1-2. LSTM(Source model = CNN -> LSTM)  
2. parameter  
  2-1. window_size = 100  
  2-2. forcast_size = 50  
  2-3. learning_rate = 0.001  
  2-4. epoch = 300  
  2-5. MSELoss (+Reconstruction Loss)  
  2-6. Adam optimizer  

## 평가

1. Prediction
  
|FEATURE|LSTM|DLINEAR|
|:-----:|:-----:|:-----:|
|판매량|0.038|0.031|
|판매금액|0.168|0.094|
|언급량|0.010|0.015|
2. Domain Adaptaion  
  
|Pair of classification|not_DA|ADDA|ADDA + Reconstruction Loss|
|:-----:|:-----:|:-----:|:-----:|
|대분류 -> 중분류|0.499|0.464|0.439|
|대분류 -> 소분류|0.257|0.255|0.243|
|중분류 -> 소분류|0.417|0.0.401|0.400|


## 참고 자료
https://today-1.tistory.com/60  
[https://github.com/Huffon/klue-transformers-tutorial.git](https://github.com/cure-lab/LTSF-Linear)

