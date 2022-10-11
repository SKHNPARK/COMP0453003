# Week 6 - HOL (2020110973_박석현)

### LAB 4-1 : 함수 정의와 호출

> 1. [코드 4-1]의 함수 호출문을 삭제하면 어떻게 되는가?

아무일도 일어나지 않는다.

> 2. [코드 4-2]를 수정하여 6줄의 별표를 출력해 보시오. 이때 함수 호출을 6회 하시오.


```python
def print_star():
    print("************************")
print_star()
print_star()
print_star()
print_star()
print_star()
print_star()
```

    ************************
    ************************
    ************************
    ************************
    ************************
    ************************
    

### LAB 4-2 : 함수 정의와 호출

> 1. [코드 4- 3]을 수정하여 함수 호출 두 번으로 10줄의 별표를 출력해 보시오.


```python
def print_star3():
    print("************************")
    print("************************")
    print("************************")
    print("************************")
    print("************************")
print_star3()
print_star3()
```

    ************************
    ************************
    ************************
    ************************
    ************************
    ************************
    ************************
    ************************
    ************************
    ************************
    

### LAB 4-3 : 함수 정의와 호출

> 1. [코드 4-4]를 수정하여 해시마크(#)를 한 줄 출력하는 print_hash() 함수를 추가로 구현하시오.


```python
def print_hash():
    print("########################")
```


```python
def print_plus():
    print("++++++++++++++++++++++++")
print_hash()
print_star()
print_plus()
print_plus()
print_star()
print_hash()
```

    ########################
    ************************
    ++++++++++++++++++++++++
    ++++++++++++++++++++++++
    ************************
    ########################
    

### LAB 4-4 : 다양한 별표와 패턴 출력

> 1. [코드 4-5]를 수정하여 별표(\*)줄이 10개 출력되도록 인자를 변경하시오


```python
def print_star(n):
    for _ in range(n):
        print("************************")
print_star(10)
```

    ************************
    ************************
    ************************
    ************************
    ************************
    ************************
    ************************
    ************************
    ************************
    ************************
    

> 2. [코드 4-5]를 수정하여 별표(\*) 대신 해시마크(#)가 출력되도록 하시오. 이를 위해 함수 이름을 print_hash(n)으로 수정하고 수정된 함수를 print_hash(10)과 같이 호출하시오.


```python
def print_hash(n):
    for _ in range(n):
        print("########################")
print_hash(10)
```

    ########################
    ########################
    ########################
    ########################
    ########################
    ########################
    ########################
    ########################
    ########################
    ########################
    

> 3. print_hash(6)을 호출하여 다음과 같은 출력이 나타나도록 하여라.


```python
print_hash(6)
```

    ########################
    ########################
    ########################
    ########################
    ########################
    ########################
    

> 4. print_hash(6)을 호출하여 다음과 같은 출력이 나타나도록 하여라. 다음 화면과 같이 매번 해시가 출력될 때마다 앞 칸에 줄 번호를 0부터 표시하도록 하여라.


```python
def print_hash(n):
    for i in range(n):
        print(i, "########################")
print_hash(6)
```

    0 ########################
    1 ########################
    2 ########################
    3 ########################
    4 ########################
    5 ########################
    

### LAB 4-5 : 두 수 연산을 수행하는 함수

> 1. 두 개의 매개변수 a, b를 받아서 두 수의 차를 구하여 출력하는 print_sub(a, b) 함수를 구현하여라. print_sum(10, 20)을 호출한 결과 다음과 같은 출력이 나타나도록 하여라.


```python
def print_sub(a, b):
    print(f"{a}과 {b}의 차는 {a - b}입니다.")
print_sub(10, 20)
```

    10과 20의 차는 -10입니다.
    


```python
def print_mult(a, b):
    print(f"{a}과 {b}의 곱은 {a * b}입니다.")
print_mult(10, 20)
```

    10과 20의 곱은 200입니다.
    

### LAB 4-6 : 함수의 사용

> 1. 다음 2차 방정식의 근을 [코드 4-10]의 함수를 사용하여 출력하여라.   
(1) x^2 + 4x - 21 = 0   
(2) x^2 - 6x + 8 = 0


```python
def print_root(a, b, c):
    r1 = (-b + (b ** 2 - 4 * a * c) ** 0.5) / (2 * a)
    r2 = (-b - (b ** 2 - 4 * a * c) ** 0.5) / (2 * a)
    print("해는", r1, "또는", r2)
print_root(1, 4, -21)
print_root(1, -6, 8)
```

    해는 3.0 또는 -7.0
    해는 4.0 또는 2.0
    

> 2. 삼각형의 면적을 구하기 위하여 밑변과 높이를 사용하려고 한다. 두 개의 매개변수 width, height를 받아서 삼각형의 면적을 출력하는 함수 print_area(width, height)를 구현하여라. 이때 print_area(10, 20)을 호출하여 다음과 같은 출력이 나타나도록 하여라.


```python
def print_area(width, height):
    print(f"밑변 {width}, 높이 {height}인 삼각형의 면적은 : {width * height}")
print_area(10, 20)
```

    밑변 10, 높이 20인 삼각형의 면적은 : 200
    

### LAB 4-7 : 원의 면적과 둘레를 반환하는 함수

> 1. 원의 면적과 둘레를 구하기 위하여 원의 반지름을 사용하려고 한다. 이 때 사용할 circle_area_circum(radius) 함수는 다음과 같이 반지름(radius) 10을 입력으로 받아서 면적(area)과 둘레(circum)의 두 값을 반환하도록 구현하여라.


```python
def circle_area_circum(radius):
    area = radius * radius * 3.14
    circum = radius * 2 * 3.14
    return area, circum
area, circum = circle_area_circum(10)
print(f"반지름 10인 원의 면적은 {area}, 원의 둘레는 {circum}")
```

    반지름 10인 원의 면적은 314.0, 원의 둘레는 62.800000000000004
    

### LAB 4-8 : 다수의 결과를 반환하는 함수 만들기

> 1. 어떤 정수 n과 m을 입력하면, n의 배수 m개를 반환하는 multiplies(n, m) 함수를 구현하고 다음과 같이 호출하여 결과를 출력하여라.


```python
def multiples(n, m):
    ret = []
    for i in range(1, m + 1):
        ret.append(n * i)
    return tuple(ret)
r1, r2, r3, r4 = multiples(3, 4)
print(r1, r2, r3, r4)
r1, r2, r3, r4, r5 = multiples(2, 5)
print(r1, r2, r3, r4, r5)
```

    3 6 9 12
    2 4 6 8 10
    

### LAB 4-9 : 키워드 인자

>1. 다음과 같이 성(last name)과 이름(first name), 존칭(honorficis)을 매개변수로 받아서 출력하는 함수 print_name이 있다.


```python
def print_name(honorifics, first_name, last_name):
    print(honorifics, first_name, last_name)
print_name(first_name='Gildong', last_name='Hong', honorifics='Dr.')
print_name('Gildong', 'Hong', 'Dr.')
```

    Dr. Gildong Hong
    Gildong Hong Dr.
    

### LAB 4-10 : 가변 인자의 활용

> 1. 가변 인자를 사용하는 sum_nums() 함수를 수정하여 인자들을 튜플 형식으로 출력한 후 모든 값들의 합과 평균을 다음과 같이 출력하시오.


```python
def sum_nums(*numbers):
    sum_total = 0
    avg = 0
    for number in numbers:
        sum_total += number
        avg = sum_total / len(numbers)
    print(f"합계 : {sum_total}, 평균 : {avg}")

sum_nums(10, 20, 30)
```

    합계 : 60, 평균 : 20.0
    

    > 2. 가변 인자를 사용하는 함수 min_nums() 함수를 구현하시오. 이 함수는 정수를 인자로 받을 수 있는데 이 인자의 개수가 가변적이다. 이 함수의 호출문이 다음과 같을 경우 다음과 같은 출력이 나타나도록 하시오.


```python
def min_nums(*numbers):
    myList = []
    for number in numbers:
        myList.append(number)
    myMin = min(myList)
    print(f"최솟값은 {myMin}")
min_nums(20, 40, 50, 10)
```

    최솟값은 10
    

### LAB 4-11 : format() 메소드의 활용

> 1. 위의 코드를 수정하여 이름, 나이, 직업, 사는 곳 까지 다음과 같이 화면에 출력하려고 한다.   
a) 출력문에서 format() 메소드를 사용하여 출력하여라.   
b) 출력문에서 format() 메소드를 사용하지 말고 쉼표로 구분하여 출력하여라.


