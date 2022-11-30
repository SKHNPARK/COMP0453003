# Week13 - 5 Exercises [202011097_박석현]

### 10.4

> 다음과 같은 문장으로 된 lyrics라는 문자열이 있다. 이 문자열을 각 단어별로 구분한 후, 아래 실행 결과와 같이 이 단어와 이 단어에 대한 대문자 튜플 쌍으로 바꾸어 출력하여라.

> (1) lyrics라는 문자열을 split() 메소드로 구분하여 각 단어를 추출한 후 for 문 안에서 각 단어에 대한 upper() 메소드를 적용하여 구현하시오.


```python
lyrics = 'Half of my heart is in Havana'
splited_list = []

for i in lyrics.split():
    tup = (i, i.upper())
    splited_list.append(tup)
print(splited_list)
```

    [('Half', 'HALF'), ('of', 'OF'), ('my', 'MY'), ('heart', 'HEART'), ('is', 'IS'), ('in', 'IN'), ('Havana', 'HAVANA')]
    

> (2) (1)과 동일한 내용을 리스트 축약표현을 사용하여 구현하시오.


```python
lyrics = 'Half of my heart is in Havana'
splited_list = [(i, i.upper()) for i in lyrics.split()]
print(splited_list)
```

    [('Half', 'HALF'), ('of', 'OF'), ('my', 'MY'), ('heart', 'HEART'), ('is', 'IS'), ('in', 'IN'), ('Havana', 'HAVANA')]
    

### 10.5

> 다음과 같은 문장으로 된 lyrics라는 문자열이 있다. 이 문자열을 각 단어별로 구분한 후, 아래 실행 결과와 같이 이 단어와 이 단어의 길이 n에 대한 튜플 쌍으로 바꾸어 출력하여라.

> (1) lyrics라는 문자열을 split() 메소드로 구분하여 각 단어를 추출하여라. 이 리스트를 for 문 안에서 반복하며 각 단어와 len() 함수로 구한 단어의 길이를 튜플 쌍으로 만들어라.


```python
lyrics = 'Half of my heart is in Havana'
splited_list = []

for i in lyrics.split():
    tup = (i, len(i))
    splited_list.append(tup)
print(splited_list)
```

    [('Half', 4), ('of', 2), ('my', 2), ('heart', 5), ('is', 2), ('in', 2), ('Havana', 6)]
    

> (2) (1)과 동일한 내용을 리스트 축약표현을 사용하여 구현하시오.


```python
lyrics = 'Half of my heart is in Havana'
splited_list = [(i, len(i)) for i in lyrics.split()]
print(splited_list)
```

    [('Half', 4), ('of', 2), ('my', 2), ('heart', 5), ('is', 2), ('in', 2), ('Havana', 6)]
    

### 10.6

> 다음과 같이 10개의 정수를 가진 n_list에서 12의 배수를 모두 찾아서 new_list라는 리스트에 저장하여라.

> (1) 이를 위하여 for문과 if조건식을 사용하여 문제를 해결하여라.


```python
n_list = [44, 66, 34, 24, 144, 98, 38, 568, 234, 345]
new_list = []

for n in n_list:
    if n % 12 == 0:
        new_list.append(n)
print(new_list)
```

    [24, 144]
    

> (2) 이를 위하여 filter() 함수와 람다 함수를 사용하여 문제를 해결하여라.


```python
n_list = [44, 66, 34, 24, 144, 98, 38, 568, 234, 345]
new_list = []

for n in filter(lambda x: x % 12 == 0, n_list):
    new_list.append(n)
print(new_list)
```

    [24, 144]
    

> (3) 리스트 축약 표현을 이용하여 위의 문제를 해결하여라.


```python
n_list = [44, 66, 34, 24, 144, 98, 38, 568, 234, 345]
new_list = [n for n in filter(lambda x: x % 12 == 0, n_list)]
print(new_list)
```

    [24, 144]
    

### 10.7

> 다음과 같이 6개의 숫자를 가진 n_list에서 양의 실수 값을 가지는 항목을 추출하여 정수로 변환하여 new_list에 담아서 출력하여라.

> (1) 이를 위하여 for 문과 if 조건식, append() 메소드를 사용하여 문제를 해결하여라.


```python
n_list = [-22.3, 29.44, 902.2, 45.7, -887.1, -56.3]
new_list = []

for n in n_list:
    if n > 0:
        new_list.append(int(n))
print(new_list)
```

    [29, 902, 45]
    

(2) filter() 함수, map() 함수와 람다 함수를 사용하여 문제를 해결하여라.


```python
n_list = [-22.3, 29.44, 902.2, 45.7, -887.1, -56.3]
new_list = []

for n in filter(lambda x: x > 0, n_list):
    new_list.append(n)
new_list = list(map(lambda x: int(x), new_list))
print(new_list)
```

    [29, 902, 45]
    

> (3) 리스트 축약 표현을 이용하여 위의 문제를 해결하여라.


```python
n_list = [-22.3, 29.44, 902.2, 45.7, -887.1, -56.3]
new_list = [int(i) for i in filter(lambda x: x > 0, n_list)]
print(new_list)
```

    [29, 902, 45]
    

### 10.8

> 다음과 같이 6개의 숫자를 가진 n_list에서 최대값과 최소값을 출력하여라.

> (1) 이떄 max()와 min()이라는 파이썬 내장함수를 사용하여라.


```python
n_list = [-22.3, 29.44, 902.2, 45.7, -887.1, -56.3]
print("최대값 :", max(n_list))
print("최소값 :", min(n_list))
```

    최대값 : 902.2
    최소값 : -887.1
    

> (2) max(), min() 이라는 내장함수를 사용하지 말고, my_max(), my_min() 이라는 함수를 직접 구현하여 최대값과 최소값을 출력하여라. 직접 구현한 함수의 내부는 for문과 if문을 이용하여 최대값, 최소값을 찾도록 하여라.


```python
def my_max(numList):
    maxNum = numList[0]
    for num in numList:
        if num > maxNum:
            maxNum = num
    return maxNum

def my_min(numList):
    minNum = numList[0]
    for num in numList:
        if num < minNum:
            minNum = num
    return minNum

n_list = [-22.3, 29.44, 902.2, 45.7, -887.1, -56.3]
print("최대값", my_max(n_list))
print("최소값", my_min(n_list))
```

    최대값 902.2
    최소값 -887.1
    

> (3) reduce() 함수와 조건식을 사용하여 최대값, 최소값을 출력하여라


```python
from functools import reduce

n_list = [-22.3, 29.44, 902.2, 45.7, -887.1, -56.3]
mx = reduce(lambda x, y: max(x, y), n_list)
mn = reduce(lambda x, y: min(x, y), n_list)
print("최대값 :", mx)
print("최소값 :", mn)
```

    최대값 : 902.2
    최소값 : -887.1
    
