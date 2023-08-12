# lec 12

## Contents

- Sequence data
- RNN (Recurrent Neural Network)
- (vanilla) RNN (Recurrent Neural Network)
- Character-level Language Model
- RNN으로 할 수 있는 것

ㅤ

ㅤ

ㅤ

Neural Network의 꽃이라고 불리는 RNN에 대한 이야기이다.

# Sequence data

`RNN`은 `sequence data`를 처리하는 모델로 음성인식, 자연어 처리 등이 가능하다.  
하지만 자연어의 경우, 앞 뒤 문맥을 이해해야 해석이 가능하다.

지금까지 배운 Neural Network나 Convolutional Neural Network로는 구현할 수 없다.

![Alt text](image.png)

그림으로 표현하면 아래와 같이 나오는데, A에서 나온 화살표가 다시 A로 들어간다.  
이것을 `재진입 (re-enterence) 또는 재귀(recursion)`이라고 부른다.

RNN에서 가장 중요한 것은 상태를 갖는 것으로 그림에서는 h_t로 표현하고있다.
`돌아오는 입력을 X_t라고 표현한다.`

ㅤ

ㅤ

ㅤ

ㅤ

# RNN (Recurrent Neural Network)

RNN은 일반적으로 step을 거칠 때 마다 결과를 예측한다.  
이 예측 값을 y라고 부른다. `(y = Wx + b)`

![Alt text](image-1.png)

공식은 아래와 같이 나오는데,

![Alt text](image-2.png)

코드로 표현하면 이와 같이 나온다.

```py
  for _ in range(노드 갯수):
      현재 상태 = W에 대한 함수(이전 상태, 입력 벡터)
```

ㅤ

ㅤ

ㅤ

ㅤ

# (vanilla) RNN (Recurrent Neural Network)

바닐라 RNN은 가장 단순한 형태의 RNN 모델을 뜻한다.

![Alt text](image-3.png)

> t는 `sequence data`에 대한 특정 시점의 데이터를 가리키고,  
> t에 대해 두 가지를 계산한다.  
> 첫 번째 줄의 공식은 W의 이전 상태와 입력을 갖고 fw에 해당하는 tanh 함수를 호출하는 것이다.  
> h_t는 현재 상태를 의미하고 h의 t-1번째는 이전(old)상태와 입력 값(x)을 사용해서 계산한다.  
> y_t는 예측 값을 의미하고, W와 현재 상태(h_t)를 곱해서 계산한다.

ㅤ

ㅤ

ㅤ

ㅤ

# Character-level Language Model

![Alt text](image-4.png)

글자를 다루는 RNN을 문자 기반의 언어 모델 `Character-level Language Model`이라고 부른다.  
일반적인 `language model`은 단어와 같은, 글자를 예측하는 모델이라고 알려져있다.  
하지만 여기에서는 4가지 종류의 글자 h, e, l, o가 있고, 연속된 `sequence`인 "hello"를 다음 예측값으로 예측한다.

![Alt text](image-5.png)

공식과 같이,  
h 값과 x의 값을 W와 계산한 다음 tanh 함수에 전달하면 hidden layer에서 보여주는 값이 차례대로 만들어 진다.  
이후 hidden lyer의 값이 변하는 것을 알 수 있다.

> tanh 함수는 sigmoid 함수 중의 하나로, 처음 나왔던 sigmoid를 개량한 버전이다.  
> 기존의 sigmoid가 0에서 1 사이의 값을 반환한다면, tanh 함수는 -1에서 1 사이의 값을 반환하도록 개량했다. 현재 상태를 가리키는 h_t는 tanh 함수의 반환값이므로 -1과 1 사이의 값이 된다.  
> 따라서, hidden layer에 있는 값들도 해당 범위에 존재하게 된다.

ㅤ

ㅤ

ㅤ

ㅤ

# RNN으로 할 수 있는 것

![Alt text](image-6.png)

1. one to one (1대1)
2. one to many (1대다)
3. many to one (다대1)
4. many to many (다대다)
5. many to many (다대다)
