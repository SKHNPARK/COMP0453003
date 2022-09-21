# Week3 - Exercise (2020110973_박석현)

> 1. 다음과 같이 사용자로부터 3개의 임의의 정수를 입력으로 받아서 가장 작은 수부터 큰 수까지 나열하는 프로그램을 if-else 문을 사용하여 작성하시오.
![image.png](attachment:image.png)


```python
a, b, c = map(int, input("세 정수를 입력하시오 : ").split())
if a > b:
    a, b = b, a
if b > c:
    b, c = c, b
if a > b:
    a, b = b, a
else:
    print("Error")
print(a, b, c)
```

    세 정수를 입력하시오 : 9 12 4
    4 9 12
    


```python
a, b, c = map(int, input("세 정수를 입력하시오 : ").split())
if a > b:
    a, b = b, a
if b > c:
    b, c = c, b
if a > b:
    a, b = b, a
else:
    print("Error")
print(a, b, c)
```

    세 정수를 입력하시오 : 99 12 4
    4 12 99
    

> 2. 사용자로부터 x, y 좌표를 가진 한 점을 입력으로 받아서 이 점이 1, 2, 3, 4 분면의 어디에 속하는지를 알려주는 프로그램을 작성하시오.


```python
x, y = map(int, input("점의 좌표 x, y를 입력하시오 : ").split())

if x > 0 and y > 0:
    print("1사분면에 있음")
elif x < 0 and y > 0:
    print("2사분면에 있음")
elif x < 0 and y < 0:
    print("3사분면에 있음")
else:
    print("4사분면에 있음")
```

    점의 좌표 x, y를 입력하시오 : 2 4
    1사분면에 있음
    


```python
x, y = map(int, input("점의 좌표 x, y를 입력하시오 : ").split())

if x > 0 and y > 0:
    print("1사분면에 있음")
elif x < 0 and y > 0:
    print("2사분면에 있음")
elif x < 0 and y < 0:
    print("3사분면에 있음")
else:
    print("4사분면에 있음")
```

    점의 좌표 x, y를 입력하시오 : -2 -4
    3사분면에 있음
    

> 3. 사용자로부터 점수를 입력받은 다음 게임 사용자의 게임점수(game_score)가 1000점 이상이면 ‘고수입니다.’를 출력하고 1000점 미만이면 ‘입문자입니다.’를 출력하는 프로그램을 if-else문을 이용하여 작성하시오. 
 ![image.png](attachment:image.png) ![image-2.png](attachment:image-2.png)


```python
score = int(input("게임점수를 입력하시오 : "))
if score >= 1000:
    print("고수입니다")
else:
    print("입문자입니다.")
```

    게임점수를 입력하시오 : 4222
    고수입니다
    


```python
score = int(input("게임점수를 입력하시오 : "))
if score >= 1000:
    print("고수입니다")
else:
    print("입문자입니다.")
```

    게임점수를 입력하시오 : 4
    입문자입니다.
    

> 4. 다음의 프로그램은 어떤 결과 값을 출력하는가? 출력결과를 미리 예측한 후 타이핑하여 그 결과가 맞는지 확인해 보도록 하자.
![image.png](attachment:image.png) ![image-2.png](attachment:image-2.png)

![image.png](attachment:image.png)


```python
for i in range(3):
    print('Python ')
    print('is ')
    print('FUN! ')
```

    Python 
    is 
    FUN! 
    Python 
    is 
    FUN! 
    Python 
    is 
    FUN! 
    

![image.png](attachment:image.png)


```python
for i in range(3):
    print('Python ')
    print('is ')
print('FUN! ')
```

    Python 
    is 
    Python 
    is 
    Python 
    is 
    FUN! 
    

> 5. 소수란 양의 자연수 중에서 1과 자기 자신이외의 약수를 가지지 않는 수를 말한다. 사용자로부터 양의 정수 n을 입력받은 후 이 숫자가 소수인지 아닌지를 판별하는 프로그램을 작성하시오. 이때 수행 속도를 개선하기 위하여 2로 나누어 본 후 나누어지지 않을 경우 3, 5, 7, … 과 같은 홀수로 나눗셈을 시도하도록 코딩하여라.   
힌트: n을 2부터 n-1까지의 정수로 모두 나누어 본다. 이 때 나누어 떨어지는 원소가 하나라도 있으면 소수가 아니다.
![image.png](attachment:image.png)


```python
stdin = int(input("숫자를 입력하세요 : "))

check = 1
odd = 3
for _ in range(stdin):
    if odd >= stdin:
        break
    if stdin % 2 == 0:
        check = 0
        break
    elif stdin % odd == 0:
        check = 0
        break
    odd += 2
if check:
    print(stdin, "은 소수입니다.")
else:
    print(stdin, "은 소수가 아닙니다.")
```

    숫자를 입력하세요 : 5
    5 은 소수입니다.
    


```python
stdin = int(input("숫자를 입력하세요 : "))

check = 1
odd = 3
for _ in range(stdin):
    if odd >= stdin:
        break
    if stdin % 2 == 0:
        check = 0
        break
    elif stdin % odd == 0:
        check = 0
        break
    odd += 2
if check:
    print(stdin, "은 소수입니다.")
else:
    print(stdin, "은 소수가 아닙니다.")
```

    숫자를 입력하세요 : 9
    9 은 소수가 아닙니다.
    

> 6. 암스트롱 수란 세 자리의 정수 중에서 각 자리의 수를 세제곱한 수의 합과 자신이 같은 수를 말한다. 구체적인 예를 들면 153은 1 + 125 + 27 의 합으로 구성될 수 있는데 이러한 수가 암스트롱 수이다. 세 자리 정수들 중에서 모든 암스트롱 수를 구하여 다음과 같이 출력하여라.
![image.png](attachment:image.png)


