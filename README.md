# golbin

# �Ƴ��ܴ� ��ġ

python -m pip install --upgrade pip	// pip ��Ű�� ���׷��̵�
conda create -n tensorflow python=3.6	// �ټ��÷ο츦 ���� �Ƴ��ܴ� ����ȯ�� ����
activate tensorflow // �ټ��÷ο� ���� ȯ������ ����
pip install tensorflow // pip�� �ټ��÷ο� �ٿ�ε�

Anaconda Prompt����
conda create -n tensorflow-cpu python=3.6 anaconda -> y
activate tensorflow-cpu
conda install tensorflow -> y

## �ټ��÷ο찡 ��ġ�Ǿ����� Ȯ���ϴ� ���
python
import tensorflow as tf


import tensorflow as tf
# tf.constant�� ����� hello ������ �����ϴ� �ڵ�
hello = tf.constant('Hello TensorFlow!')
print(hello)

Tensor("Const:0", shape=(), dtype=string) # hello�� �ټ��÷��� �ټ���� �ڷ����̰� ����� ��� �ִ�.

## Rank�� Shape
Tensor �ڷ����� ���� ����
* rank : ������ ��
* Shape : �� ������ ����� ����, �ټ��� ������ ������
```py
3									# rank = 0(scalar), shape = []
[1. ,2. ,3.]						# rank = 1(vector), shape = [3]
[[1. ,2. ,3.], [4. ,5. ,6.]]		# rank = 2(matrix), shape = [2, 3]
[[[1. ,2. ,3.]], [[4. ,5. ,6.]]]	# rank = 3(n-Tensor), shape = [2, 1, 3]
```
## ����

a = tf.constant(10)
b = tf.constant(20)
c = tf.add(a, b)
print(c)			# Tensor("Add:0", shape=(), dtype=int32) -> �ټ��� ���·� ��� -> �ټ��÷� ���α׷��� ������ �и��Ǿ��ֱ� ����

## TensorFlow ���α׷��� ����
1. �׷��� ���� : 
2. �׷��� ���� : Session�ȿ��� �̷����(Session ��ü�� run �޼ҵ� ���)
```py
sess = tf.Session()

print(sess.run(hello))		# b'Hello TensorFlow!'
print(sess.run([a, b, c]))	# [10, 20, 30]

sess.close()
```

�׷��� : �ټ����� ���� ����
��������(lazy evaluation) : �ټ��� �ټ��� ������� ���� ������ �׷����� �����, ���� �ʿ��� �� �����ڵ带 �־� ���ϴ� ������ ���� ���� ����

## placeholder
�׷����� ����� �Է°��� ���߿� �ޱ� ���� ����ϴ� parameter
```py
X = tf.placeholder(tf.float32,[None,3])
print(X)									#Tensor("Placeholder:0", shape=(?, 3), dtype=float32)

```

## ����
�׷����� ����ȭ�ϴ� �뵵�� �ټ��÷�(�н� �Լ�)�� �н��� ����� �����ϱ� ���� ����ϴ� ����
�� �������� ���� �Ű���� ������ �¿���










## ��İ�
* ��İ� A*B : ��� A�� �� ���� ��� B�� �� ���� ���ƾ� ��
* ��İ� A*B�� ����� ��� AB�� ũ��� A�� �� ������ B�� �� ������ �ȴ�.

