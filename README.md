# 소설 작가 분류 AI 개발

멀티캠퍼스 [4차산업 선도인력] 딥러닝 기반 AI 엔지니어링 과정 수강생들의 자연어 처리 프로젝트입니다.



## 목차

1. 프로젝트 설명
2. 프로젝트 기간
3. 프로젝트 구조와 환경
4. 수행 절차 및 결과



## 1. 프로젝트 설명

#### [프로젝트 주제: 소설 작가 문체를 분석하는 AI 알고리즘 개발]

* 글을 읽다 보면 작가마다 개성 있는 글쓰기 스타일이 있다는 것을 발견하게 됩니다. 이러한 문장적 특색을 문체, 우리말로는 ‘글투’라고 합니다. 문체는 작가의 지문과 비슷한 역할을 하기 때문에 우리는 글을 읽을 때 문체를 통해 누가 쓴 글인지 구별할 수 있습니다. 문체를 구분하는 인공지능을 이용한다면 책 일부분만으로도 글의 저자가 누구인지 비교, 분석할 수 있습니다.
* 기대효과:  특정 필자의 글투를 흉내내고 악용하는 사례로 이메일 사칭, 창작물 대필, 유사 작품 창작 등이 있습니다. 자연어 처리 기술을 활용한 문체 분석은 이러한 범죄를 탐지하는 데에 유용할 것입니다. 



#### [프로젝트 목적]

* 소설 문장 속 단어 사용과 특징을 분석하여 어떤 작가인 글인지 예측하는 다양한 머신러닝, 딥러닝 모델을 개발하고 비교
* 월간 데이콘 "소설 작가 분류 AI 경진대회"에서 높은 점수 획득
  * https://dacon.io/competitions/official/235670/overview/



## 2. 프로젝트 기간

#### [프로젝트 기간]

* 총 개발 기간 : 2020/10/29 ~ 11/11 (2주)

|      구분      |     기간      |                             활동                             |        비고        |
| :------------: | :-----------: | :----------------------------------------------------------: | :----------------: |
|      기획      | 10/29 ~ 10/30 |                  프로젝트 기획 및 주제 선정                  |   아이디어 선정    |
|      개발      | 10/30 ~ 11/02 |                데이터셋 1차 분석 & 모델 선정                 |   EDA & Research   |
|                | 11/03 ~ 11/08 | 데이터 전처리 자료조사 및 연구 <br/>& 문체 분석 알고리즘 개발 | 알고리즘 성능 향상 |
| 수정/보완/발표 | 11/09 ~ 11/11 |           코드 정리, 수정, 보완 & 결과 보고서 작성           |     오류 수정      |



## 3. 프로젝트 구조와 환경

* 데이콘에서 제공하는 소설 문장 뭉치 데이터를 이용하여 5명의 작가들을 구별
  * 문장 언어 = 영어
* 진행 과정 : 1) 텍스트 전처리, 2) 특징 추출, 3) 작가 구별, 4) 데이콘 리더보드에서 모델 성능 평가
* 사용 모델 : TF-IDF & Logistic Regression, Word2Vector, 다층 퍼셉트론, 나이브 베이즈 분류기
* 모델 평가 산식 : Logloss
* 활용 언어 : Python, R



## 4. 수행 절차 및 결과

#### [데이터 전처리 및 시각화]

* 특수문자 및 문장 부호 제거
* 불용어 제거
* 작가별 워드클라우드에서 공통적으로 나타나는 단어 "odin" 제거 -> 작가 비식별화를 위해 대회 측에서 삽입한 단어로 취급

![image1](C:\Users\Lee Chanju\Documents\Multicampus\Semi-project_01\image1.PNG)

* 작가별 단어 사용 빈도수 시각화
  * 다섯 작가 모두 "said"가 가장 많이 등장 -> 소설이라는 특성상, ~~가 말했다 형식의 문체를 드러냄

![image2](C:\Users\Lee Chanju\Documents\Multicampus\Semi-project_01\image2.PNG)



#### [모델 개발 및 성능 비교]

**모델 평가 지표 : Logloss**

* 작가 분류 확률 값을 평가 지표로 사용 -> Logloss는 모델이 예측한 확률 값을 직접적으로 반영하여 평가



**사용 모델**

* TF-IDF (Term Frequency-Inverse Document Frequency) & Logistic Regression
* Word2Vec

![image3](C:\Users\Lee Chanju\Documents\Multicampus\Semi-project_01\image3.PNG)

* 다층 퍼셉트론 (Multi-Layer Perceptron)
* 나이브 베이즈 분류기 (Naive Bayes Classifier)



**=> Logloss 낮은 순으로 모델 정렬 : **

​	**나이브 베이즈 분류기 < 다층 퍼셉트론 < Word2Vec < Logistic Regression**

​		*\*Logloss가 낮을 수록 모델 정확도가 높음을 의미함*



**데이터 전처리 방식에 따른 모델 성능 비교**

<img src="C:\Users\Lee Chanju\Documents\Multicampus\Semi-project_01\image.PNG" alt="image" style="zoom: 50%;" />