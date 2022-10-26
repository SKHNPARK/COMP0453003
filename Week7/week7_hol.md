# Week7 - HOL (2020101973_박석현)

### LAB 7-1 : 오늘의 날짜와 현재시간 출력하기

> 1. datetime 모듈을 사용하여 오늘의 날짜와 시간을 다음과 같이 출력하여라. 이때 hour 같이 10일 경우 오전 10시, 13이면 오후 1시와 같이 오전/오후 정보를 출력하여라.


```python
import datetime

today = datetime.date.today()
time = datetime.datetime.now()
time_hour = time.hour

if time_hour < 12:
    ampm = "오전"
else:
    time_hour -= 12
    ampm = "오후"
print(f"오늘의 날짜 : {today.year}년 {today.month}월 {today.day}일")
print(f"현재시간 : {ampm} {time_hour}시 {time.minute}분 {time.second}초")
```

    오늘의 날짜 : 2022년 10월 13일
    현재시간 : 오후 2시 46분 36초
    

### LAB 7-2 : 남은 날짜 계산하기

> 1. 앞서 배운 남은 날짜 계산 프로그램을 수정하여 오늘 날짜와 함께 2025년 크리스마스까지의 남은 날짜와 시간을 구해서 출력해 보자.


```python
import datetime as dt
today = dt.date.today()
print("오늘은 {}년 {}월 {}일입니다".format(today.year, today.month, today.day))
xMas = dt.datetime(2025, 12, 25)
time_gap = xMas - dt.datetime.now()
print("2025년 크리스마스 까지는 {}일 {}시간 남았습니다".format(time_gap.days, time_gap.seconds // 3600))
```

    오늘은 2022년 10월 13일입니다
    2025년 크리스마스 까지는 1168일 8시간 남았습니다
    

> 2. 앞서 배운 남은 날짜 계산 프로그램을 수정하여 2036년 1월 1일까지의 남은 날짜와 시간을 구해서 출력해 보자.


```python
import datetime as dt
today = dt.date.today()
print("오늘은 {}년 {}월 {}일입니다".format(today.year, today.month, today.day))
nYear = dt.datetime(2036, 1, 1)
time_gap = nYear - dt.datetime.now()
print("2036년 새해 까지는 {}일 {}시간 남았습니다".format(time_gap.days, time_gap.seconds // 3600))
```

    오늘은 2022년 10월 13일입니다
    2036년 새해 까지는 4827일 7시간 남았습니다
    

> 3. 다가오는 자신의 생일까지 남은 날짜와 시간을 출력해 보자.


```python
import datetime as dt
today = dt.date.today()
print("오늘은 {}년 {}월 {}일입니다".format(today.year, today.month, today.day))
bDay = dt.datetime(2023, 1, 25)
time_gap = bDay - dt.datetime.now()
print("다가오는 생일 까지는 {}일 {}시간 남았습니다".format(time_gap.days, time_gap.seconds // 3600))
```

    오늘은 2022년 10월 13일입니다
    다가오는 생일 까지는 103일 7시간 남았습니다
    

### LAB 7-3 : 날짜 계산하기

> 1. timedelta 클래스를 사용하여 오늘 날짜로부터 1,000일 후의 날짜를 구하시오.


```python
import datetime as dt

today = dt.datetime.today()
k = today + dt.timedelta(days=1000)
print("1000일 후의 날짜 : {}년 {}월 {}일".format(k.year, k.month, k.day))
```

    1000일 후의 날짜 : 2025년 7월 9일
    

> 2. timedelta 클래스를 이용하여 커플들을 위한 프로그램을 작성하자. 다음과 같이 처음으로 사귄 연도와 월, 일을 띄어쓰기로 입력하면 100일 기념일을 출력하는 기능이 있다. 프로그램의 이름은 couple_day.py라고 정하도록 하자.


