# golbin

# 아나콘다 설치

python -m pip install --upgrade pip	// pip 패키지 업그레이드
conda create -n tensorflow python=3.6	// 텐서플로우를 위한 아나콘다 가상환경 구축
activate tensorflow // 텐서플로우 가상 환경으로 진입
pip install tensorflow // pip로 텐서플로우 다운로드

Anaconda Prompt에서
conda create -n tensorflow-cpu python=3.6 anaconda -> y
activate tensorflow-cpu
conda install tensorflow -> y

## 텐서플로우가 설치되었는지 확인하는 방법
python
import tensorflow as tf


import tensorflow as tf
# tf.constant로 상수를 hello 변수에 저장하는 코드
hello = tf.constant('Hello TensorFlow!')
print(hello)

Tensor("Const:0", shape=(), dtype=string) # hello가 텐서플로의 텐서라는 자료형이고 상수를 담고 있다.

## Rank와 Shape
Tensor 자료형이 갖는 개념
* rank : 차원의 수
* Shape : 각 차원의 요소의 개수, 텐서의 구조를 설명함
```py
3									# rank = 0(scalar), shape = []
[1. ,2. ,3.]						# rank = 1(vector), shape = [3]
[[1. ,2. ,3.], [4. ,5. ,6.]]		# rank = 2(matrix), shape = [2, 3]
[[[1. ,2. ,3.]], [[4. ,5. ,6.]]]	# rank = 3(n-Tensor), shape = [2, 1, 3]
```
## 덧셈

a = tf.constant(10)
b = tf.constant(20)
c = tf.add(a, b)
print(c)			# Tensor("Add:0", shape=(), dtype=int32) -> 텐서의 형태로 출력 -> 텐서플로 프로그램의 구조가 분리되어있기 때문

## TensorFlow 프로그램의 구조
1. 그래프 생성 : 
2. 그래프 실행 : Session안에서 이루어짐(Session 객체와 run 메소드 사용)
```py
sess = tf.Session()

print(sess.run(hello))		# b'Hello TensorFlow!'
print(sess.run([a, b, c]))	# [10, 20, 30]

sess.close()
```

그래프 : 텐서들의 연산 모음
지연실행(lazy evaluation) : 텐서와 텐서의 연산들을 먼저 정의해 그래프를 만들고, 이후 필요할 때 실행코드를 넣어 원하는 시정에 실제 연상 수행

## placeholder
그래프에 사용할 입력값을 나중에 받기 위해 사용하는 parameter
```py
X = tf.placeholder(tf.float32,[None,3])
print(X)									#Tensor("Placeholder:0", shape=(?, 3), dtype=float32)

```

## 변수
그래프를 최적화하는 용도로 텐서플로(학습 함수)가 학습한 결과를 갱신하기 위해 사용하는 변수
이 변수들의 값이 신경망의 성능을 좌우함










## 행렬곱
* 행렬곱 A*B : 행렬 A의 열 수와 행렬 B의 행 수는 같아야 함
* 행렬곱 A*B를 계산한 행렬 AB의 크기는 A의 행 개수와 B의 열 개수가 된다.

