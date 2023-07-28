# lec 05-2

## Contents

- Cost
- Sigmoid problem
- New cost function for logistic
- understanding cost function
- Minimize cost - Gradient decent algorithm
  ㅤ

ㅤ

ㅤ

ㅤ

# Cost

- Hypothesis cost

  ![Alt text](image.png)  
  ![Alt text](image-1.png)  
  ![Alt text](image-2.png)

  제곱 덕분에 매끄럽게 미끄러진다.

- Sigmoid cost

  ![Alt text](image-3.png)  
  ![Alt text](image-1.png)  
  ![Alt text](image-4.png)

ㅤ

ㅤ

ㅤ

ㅤ

# Sigmoid problem

결론부터 말하면 시작점에 따라 끝나는 점이 달라질 수 있기 때문에,  
gradient descent을 사용할 때 Cost를 작게 만드는 W를 찾을 수 없다.

![Alt text](image-5.png)

- local minimum = 한 구간에서의 최솟점
- global minimum = 모든 구간에서의 최솟점

ㅤ

ㅤ

ㅤ

ㅤ

# New cost function for logistic

![Alt text](image-6.png)

cost는 W에 대한 함수로, 모든 값의 합으로 평균을 낸 것이기에  
![Alt text](image-7.png) 부분은 변함이 없다.  
또한 하나의 엘리먼트에 대한 cost를 c함수로 새로 정의된다.

ㅤ

ㅤ
c함수는 두 가지 케이스로 나누어 함수를 정의한다.

- y = 1

  ![Alt text](image-8.png)

- y = 0

  ![Alt text](image-9.png)

ㅤ

ㅤ

ㅤ

ㅤ

# understanding cost function

- y = 1

![Alt text](image-8.png)

H(x) = 1 -> cost(1) = 0  
H(x) = 0 -> cost = 무한

![Alt text](image-18.png)

ㅤ

ㅤ

- y = 0

![Alt text](image-9.png)

H(x) = 0 -> cost(1) = 0  
H(x) = 1 -> cost = 무한

![Alt text](image-17.png)  
<예측이 틀리면 코스트가 굉장히 높아진다.>

ㅤ

ㅤ

위의 두 그래프를 합치면 경사 하강법을 할 수 있는 그래프가 만들어 진다.  
또한, 두 식을 합쳐서 간단하게 만들 수 있다.
![Alt text](image-12.png)

ㅤ

ㅤ

생각보다 간단하다.  
예를 들면,

![Alt text](image-10.png)  
![Alt text](image-11.png)

ㅤ

ㅤ

ㅤ

ㅤ

# Minimize cost - Gradient decent algorithm

위에서 cost를 구했으니 아래와 같이 경사 하강법을 구할 수 있다.

![Alt text](image-15.png)  
![Alt text](image-14.png)  
![Alt text](image-13.png)
