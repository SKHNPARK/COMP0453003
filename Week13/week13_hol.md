# Week14 - HOL (2020110973_박석현)

### LAB 10-1 : 일반  함수와 람다 함수의 정의와 호출

> 1. 두 수의 차를 구하여 반환하는 sub라는 이름의 함수를 정의하여 호출하여라. sub(200, 100)을 이용하여 호출하고 그 반환 값을 다음과 깉이 출력하여라.


```python
def sub(x, y):
    return x - y

print("200- 100 =",sub(200, 100))
```

    200- 100 = 100
    

> 2. 1번 문제에서 정의한 sub() 함수를 람다 함수를 이용하여 구현하여라. 그리고 그 반환 값을 다음과 같이 출력하여라.


```python
print("200 - 100 =", (lambda x, y: x - y)(200, 100))
```

    200 - 100 = 100
    

### LAB 10-2 : 람다 함수의 응용

> 1.정수 요소 값을 가진 n_list = [1, 2, 3, 4, 5, 6, 7, 8, 9, 20]라는 리스트가 있다. n_list에서 짝수 값 항목만들 가진 even_list라는 리스트를 람다 함수를 이용하여 아래와 같이 생성해 보자.



```python
def getEven(num):
    if (num % 2 == 0):
        return 1
    return 0

even_list = []
n_list = [1, 2, 3, 4, 5, 6, 7, 8, 9,10]
for n in n_list:
    if (getEven(n)):
        even_list.append(n)
print("even_list =", even_list)

```

    even_list = [2, 4, 6, 8, 10]
    

> 2. 1번 문제에서 사용한 n_list 리스트에 람다 함수를 이용하여 홀수 값 항목만을 가진 다음과 같은 odd_list를 생성해 보자.


```python
n_list = [1, 2, 3, 4, 5, 6, 7, 8, 9,10]

odd_list = []
for n in filter(lambda x: x % 2 == 1, n_list):
    odd_list.append(n)
print("odd_list =", odd_list)
```

    odd_list = [1, 3, 5, 7, 9]
    

### LAB 10-3 : map() 함수의 응용

> 1. ['a', 'b', 'c', 'd']와 같은 영문 소문자가 들어있는 a_list라는 이름의 리스트를 ['A', 'B', 'C', 'D']와 같이 영문 대문자가 들어있는 upper_a_list라는 이름의 리스트로 변환시키는 map() 함수를 작성하여라.

> 1) 이때 소문자를 매개변수로 받아 대문자를 반환하는 to_upper()라는 이름의 함수를 정의하여 변환시키시오.


```python
def to_upper(x):
    return x.upper()

a_list = ['a', 'b', 'c', 'd']
upper_a_list = list(map(to_upper, a_list))
print(upper_a_list)
```

    ['A', 'B', 'C', 'D']
    

> 2) 1)에서 생성한 to_upper() 함수를 lambda 함수로 고쳐서 간결하게 변환시키시오.


```python
a_list = ['a', 'b', 'c', 'd']
upper_a_list = list(map(lambda x: x.upper(), a_list))
print(upper_a_list)
```

    ['A', 'B', 'C', 'D']
    

### LAB 10-4 : reduce() 함수의 응용

> 1. reduce() 함수를 사용하여 1에서 100까지 정수의 합을 구하여라. 이 때 range(1, 101)을 입력으로 사용하여라.


```python
from functools import reduce

a = reduce(lambda x, y: x + y, range(1, 101))
print("1에서 100까지의 합 :", a)
```

    1에서 100까지의 합 : 5050
    

> 2. reduce() 함수를 사용하여 10!을 구하여라. 이 때 range(1, 11)을 입력으로 사용하여라.


```python
from functools import reduce

a = reduce(lambda x, y: x * y, range(1, 11))
print("10! =", a)
```

    10! = 3628800
    

### LAB 10-5 : 리스트의 축약기능

