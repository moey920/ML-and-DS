# ML을 위한 핵심개념

- 데이터 준비
    - 데이터(Data)
    - 변수(Variable)
    - 특성(Feature)
    - 목표값(Target)

- 모델 구축&분석
    - 모델(Model)
    - 알고리즘(Algorithm)
    - 오차(Error)
    - 손실(Loss), 비용(Cost)
    - 학습(Learning)

===

# 데이터(Data)의 정의

> 현실 세계의 **어떤 현상**(일부)을 관찰하여 기록한 것

관찰할 수 없는 것은 데이터에 담길 수 없다. 

- 데이터의 예: 심장 데이터
    - 심장 상태를 관찰하여 기록한 것
    - 데이터의 질은 데이터를 수집하는 센서의 질과 양과도 관련이 있다.

- 현실의 일부로서의 데이터
    - 데이터에 담기지 않은 누락된, 감추어진 사실이 무엇인지 반드시 생각해야한다.(관찰되지 않는 사실)

## 데이터의 특징

- 객관화된 자료라는 믿음
- 수치 자체는 의미가 없다
- 데이터는 현실의 재현(Re-Presentation)이다. 복제가 아니다. 재현이기 때문에 담지 못하는 것이 존재한다.

- 데이터의 특징에 대한 예시

```
성별: 남성
나이: 45세 # 수치 자체는 의미 없으마 세, cm, kg 등의 붙어 의미가 생긴다.
키: 178 cm
몸무게: 79kg
```

## 데이터의 종류

1. 정형(structured) 데이터
    - 테이블 형태의 데이터
2. 비정형(unstructured) 데이터
    - 이미지, 텍스트, 영상, 음성 등
    - 반드시 테이블 형태로 전처리 해야한다.

### 훈련 데이터 vs 테스트 데이터

- 훈련 데이터 (Training Data) : 모델 학습에 사용하는 데이터, parameter
feature + target

- 테스트 데이터 (Testing Data) : 예측의 정확도를 판단하는 데에만 사용하는 데이터
feature + target

- 검증 데이터 (Validation Data) : 모델의 복잡도를 결정하는 hyper parameter를 찾기위해 사용하는 데이터

전체 데이터 (Original Data) : Training Data + Validation Data + Testing Data

## Feature의 정의

> Feature는 데이터(data)를 컴퓨터가 이해할 수 있도록 수치(numeric) 또는 디지털(digitized)로 표현/표상(representation)한 것

### Feature의 동의어
- 변수 Variable
- 독립변수 Independent Variable
- 설명변수 Explanatory Variable
- 예측인자 Predictor
- 입력값 Input Value
- 속성 Attribute

## 목표값(Target)의 정의

- 예측하려는 목표

## 모델(Model)의 정의

- 실제의 무엇을 더 작게 추상화된 형태로 표현한 것, 모형 또는 본보기
- 모델 예시 : 지도, 어떤 지도가 좋은 지도인지는 목적에 따라 다르다.
- 모델은 사용 목적에 얼마나 적합한가가 중요하다.
- 목적에 맞게 모델을 선택하는 능력이 필요하다.

### 머신러닝에서 모델이란?

- 어떠한 문제를 해결하기 위해 수립한 가설을 논리적, 수학적 함수식의 형태로 표현한 것

### 모델의 파라미터(parameter)와 하이퍼 파라미터(hyper-parameter)

- 하이퍼 파라미터 : 모델의 복잡도와 관련

1. y = ax + b (가설) , 정확한 a,b값 찾는 것이 목표, **훈련데이터를 이용해 파라미터를 찾는 것이 목표**이다.(a, b)   
2. y = ax^2 + bx + c : 직선보다 더 복잡. 차수가 높아질수록 복잡도가 높아진다. 데이터를 좀 더 정확하게 예측할 수 있다. (모델이 유연하다)   
이 경우에 **몇 차수(n)로 진행할지가 바로 하이퍼 파라미터**이다.


## 알고리즘(Algorithm)의 정의

> 입력된 자료를 바탕으로 원하는 결과를 유도하기 위해 일련의 논리적인 순서와 절차를 규칙화 한 것

### 머신러닝에서 알고리즘이란?

> 모델이 어떠한 문제를 해결하기 위한 함수식이라면 알고리즘은 그 함수식을 만들어내는 일련의 절차, 규칙

- 알고리즘을 함수식을 만들어내는 방법이다. 모델과 헷갈리지 말 것

##  오차(Error)의 정의

> 오차: 목표값(y)과 예측값(y0)의 차이, Error = y - y'

## 손실함수, 비용함수 (Loss Function, Cost Function)

> 손실함수/비용함수 : 오차를 최적화(최소화)하기 쉬운 형태로 만든 목적함수

- MSE 등 다양한 함수가 존재한다.

## 학습(Learning)의 정의

> 예측 목표로부터 예측 결과의 오차를 최소화(손실함수/비용함수를 최소화)하는 함수식을 시행착오를 통해 찾아내는 과정

=== 

# 데이터 준비의 중요성과 파이프라인

1. 문제파악,문제정의
2. **데이터 준비**
3. 모델 구축 & 분석 (패턴 찾기)
4. 결과 공유
5. 모니터링

## 데이터 준비의 중요성 (1)
- Garbage Input -> Garbage Output : 오염된 데이터를 넣으면 오염된 결과가 나온다.

