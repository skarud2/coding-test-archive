# 내장 함수

import 없이 사용

## 문자열을 숫자로 바꾸기

### int() - 정수로 변환

```python
s = "-1234"
num = int(s)

print(num)        # -1234
print(type(num))  # <class 'int'>
```

문자열 앞에 +, - 부호가 있어도 변환됨

### float() - 실수로 변환

```python
s = "3.14"
num = float(s)

print(num)        # 3.14
print(type(num))  # <class 'float'>
```

### 주의

```python
int("3.14")  # ValueError
float("abc")  # ValueError
```

int()에 소수점이 있는 문자열을 바로 넣으면 오류
숫자로 바꿀 수 없는 문자열도 오류

## str() - 문자열로 변환

```python
num = 123
s = str(num)

print(s)        # 123
print(type(s))  # <class 'str'>
```

숫자를 문자열과 +로 연결할 때 사용
표현할 문자열 안에 숫자를 넣을 때는 [f-string](string.md)으로도 가능