> 1. 리스트 축약기능을 이용하여 1에서 10 사이 정수의 세제곱 값을 가지는 리스트 cubic를 다음과 같이 생성하여라.


```python
cubic = [x**3 for x in range(1, 11)]
print("cubic =", cubic)
```

    cubic = [1, 8, 27, 64, 125, 216, 343, 512, 729, 1000]
    

> 2. 리스트 축약기능을 이용하여 ['welcome', 'to', 'the', 'python', 'world']라는 항목을 가지는 리스트 a로부터 첫 알파벳을 추출한 first_a 리스트를 생성하여라.


```python
a = ['welcome', 'to', 'the', 'python', 'world']
first_a = [x[0].lower() for x in a]
print("first_a =", first_a)
```

    first_a = ['w', 't', 't', 'p', 'w']
    

### LAB 10-6 : 리스트의 축약기능과 조건식

> 1. 리스트 축약기능과 조건식을 사용하여 1에서 10 사이 정수의 세제곱 값 중에서 500 이하인 값만을 가진 cubic  리스트를 다음과 같이 생성하여라.


```python
cubic = [x**3 for x in range(1, 11) if x**3 <= 500]
print("cubic =", cubic)
```

    cubic = [1, 8, 27, 64, 125, 216, 343]
    

> 2. st = 'Hello 1234 Python'라는 문자열이 있다. 리스트 축약기능과 조건식을 사용하여 이 문자열로부터 ['1', '2', '3', '4']를 추출하여 다음과 같이 출력하여라.


```python
st = 'Hello 1234 Python'
st = [x for x in st if x.isdigit()]
print(st)
```

    ['1', '2', '3', '4']
    

### LAB 10-7 : 반복자 객체 만들기

> 1. 짝수를 순차적으로 반환하는 __next__() 메소드를 가진 EvenCounter라는 이름의 클래스를 정의하고 my_even 객체를 생성하여라. 이 객체의 __next__() 메소드를 호출하여 다음과 같이 출력하여라.


```python
class EvenCounter:
    def __init__(self, n=0):
        self.my_even = n

    def __iter__(self):
        return self

    def __next__(self):
        temp = self.my_even
        self.my_even += 2
        return temp


my_even = EvenCounter()
for _ in range(5):
    print(my_even.__next__(), end=' ')
```

    0 2 4 6 8 

> 2. 1번 문제를 통해 생성한 my_even 객체를 이용하여 for 문에서 다음과 같이 20 이하의 짝수를 출력하여라..


```python
class EvenCounter:
    def __init__(self, n=0):
        self.my_even = n

    def __iter__(self):
        return self

    def __next__(self):
        temp = self.my_even
        self.my_even += 2
        return temp


my_even = EvenCounter()
for x in my_even:
    if x > 20:
        break
    print(x, end=' ')

```

    0 2 4 6 8 10 12 14 16 18 20 

### LAB 10-8 : split()과 join()

> 1. 다음 코드의 실행 결과는 무엇인가?


```python
txt = 'Welcome to Busan Metropolitan City.'
print(txt.split())
```

    ['Welcome', 'to', 'Busan', 'Metropolitan', 'City.']
    

> 2. 다음 코드의 실행 결과는 무엇인가?


```python
greet = 'Hello,My name is DongMin,Good to see you agian'
print(greet.split(','))
```

    ['Hello', 'My name is DongMin', 'Good to see you agian']
    

> 3. 다음 코드와 같이 '|'로 구분된 과일의 이름을 가진 fruits 문자열이 있다. 이 문자열을 spllit()을 이용하여 구분하여 ['Apple', 'Banana', 'Melon', 'Orange']와 같은 문자열의 리스트로 만드시오.


```python
fruits = 'Apple|Banana|Melon|Orange'

print(fruits.split('|'))
```

    ['Apple', 'Banana', 'Melon', 'Orange']
    