```python
for i in range(100, 1000):
    hundred = i // 100
    ten = i // 10 % 10
    one = i % 10
    if (hundred**3 + ten**3 + one**3) == i:
        print(i, end=" ")
```

    153 370 371 407 

> 7. 다음과 같이 사용자로부터 1에서 9사이의 숫자를 입력받아 입력받은 숫자의 절에 해당하는 구구단을 출력하는 프로그램을 for문과 while 문을 사용하여 작성하여라. 만일 1에서 9 이외의 숫자가 입력되면 ‘1에서 9까지의 수를 다시 입력하세요’라는 안내문을 출력하여라.
![image.png](attachment:image.png)


```python
a = int(input("1에서 9까지의 수를 입력하세요 : "))

while True:
    if a >=1 and a <= 9:
        for i in range(1, 10):
            print(a, "*", i, "=", a * i)
        break
    else:
        a = int(input("1에서 9까지의 수를 다시 입력하세요 : "))
```

    1에서 9까지의 수를 입력하세요 : 11
    1에서 9까지의 수를 다시 입력하세요 : 134
    1에서 9까지의 수를 다시 입력하세요 : 2
    2 * 1 = 2
    2 * 2 = 4
    2 * 3 = 6
    2 * 4 = 8
    2 * 5 = 10
    2 * 6 = 12
    2 * 7 = 14
    2 * 8 = 16
    2 * 9 = 18
    

> 8. 맛나 식당의 메뉴 주문 프로그램을 개발하고자 한다. 이를 위해 사용자에게 다음과 같은 메뉴를 보여주고 이중에서 메뉴에 대응되는 하나의 알파벳을 선택하도록 하자. 이때 메뉴에 없는 알파벳이 입력되면 ‘메뉴를 다시 입력하세요:  ’가 출력되도록 한 후 다시 입력을 받도록 하자.
![image.png](attachment:image.png)


```python
print("맛나 식당에 오신 것을 환영합니다. 메뉴는 다음과 같습니다.")
print("- 삼겹구이 (입력 s)\n- 오삼불고기 (입력 o)\n- 된장찌개 (입력 d)")
while True:
    stdin = str(input("메뉴를 선택하세요(알파벳 s, o, d 입력) : "))
    s = "삼겹구이"
    o = "오삼불고기"
    d = "된장찌개"
    if stdin == "s":
        print("삼겹구이를 선택하였습니다.")
        break
    elif stdin == "o":
        print("오삼불고기를 선택하였습니다.")
        break
    elif stdin == "d":
        print("된장찌개를 선택하였습니다.")
        break
    else:
        print("메뉴를 다시 입력하세요.")
```

    맛나 식당에 오신 것을 환영합니다. 메뉴는 다음과 같습니다.
    - 삼겹구이 (입력 s)
    - 오삼불고기 (입력 o)
    - 된장찌개 (입력 d)
    메뉴를 선택하세요(알파벳 s, o, d 입력) : o
    오삼불고기를 선택하였습니다.
    

> 9. 이중 for 문을 사용하여 숫자를 입력 받아 다음과 같은 삼각형을 출력하는 프로그램을 작성하시오. 이때 아래 결과와 같이 숫자 10이 입력되면 높이가 10이고 제일 마지막 줄의 별이 10개가 삼각형 형태로 나타나도록 하시오.   
힌트: 첫번째줄은 공백 9개, 별1개 / 마지막줄은 공백이 없다.
![image.png](attachment:image.png)


```python
stdin = int(input("숫자를 입력하세요 : "))

for i in range(1, stdin + 1):
    for j in range(stdin - i, 0, -1):
        print(" ", end="")
    print("*" * i)
```

    숫자를 입력하세요 : 10
             *
            **
           ***
          ****
         *****
        ******
       *******
      ********
     *********
    **********
    

> 10.사용자로부터 숫자 1보다 크고 10보다 작은 값 n을 입력으로 받아서 다음과 같이 뱀의 몸통처럼 증가하는 이차원 배열을 출력하여라. (이 배열은 마치 뱀의 몸통처럼 'ㄹ’과 같은 패턴을 그리며 수가 1씩 증가하는 형태의 배열이다.)
![image.png](attachment:image.png)
![image-2.png](attachment:image-2.png)


```python
n = int(input("n을 입력하시오 : "))
arr = [[0 for i in range(n)] for j in range(n)]

num = 1
for i in range(n):
    if i % 2:
        for j in range(n - 1, -1, -1):
            arr[i][j] = num
            num += 1
    else:
        for j in range(n):
            arr[i][j] = num
            num += 1

for i in range(n):
    for j in range(n):
        print("%-3d" % arr[i][j], end=" ")
    print("\n")
```

    n을 입력하시오 : 5
    1   2   3   4   5   
    
    10  9   8   7   6   
    
    11  12  13  14  15  
    
    20  19  18  17  16  
    
    21  22  23  24  25  
    
    


```python
n = int(input("n을 입력하시오 : "))
arr = [[0 for i in range(n)] for j in range(n)]

num = 1
for i in range(n):
    if i % 2:
        for j in range(n - 1, -1, -1):
            arr[i][j] = num
            num += 1
    else:
        for j in range(n):
            arr[i][j] = num
            num += 1

for i in range(n):
    for j in range(n):
        print("%-3d" % arr[i][j], end=" ")
    print("\n")
```

    n을 입력하시오 : 7
    1   2   3   4   5   6   7   
    
    14  13  12  11  10  9   8   
    
    15  16  17  18  19  20  21  
    
    28  27  26  25  24  23  22  
    
    29  30  31  32  33  34  35  
    
    42  41  40  39  38  37  36  
    
    43  44  45  46  47  48  49  
    
    


```python

```