## 데이터 준비의 중요성 (2)

> Source1(수치형)+Source2(텍스트)+Source3(음성) -> Data -> Data Preprocessing, Feature Engineering -> Features -> Learning

- 학습의 퍼포먼스를 가장 높힐 수 있는 적합한 형태로 데이터를 바꾸는 것이 전처리, Feature Engineering이다.

## 데이터 분석 파이프라인 관점으로 본 데이터 준비 과정

* 파이프라인: 데이터 처리 요소들이 연속적으로 연결된 것

**Data(input) -> Data Acquisition(수집) -> Data Preprocessing -> Feature Engineering -> Feature**

- 데이터 준비 과정은 데이터 분석/머신러닝 프로젝트 성공의 열쇠
    - 대다수의 Data Preprocessing과 Feature Engineering 기법은 **Domain Knowledge**를 필요로 합니다.

### 데이터 전처리(Data Preprocessing)의 정의

- 컴퓨터가 좀 더 잘 받아들일 수 있는 형태로 Data 데이터를 가공하는 작업입니다

### 데이터 전처리의 예시

- Vectorization(벡터화)
    - one-hot encoding : 해당되는 값과 일치하는 위치만 1, 나머지는 모두 0으로 인코딩한다.
    - 자연어 처리에 주로 사용
- Normalization(정규화)
    - 나이와 소득 값이 존재할 때, 나이보다 소득의 범위가 훨씬 크기 때문에 모든 Feature를 0~1 사이의 값으로 변환하는 등의 방법
    - 정규화의 다양한 방법이 있다. 
- Handling Missing Values
    - NaN 등의 값을 처리 : 어떻게 처리할지는 도메인 지식에 따른 판단이 필요하다.
        - df.fillna()
        - mean() : 각 feature 들의 평균값으로 NaN 값을 대체한다.

## 피쳐 엔지니어링(Feature Engineering)의 정의

> 도메인 지식을 활용하여 머신러닝 알고리즘이 학습을 잘 진행할 수 있도록 Preprocessed Data(전처리된 데이터)를 변환하는 작업

- 차원 축소를 위한 피쳐 엔지니어링
    - 세 종류의 데이터를 분류하기 위해서, 몇 차원으로 나타내는 것이 효율적일까? 3차원? 2차원? 1차원?
        - 3차원은 메모리가 너무 커진다
        - 2차원에선 모든 데이터를 적합하게 표현 가능하다
        - 1차원도 어느 정도 데이터 별 구분이 가능하다.
        - 따라서 3차원 데이터를 2, 1차원으로 변환하므로써 사용되는 메모리를 줄이는 등의 역할을 한다.

- 차원의 저주(Curse of Dimensionality) : 어느 정도까지는 차원이 높아질수록 퍼포먼스가 올라가나, 계속 차원이 높아질수록 퍼포먼스는 떨어진다.

## 피쳐 엔지니어링의 예시

- Feature Transformation
- Feature Generation
- Feature Selection
- Feature Extraction
- ……

### Feature Selection vs Feature Extraction

- Feature Selection : x1~x6까지의 6차원 데이터를 3차원으로 줄이고자 할 때 가장 퍼포먼스를 높혀주는 3개의 xn,xn,xn 만 고른다. 
- Feature Extraction : 여러개의 Feature를 조합해서 새로운 Feature z1, z2, z3를 만들어낸다.

===

## 변수에 대해 더 알아보기

- Feature의 동의어로 쓰이기도 한다.
- 변수는 크게 두 개로 나뉜다.

- 1. 변수(Variable) 살펴보기: 수치형(Numeric)
    - 정량적(quantitative)으로 측정 가능한 데이터
    - 정수(integer) / 실수(real-number)
    - 온도, 나이, 속도, 날짜
    - 예) 184.5 cm, 45세
    - 사칙연산이 가능하다.

- 수치형(Numeric) 변수의 두 가지
    - 이산형 (Discrete) 
        - 상품의 개수
        - 정수값으로 표기됨
    - 연속형 (Continuous)
        - 키, 몸무게, 가격
        - 일반적인 실수값

- 2. 변수(Variable) 살펴보기: 범주형(Categorical)
    - 범주(category)로 분류가 가능한 데이터
    - 정성적/질적(qualitative) 데이터
    - 색깔, 성별, 좌석 등급
    - 예) 파란색, 1등급 좌석
    - 덧셈, 뺼셈 등이 불가능하다

- 범주형(Categorical) 변수의 두 가지
    - 명목형 (Nominal)
        - 셀 수는 있지만, 순서를 매길 수 없다.(남성이 몇 명인지 등)
        - 예시) 성별, 취미, 색깔
    - 순서형 (Ordinal)
        - 범주 간 순서가 있다.
        - 좌석 등급, 테이크아웃 커피 사이즈(G, V, T, S)
        - 순서가 있다고 해서, 배수로 증가하는 것은 아니다.
            - 예) 1등급 좌석 vs. 2등급 좌석

### 변수에 대해 더 알아보기
- Target = Dependent Variable = Output Value
- Feature = Explanatory Variable = Predictor = Independent = Variable = Input Value 
- Row = Instance = Observation
- Column = Feature Vector
Feature Vector
Instance, Observation, Row
Numeric, Continuous
03 변수에 대해 더 알아보기
Categorical, Nominal Numeric, Discrete