```python
import datetime as dt

year, month, day = map(int, input("처음으로 사귄 연도와 월, 일을 입력하시오 : ").split())
first_date = dt.datetime(year, month, day)
hundred = first_date + dt.timedelta(days=100)
print("100일 기념일은 : {}년 {}월 {}일입니다.".format(hundred.year, hundred.month, hundred.day - 1))
```

    처음으로 사귄 연도와 월, 일을 입력하시오 : 2019 3 30
    100일 기념일은 : 2019년 7월 7일입니다.
    

### LAB 7-4 : math 모듈을 이용한 계산

> 1. math 모듈과 for - in range()를 사용하여 4의 2승부터 10승까지를 화면에 출력하여라.


```python
import math

for i in range(2, 11):
    print("4**{:2d} = {:9.1f}".format(i, math.pow(4, i)))
```

    4** 2 =      16.0
    4** 3 =      64.0
    4** 4 =     256.0
    4** 5 =    1024.0
    4** 6 =    4096.0
    4** 7 =   16384.0
    4** 8 =   65536.0
    4** 9 =  262144.0
    4**10 = 1048576.0
    

> 2. 일반각도 0도에서 180도를 10도 단위로 출력하라. 이때 이 일반각도에 대응되는 라디안 각도 값을 함께 출력하라.


```python
import math

for i in range(0, 181,10):
    print("{:3d} degree = {:.3f} radian".format(i, math.radians(i)))
```

      0 degree = 0.000 radian
     10 degree = 0.175 radian
     20 degree = 0.349 radian
     30 degree = 0.524 radian
     40 degree = 0.698 radian
     50 degree = 0.873 radian
     60 degree = 1.047 radian
     70 degree = 1.222 radian
     80 degree = 1.396 radian
     90 degree = 1.571 radian
    100 degree = 1.745 radian
    110 degree = 1.920 radian
    120 degree = 2.094 radian
    130 degree = 2.269 radian
    140 degree = 2.443 radian
    150 degree = 2.618 radian
    160 degree = 2.793 radian
    170 degree = 2.967 radian
    180 degree = 3.142 radian
    

> 3. math 모듈과 for 문을 사용하여 일반각도 sin 0도에서 부터 180도까지의 값을 10도 간격으로 출력하여라.


```python
import math

for i in range(0, 181,10):
    print("{:3d} degree = {:.2f} radian".format(i, math.sin(math.radians(i))))
```

      0 degree = 0.00 radian
     10 degree = 0.17 radian
     20 degree = 0.34 radian
     30 degree = 0.50 radian
     40 degree = 0.64 radian
     50 degree = 0.77 radian
     60 degree = 0.87 radian
     70 degree = 0.94 radian
     80 degree = 0.98 radian
     90 degree = 1.00 radian
    100 degree = 0.98 radian
    110 degree = 0.94 radian
    120 degree = 0.87 radian
    130 degree = 0.77 radian
    140 degree = 0.64 radian
    150 degree = 0.50 radian
    160 degree = 0.34 radian
    170 degree = 0.17 radian
    180 degree = 0.00 radian
    

### LAB 7-5 : 랜덤 번호 생성기

> 1.random 모듈의 randrange() 함수를 이용하여 0에서 100 이하의 정수 중에서 5의 배수 값을 임의로 3개 선택하여 리스트 형식으로 출력해 보시오.


```python
import random as rd

myList = []

while len(myList) < 3:
    randNum = rd.randrange(0, 101)
    if randNum % 5 == 0 and randNum not in myList:
        myList.append(randNum)
print("0에서 100 이하의 정수 중에서 5의 배수")
print(myList)
```

    0에서 100 이하의 정수 중에서 5의 배수
    [100, 75, 40]
    

> 2. 1에서 10 사이의 정수 중 임의의 정수 3개를 sample() 함수를 이용하여 출력하시오.


```python
import random as rd

myList = list(range(1, 11))
print("1에서 10 사이의 임의의 정수 :", rd.sample(myList, 3))
```

    1에서 10 사이의 임의의 정수 : [3, 4, 9]
    
