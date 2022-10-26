# Week8 - HOL (2020110973_박석현

### LAB 8-1 : 다음 코드는 어떤 예외를 발생시키는가?

> 1. 다음 코드는 각각 어떤 예외를 발생시키는가?


```python
a = [10, 20, 30]
print(a[3])
```


    ---------------------------------------------------------------------------

    IndexError                                Traceback (most recent call last)

    Input In [1], in <cell line: 2>()
          1 a = [10, 20, 30]
    ----> 2 print(a[3])
    

    IndexError: list index out of range



```python
n = int('20%')
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    Input In [2], in <cell line: 1>()
    ----> 1 n = int('20%')
    

    ValueError: invalid literal for int() with base 10: '20%'



```python
a = 100 + '200'
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    Input In [3], in <cell line: 1>()
    ----> 1 a = 100 + '200'
    

    TypeError: unsupported operand type(s) for +: 'int' and 'str'



```python
try:
    a = [10, 20, 30]
    print(a[3])
except Exception as e:
    print("error :", e)
    
try:
    n = int('20%')
except Exception as e:
    print("error :", e)
    
try:
    a = 100 + '200'
except Exception as e:
    print("error :", e)
```

    error : list index out of range
    error : invalid literal for int() with base 10: '20%'
    error : unsupported operand type(s) for +: 'int' and 'str'
    

### LAB 8-2 : 다음 코드는 어떤 예외를 발생시키는가?

> 1. 다음 코드가 있을 경우 이 코드에 적합한 예외 처리문을 만드시오.


```python
try:
    10 * (30 / 0)
except ZeroDivisionError:
    print("오류: 0으로 나눔을 시도했습니다.")

try:
    x = int(input("정수 x를 입력하세요: "))
except ValueError:
    print("오류: 입력 값이 정수나 실수가 아닙니다.")

try:
    f = open("myfile.txt")
    s = f.readline()
except:
    print("오류: 파일을 열 수 없습니다.")
```

    오류: 0으로 나눔을 시도했습니다.
    정수 x를 입력하세요: 일
    오류: 입력 값이 정수나 실수가 아닙니다.
    오류: 파일을 열 수 없습니다.
    

### LAB 8-3 : 예외의 생성과 처리

> 1. [1, 2, 3, 4, 5]의 다섯개의 요소를 가진 리스트 a가 있을 때 다음과 같이 사용자로 부터 정수를 입력 받은 후 이에 해당하는 인덱스를 출력하도록 하자.


```python
a = [1, 2, 3, 4, 5]
b = int(input("a의 요소를 하나 선택하시오 : "))
if b == 1:
    print("1 은(는) 첫 번째 요소입니다.")
elif b == 2:
    print("2 은(는) 두 번째 요소입니다.")
elif b == 3:
    print("3 은(는) 두 번째 요소입니다.")
elif b == 4:
    print("4 은(는) 두 번째 요소입니다.")
elif b == 5:
    print("5 은(는) 두 번째 요소입니다.")
```

    a의 요소를 하나 선택하시오 : 2
    2 은(는) 두 번째 요소입니다.
    


```python
a = [1, 2, 3, 4, 5]
b = int(input("a의 요소를 하나 선택하시오 : "))
if b == 1:
    print("1 은(는) 첫 번째 요소입니다.")
elif b == 2:
    print("2 은(는) 두 번째 요소입니다.")
elif b == 3:
    print("3 은(는) 세 번째 요소입니다.")
elif b == 4:
    print("4 은(는) 네 번째 요소입니다.")
elif b == 5:
    print("5 은(는) 다섯 번째 요소입니다.")
```

    a의 요소를 하나 선택하시오 : 2
    2 은(는) 두 번째 요소입니다.
    

> 2.다음과 같이 '삼'이 입력되면 try - except 문을 통해 '오류 : 입력 값이 정수나 실수가 아님'을 출력하시오.


```python
a = [1, 2, 3, 4, 5]
try:
    b = int(input("a의 요소를 하나 선택하시오 : "))
    if b == 1:
        print("1 은(는) 첫 번째 요소입니다.")
    elif b == 2:
        print("2 은(는) 두 번째 요소입니다.")
    elif b == 3:
        print("3 은(는) 세 번째 요소입니다.")
    elif b == 4:
        print("4 은(는) 네 번째 요소입니다.")
    elif b == 5:
        print("5 은(는) 다섯 번째 요소입니다.")
except:
    print("오류: 입력 값이 정수나 실수가 아님")
```

    a의 요소를 하나 선택하시오 : 1
    1 은(는) 첫 번째 요소입니다.
    

### LAB 8-4 : 파일 저장하기

> 1. 다음과 같은 내용을 가지는 numbers.txt 파일을 파이썬의 write() 메소드를 이용하여 작성하여라. 이때 아래와 같이 줄바꿈이 되도록 하자.

![image.png](attachment:image.png)

> 2. 다음과 같은 내용을 가지는 we_will_rock.txt 파일을 파이썬의 write() 메소드를 이용하여 작성하여라. 따옴표의 출력에 주의하여 프로그램을 작성하자.

![image.png](attachment:image.png)

### LAB 8-5 : 파일 읽어오기

> 1. 다음과 같은 내용을 가지는 numbers.txt 파일을 파이썬의 read() 메소드를 이용하여 출력하시오(힌트 : f.readline().rstrip()을 사용하여라).

![image-2.png](attachment:image-2.png)

> 2.다음과 같은 내용을 가지는 we_will_rock.txt 파일을 파이썬의 read() 메소드를 이용하여 출력하여라.(힌트 : f.readline().rstrip()을 사용하여라)

![image.png](attachment:image.png)

### LAB 8-6 : 파일 저장하기

> 1. 사용자로부터 파일 이름을 입력으로 받은 후 입력받은 파일의 모든 문자를 대문자로 변환한 후 출력하여라. 그리고 이 내용을 [파일명_upper].txt 라는 이름의 파일로 저장하여라(힌트 : 문자열의 upper() 메소드를 사용하시오).

![image.png](attachment:image.png)

> 2. 사용자로부터 파일 이름을 입력으로 받은 후 입력받은 파일의 모든 줄을 역순으로 하여 다음과 같이 출력하시오.

![image.png](attachment:image.png)


```python

```
