# lec 01

## Contents

- What is ML?
- What is learning?
  - supervised learning
  - unsupervised learning
- Supervised learning
  - What is regression?
  - What is classification?
  - What is Multi-label Classification?
    ㅤ

ㅤ

ㅤ

ㅤ

## 1. What is ML

_ML = Machine Learning_  
ML은 `Explicit programming`가 불가능하기 때문에 생겨났다.  
`Explicit programming`은 명시적 프로그래밍으로 개발자가 명시적으로 설정해둔 부분만 작동하는 프로그램이다.

`Explicit programming`은  
Spam filter나 Atuomatic driving 등과 같은 프로그램을 작성하는데에 한계가 있다.  
개발자가 굉장히 많은 규칙과 문자를 명시적으로 프로그래밍할 수 없기 때문이다.

따라서 1959년, 'Arthur Samuel'라는 과학자는 '명시적으로 프로그래밍을 해주지 않아도 기계가 데이터를 보고 스스로 학습할 수 있도록' ML을 개발했다.

ML이 학습하는 방법은 아래와 같이 두 가지로 나뉜다.

> - Supervised learning
> - Unsupervised learning

ㅤ

ㅤ

ㅤ

ㅤ

## 2. Learning

### Supervised Learning(지도 학습),

레이블이 있는 입력 데이터를 이용하여 입력과 출력 간의 관계를 학습하는 방식이다.  
즉, `모델에게 정답을 알려주고 학습시키는 방법`으로, 분류(Classification)와 회귀(Regression) 문제를 해결한다.

### Unsupervised Learning(비지도 학습),

레이블이 없는 데이터를 이용하여 `데이터의 숨겨진 구조와 패턴을 학습`하는 방식이다.  
주로 데이터 클러스터링(Clustering), 차원 축소(Dimensionality Reduction), 이상 탐지(Anomaly Detection) 등에 사용된다.

ㅤ
ㅤ

### 장단점

_Supervised learning_

- 정답(label)이 있는 데이터를 사용하여 모델을 학습시키기 때문에, `정확도가 높다.`
- 대규모 데이터셋의 레이블링과 같이 `레이블링의 시간과 비용`이 많이 소요된다.

_Unsupervised learning_

- 정답(label)이 없는 데이터를 사용하여 학습하기 때문에, 데이터 간의 구조와 `패턴을 자유롭게 파악`할 수 있다. 이를 통해 데이터의 숨겨진 특성을 발견하고 이해할 수 있다.
- 정답(label)이 없는 데이터를 사용하여 학습하기 때문에, `모델의 정확도가 떨어진다.`

ㅤ

ㅤ

ㅤ

ㅤ

## 3. Training Learning

모델을 학습시키는 데 사용되는 입력 데이터와 해당 데이터에 대한 정답(label 또는 ground truth)으로 구성된 데이터 세트. `(한마디로 입력과 정답이 있는 데이터 세트)`

아래에서 x가 문제, y가 정답 레이블이라 한다면,
아래의 데이터를 보고 학습한 ML은 10, 20, 30을 보고 0이라는 정답을 출력할 것이다.
|x|y|
|:---:|:---:|
|10, 20, 30|0|
|40, 50, 60|1|

Training Dataset은 모델의 성능과 일반화(generalization) 능력을 결정하는 중요한 요소이기 떄문에, 다양하고 대표적인 데이터로 구성하는 것이 좋다.

ㅤ

ㅤ

ㅤ

ㅤ

## 4. Types of supervised learning

- 분류(Classification):  
  입력 데이터를 미리 정의된 클래스 레이블 중 하나로 할당하는 작업,  
  아래의 데이터를 보고 규칙을 찾아 예측하는 것을 학습하였기에 `classification`모델이 된다.

| x (hour) | y (pass / fail) |
| :------: | :-------------: |
|    10    |        P        |
|    8     |        P        |
|    5     |        F        |
|    4     |        F        |

- 회귀(Regression):  
  연속적인 값이나 숫자를 예측하는 작업,  
  아래의 데이터는 학생들이 공부 시간에 따른 시험 점수를 나타낸다.  
  이 데이터를 학습한 모델을 `Regression`모델이 되어 7시간 공부한 학생은 75점을 받는다는 결과를 도출한다.

| x (hour) | y (score) |
| :------: | :-------: |
|    10    |    90     |
|    9     |    80     |
|    3     |    50     |
|    2     |    30     |

- 다중 레이블 분류(Multi-label Classification):  
  하나의 입력 데이터가 여러 개의 레이블에 속할 수 있는 작업,
