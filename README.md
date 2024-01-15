# Tobigs20-conference
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
1. consider both text classification and topic modeling
2. text classification with KoBERT  
   2-1. sentence transform  
   2-2. BERTDataset  
   2-3. BERTClassifier  
   2-4. Class and predict label  
3. Topic Modeling with KoBERTopic  
   3-1. Embed Document  
   3-2. UMAP(decomposition)  
   3-3. HDBSCAN(clsutering)  
   3-4. TF-IDF   
4. making library  

### time_series model
1. consider both title and content
2. title : learning clickbaitClass
3. content : textRank + ko-BART + Jaccard Similarity
4. model : FNN model(title_prob + content_prob)
5. making library

### DA(domain adaptation)
1. news data & factcheck data crawling
2. crawling data preprocessing(summerization + labeling)
3. STS + NLI model(by KLUE & roBERTa)
4. final sentence and judgment of T/F about news
5. making library

## 참고 자료
https://today-1.tistory.com/60  
[https://github.com/Huffon/klue-transformers-tutorial.git](https://github.com/cure-lab/LTSF-Linear)

