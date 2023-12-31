# lec 08

## Contents

- Start and Activation Function
  - Activation Function
- First Problem
  - In 1969
- Problem Solving
  - Back propagation
  - Convolutional Neural Networks
  - A BIG problem
- After this
  - AlexNet

ㅤ

ㅤ

ㅤ

# Deep Learning의 역사

ㅤ

ㅤ

ㅤ

ㅤ

# Start and Activation Function

딥러닝은 인류의 궁극적인 꿈,  
'우리를 대신할 수 있는 기계를 만들자'라는 목표로 우리의 뇌를 공부해서 구현해보자는 의지에서 시작되었다.

ㅤ

ㅤ

사람들은 뇌가 굉장히 복잡하다는 것에 놀라고,  
복잡하게 연결된 부분들을 자세히 보니 뉴런이 너무나 단순하게 동작이 됨에 놀랐다.

ㅤ

ㅤ

앞의 뉴런의 출력값을 입력받아 계산을 거친 후, 똑같이 다음 뉴런에 전달하는 식이였기 때문이다.

![Alt text](image-1.png)

식으로 본다면,
가중치 W와 입력값을 곱하고 편향 b 값을 더한 후, 이를 합산하여 Activation function을 통과시켜 최종 출력값을 다음 뉴런으로 넘겨주는 것이다.

ㅤ

ㅤ
ㅤ

ㅤ

## Activation Function (활성화 함수)

일정 값을 넘기면 다음으로 값을 넘겨준다.  
최종 출력 값은 0과 1이다.

그림으로 보면 아래와 같다. 왼쪽이 우리가 평소에 공부했던 그림이고, 오른쪽이 실제 뉴런을 표현한 형태로 차이가 별로 없어 이해하기 쉬울 것이다.

![Alt text](image.png)

ㅤ

ㅤ

ㅤ

ㅤ

# First Problem

컴퓨터가 AND, OR 문제를 풀 수 있다는 논문과 컴퓨터의 한계를 다룬 논문이 동시에 나오게된다.

AND와 OR의 문제는 아래와 같이 직선을 그어서 풀 수 있지만,

![Alt text](image-2.png)

XOR를 풀 때에는 직선을 긋지 못해 선이 휘면서 정확도가 굉장히 많이 떨어져 모델에게 학습시키기 어렵다는 내용이였다.

![Alt text](image-3.png)

ㅤ

ㅤ
ㅤ

ㅤ

## In 1969

MIT의 한 교수가 책을 냈다.  
XOR은 지금의 기술로는 풀 수 없다고 수학적으로 증명함과 동시에
여러 개로 나누어 합치면 XOR을 해결할 수 있다는 내용이었다.

하지만 큰 문제는 각각의 W, b를 학습시킬 수 없어 불가능할 것이라고 말했다.

> "No one on earth had found a viable way to train"

이 책이 나온 후, 뉴런 연구는 20년 정도 후퇴하게되었다.

ㅤ

ㅤ

ㅤ

ㅤ

# Problem Solving

## Back propagation

![Alt text](image-4.png)

Back propagation은 각각의 W, b를 사용해 출력값을 구한 후,  
예상과 다른 출력일 경우 W, b를 조정하는 것이다.

한마디로 출력 부분에서 error를 구해, 뒤로 전달하여 W, b를 처리하는 것.

> Hinton이 이 방법을 독자적으로 만들어냄 : rediscovery

ㅤ

ㅤ
ㅤ

ㅤ

## Convolutional Neural Networks

라쿤 교수는,  
고양이가 그림을 보게한 후, 시신경의 동작을 확인하고 그림의 형태에 따라 일부 뉴런만 활성화되는 것을 발견했다.

![Alt text](image-5.png)

ㅤ

ㅤ

라쿤 교수의 주장은 다음과 같았다.

> 그림을 볼 때 신경망 세포가 동시에 전체를 보는게 아니라 일부분을 보고 나중에 조합하는 것이 아닐까?

![Alt text](image-6.png)

그림이 있으면 이것을 한번에 다 입력시키는 것이 아니라,  
부분부분 잘라서 레이어에 분류해 나중에 합치는 방법의 Network를 발견해낸 것이다.

> 숫자와 문자를 인식하는데 약 90%이상의 성능을 보였다.

ㅤ

ㅤ
ㅤ

ㅤ

## A BIG problem

하지만 `Back propagation`은 몇몇의 layer를 학습시킬 땐 잘 동작하지만,  
10여개 이상의 layer를 학습시키면 문제가 생긴다.

뒤로 갈 수록 전달되는 에러가 약해져서 에러가 거의 전달되지 않아 뒤 쪽 layer들을 학습시키기가 어려워진 것이다.

따라서 layer가 많아질 수록 성능이 낮아지는 문제가 생겼다.

> 결국 복잡함 때문에 간단한 다른 알고리즘이 성능이 더 좋다는 결론이 나왔다.

ㅤ

ㅤ

ㅤ

ㅤ

# After this

A BIG problem으로 Back propagation과 관련된 연구 속도는 현저히 낮아졌다.

아무도 연구를 하지 않고 이해하려하지 않아 발전이 더딜 때,  
`CIFAR`이라는 단체는 Hinton 교수에게 연구비를 지원해줄테니 연구를 계속 해달라고 말했다.

---

10년 후, 2006/2007년에 한 논문이 나오게된다.

논문은 지금까지 학습할 수 없던 신경망이 알고보니 W의 `초기값`을 잘못 잡았다는 내용이였다.

ㅤ

하지만 Neural networks을 논문 이름으로 낸다면 사람들이 관심을 가지지 않을 것이하 생각해, 이름을 지금의 `Deep learning`으로 바꾸게 된 것이다.

ㅤ

이 때부터 다시 신경망에 관심을 가지게 되면서 사람들이 연구를 하기 시작했다.

ㅤ

가장 주목을 받게된 계기는 `IMAGENET Challenge`이다.  
컴퓨터가 제시된 그림이 무엇인지 맞추는 챌린지이다.  
생각보다 어려운 난이도로 컴퓨터 비전계에서는 굉장히 중요한 문제로 다루고 있었고,  
2010년도에는 약 30%에 가까운 에러율로, 매년 1~2% 감소되고있었다.

ㅤ

ㅤ
ㅤ

ㅤ

## AlexNet

2012년, 모두를 놀라게할만한 결과가 나타났다.  
알렉스라는 박사 과정 학생이 쓴 논문 (AlexNet)에 26.2%의 에러율이 15.3%로 줄어든 것이다.