```python
name = str(input("당신의 이름을 입력해주세요 : "))
age = int(input("나이를 입력해주세요 : "))
job = str(input("직업을 입력해주세요 : "))
location = str(input("사는 곳을 입력해 주세요 : "))
print("당신의 이름은 {}, 나이는 {}, 직업은 {}, 사는 곳은 {}입니다.".format(name, age, job, location))
```

    당신의 이름을 입력해주세요 : 김철수
    나이를 입력해주세요 : 21
    직업을 입력해주세요 : 학생
    사는 곳을 입력해 주세요 : 창원시
    당신의 이름은 김철수, 나이는 21, 직업은 학생, 사는 곳은 창원시입니다.
    


```python
name = str(input("당신의 이름을 입력해주세요 : "))
age = int(input("나이를 입력해주세요 : "))
job = str(input("직업을 입력해주세요 : "))
location = str(input("사는 곳을 입력해 주세요 : "))
print("당신의 이름은", name, "나이는", age, "직업은", job, "사는 곳은", location, "입니다.")
```

    당신의 이름을 입력해주세요 : 김철수
    나이를 입력해주세요 : 21
    직업을 입력해주세요 : 학생
    사는 곳을 입력해 주세요 : 창원시
    당신의 이름은 김철수 나이는 21 직업은 학생 사는 곳은 창원시 입니다.
    

### LAB 4-12 : 문자열의 여러 메소드 활용

> 1. join() 메소드를 사용하여 'ABCD'의 문자열을 'A_B_C_D'와 같이 출력하여라.


```python
print('_'.join("ABCD"))
```

    A_B_C_D
    

> 2. 'My favorite thing is monsters.'라는 문자열 s에 replace() 메소드를 적용하여 'My favorite thing is cartoons.'로 수정된 t 문자열을 얻도록 하여라.


```python
s = 'My favorite thing is monsters.'
t = s.replace('monsters', 'cartoons')
print(t)
```

    My favorite thing is cartoons.
    


```python

```
