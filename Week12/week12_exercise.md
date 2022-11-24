> 1. 다음과 같은 기능을 가지는 클래스를 정의하고, 인스턴스를 생성하여라.
-이름(name)과 나이(age)를 속성으로 가지는 Dog 클래스를 정의하여라   
-이름으로 ‘Mango’, 나이로 3의 값을 가지는 my_dog 인스턴스를 생성하여라   
-my_dog의 이름과 나이를 다음과 같이 출력하여라.    
-단, 문자열화 메소드 __str__( )를 구현하여 print(my_dog)의 결과가 예제와 같이 나와야 함.


![image.png](attachment:image.png)


```python
class Dog:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def __str__(self):
        return f"이름은 {self.name}이고, 나이는 {self.age}살 입니다."


print(Dog("Mango", 3))

```

    이름은 Mango이고, 나이는 3살 입니다.
    

> 2. 다음과 같은 기능을 가지는 Counter 클래스를 정의하고 c1, c2라는 이름의 인스턴스를 생성하여라.
-이 클래스는 __number라는 속성값을 가짐   
-number 를 매개변수로 가지는 __init__(self, number) 메소드를 가짐. number의 디폴트 매개변수 값은 0임. 만약 number가 100 이상이 되거나 -1 이하가 되면 0 값을 초기 값으로 가짐.   
-reset( ): __number 를 0으로 초기화하는 메소드   
-inc( ): __number 를 1 증가시키는 메소드. 만약 더한 후 __number의 값이 100 이상이 되면 0으로 초기화 됨   
-dec( ): __number 를 1 감소시키는 메소드. 만약 감소시킨 후 __number의 값이 -1 이하가 되면 0 값을 가짐   
-__str__( ): print(c1)을 실행하면 C(__number)를 출력하는 특수 메소드   
-__add__( ): c1 + c2 연산을 통해 c1의 __number와 c2의 __number 합을 __number로 가지는 Counter 인스턴스를 반환. 만약 __number 합이 100 이상이면 0으로 초기화 됨.   
-__sub__( ): c1 - c2 연산을 통해 c1의 __number와 c2의 __number 차를 __number로 가지는 Counter 인스턴스를 반환. 만약 __number 합이 -1 이하이면 0으로 초기화 됨.   


```python
class Counter:
    def __init__(self, number=0):
        self.__number = number
        if self.__number >= 100 or self.__number <= -1:
            self.__number = 0

    def reset(self):
        self.__number = 0

    def inc(self):
        self.__number += 1
        if self.__number >= 100:
            self.__number = 0

    def dec(self):
        self.__number -= 1
        if self.__number <= -1:
            self.__number = 0

    def __str__(self):
        return f"C({self.__number})"


c1 = Counter(10)
c1.inc()
print("c1 =", c1)

print()

c2 = Counter()
c2.inc()
c2.inc()
c2.dec()
print("c2 =", c2)
c2.reset()
print("c2 =", c2)
```

    c1 = C(11)
    
    c2 = C(1)
    c2 = C(0)
    

> 3. 다음과 같은 기능을 가지는 은행계좌 클래스 BankAccount 클래스를 구현한 뒤, 인스턴스를 생성하여 실행해 보아라.

![image.png](attachment:image.png)


```python
class BankAccount:
    def __init__(self, name, account_num):
        self.__name = name
        self.__account_num = account_num
        self.__balance = 0

    def __str__(self):
        return f"{self.__name}님의 계좌 {self.__account_num}의 잔고는 {self.__balance}원입니다."

    def get_name(self):
        return self.__name

    def get_account_num(self):
        return self.__account_num

    def get_balance(self):
        return self.__balance

    def deposit(self, money):
        self.__balance += money
        print(f"{money}원이 입금되었습니다. 잔고는 {self.__balance}원입니다.")

    def withdraw(self, money):
        if money > self.__balance:
            print(f"계좌 잔고는 {self.__balance}원으로 인출 요구 금액 {money}원 보다 작습니다.")
        else:
            self.__balance -= money


account1 = BankAccount('홍길동', '1234-0001')
print(account1)
account1.deposit(2000)
print(account1)
account1.withdraw(500)
print(account1)
account1.withdraw(5000)

```

    홍길동님의 계좌 1234-0001의 잔고는 0원입니다.
    2000원이 입금되었습니다. 잔고는 2000원입니다.
    홍길동님의 계좌 1234-0001의 잔고는 2000원입니다.
    홍길동님의 계좌 1234-0001의 잔고는 1500원입니다.
    계좌 잔고는 1500원으로 인출 요구 금액 5000원 보다 작습니다.
    

> 4. 다음과 같은 기능을 가지는 Student라는 학생 클래스를 구현하여라. 그리고 인스턴스를 생성하여 실행해보아라.


```python
class Student:
    def __init__(self, name, student_id):
        self.__name = name
        self.__student_id = student_id
        self.__korean_quiz = 0
        self.__math_quiz = 0
        self.__science_quiz = 0
        self.__total_quiz = 0

    def __str__(self):
        return f"이름: {self.__name}, 학번: {self.__student_id}\n" \
               f"국어성적: {self.__korean_quiz}, 수학성적: {self.__math_quiz}, 과학성적: {self.__science_quiz}\n" \
               f"합계: {self.__total_quiz}, 평균: {self.__total_quiz / 3}"

    def get_name(self):
        return self.__name

    def get_student_id(self):
        return self.__student_id

    def get_korean_quiz(self):
        return self.__korean_quiz

    def get_math_quiz(self):
        return self.__math_quiz

    def get_science_quiz(self):
        return self.__science_quiz

    def set_korean_quiz(self, score):
        self.__korean_quiz += score
        self.__total_quiz += self.__korean_quiz

    def set_math_quiz(self, score):
        self.__math_quiz += score
        self.__total_quiz += self.__math_quiz

    def set_science_quiz(self, score):
        self.__science_quiz += score
        self.__total_quiz += self.__science_quiz

    def get_total_score(self):
        return self.__total_quiz

    def get_avg_score(self):
        return self.__total_quiz / 3


name = input('학생의 이름을 입력하세요 : ')
student_id = input('학생의 학번을 입력하세요 : ')

student = Student(name, student_id)

korean_quiz = int(input('학생의 국어 성적을 입력하세요 : '))
math_quiz = int(input('학생의 수학 성적을 입력하세요 : '))
science_quiz = int(input('학생의 과학 성적을 입력하세요 : '))
student.set_korean_quiz(korean_quiz)
student.set_math_quiz(math_quiz)
student.set_science_quiz(science_quiz)
print(student)

```

    학생의 이름을 입력하세요 : 홍길동
    학생의 학번을 입력하세요 : 20200012
    학생의 국어 성적을 입력하세요 : 85
    학생의 수학 성적을 입력하세요 : 90
    학생의 과학 성적을 입력하세요 : 95
    이름: 홍길동, 학번: 20200012
    국어성적: 85, 수학성적: 90, 과학성적: 95
    합계: 270, 평균: 90.0
    

> 5. 다음과 같은 기능을 가지는  TV클래스를 구현하여라. 그리고 이 클래스를 이용하여 인스턴스를 생성하여라. 이 클래스는 다음과 같은 속성과 메서드를 가진다.   
A.속성   
-인스턴스변수   
1.__volume: 0~20까지 볼륨값 가짐   
2.__channel: 0~200까지 채널값 가짐   
3.__is_on: 켜짐 상태면 True, 꺼짐 상태면 False 값 가짐   
-클래스 변수   
1.MIN_VOLUME: 볼륨의 최솟값으로 0이라는 상수   
2.MAX_VOLUME: 볼륨의 최댓값으로 20이라는 상수   
3.MIN_CHANNEL: 채널의 최솟값으로 0이라는 상수   
4.MAX_CHANNEL: 채널의 최댓값으로 200이라는 상수   
B. 메서드   
-__init__ : 디폴트 볼륨 = 5 / 디폴트 채널 = 0일경우 꺼짐 상태 기본값   
-__str__ : TV 볼륨, 채널 상태를 문자열로 반환, TV가 꺼짐 상태일 경우 “TV가 꺼짐 상태입니다”를 반환함   
-toggle_power: TV 상태 꺼짐 <-> 켜짐 변환   
-get_channel: 채널 값 반환   
-set_channel: 채널값 choice값으로 설정. 이때 choice 값이 0~201사이 값이 아니면 “채널오류” 출력   
-get_volume: 볼륨값 반환   
-set_volume: 볼륨값 choice값으로 설정. 이때 choice 값이 0~20사이 값이 아니면 “볼륨오류” 출력   
-volume_up: 볼륨 1 증가. 최댓값 MAX_VOLUME   
-volume_down: 볼륨 1 감소, 최솟값 MIN_VOLUME   
-channel_up: 채널 1 증가, 201이상 될 경우 MIN_CHANNEL(=0)로 돌아감   
-channel_down: 채널 1 감소, 0이하 될 경우 MAX_CHANNEL(=200)로 돌아감   



```python
class TV:
    MIN_VOLUME = 0
    MAX_VOLUME = 20
    MIN_CHANNEL = 0
    MAX_CHANNEL = 200

    def __init__(self):
        self.__volume = 5
        self.__channel = 0
        self.__is_on = 0

    def __str__(self):
        if self.__is_on:
            return f"볼륨 = {self.__volume}, 채널 = {self.__channel}"
        else:
            return "TV가 꺼짐 상태입니다."
    def toggle_power(self):
        if self.__is_on == 1:
            self.__is_on = 0
        else:
            self.__is_on = 1

    def get_channel(self):
        return self.__channel

    def set_channel(self, choice):
        if choice > 201 or choice < 0:
            print("채널 오류")
        else:
            self.__channel = choice

    def get_volume(self):
        return self.__volume

    def set_volume(self, choice):
        if choice > TV.MAX_VOLUME or choice < TV.MIN_VOLUME:
            print('볼륨오류')
        else:
            self.__volume = choice

    def volume_up(self):
        if self.__volume < TV.MAX_VOLUME:
            self.__volume += 1

    def volume_down(self):
        if self.__volume > TV.MIN_VOLUME:
            self.__volume -= 1

    def channel_up(self):
        self.__channel += 1
        if self.__channel > TV.MAX_CHANNEL:
            self.__channel = TV.MIN_CHANNEL

    def channel_down(self):
        self.__channel -= 1
        if self.__channel < TV.MIN_CHANNEL:
            self.__channel = TV.MAX_CHANNEL

my_tv = TV()
print(my_tv)
my_tv.toggle_power()
print(my_tv)
my_tv.set_channel(200)
print(my_tv)
my_tv.volume_up()
my_tv.channel_up()
print(my_tv)
```

    TV가 꺼짐 상태입니다.
    볼륨 = 5, 채널 = 0
    볼륨 = 5, 채널 = 200
    볼륨 = 6, 채널 = 0
    

> 6.	다음과 같은 기능을 가지는 Rectangle 클래스를 구현하여라. 그리고 이 클래스를 이용하여 인스턴스를 생성하여라. 이 클래스는 다음과 같은 속성과 동작을 가진다.   
-속성   
1.인스턴스변수   
A.__x: 사각형 좌 상단 x값   
B.__y: 사각형 좌 상단 y값   
C.__width: 사각형 너비   
D.__height: 사각형 높이   
2.메서드   
A.__init__: x,y,width, height 매개변수로 인스턴스 변수 초기화   
B.__str__: 좌표, 너비, 높이, 면적 문자열로 반환   
C.set_x, set_y, set_width, set_height: x, y, width, height 지정   
D.get_x, get_y, get_width, get_height: x, y, width, height 반환   
E.area: 사각형 면적 반환   
F.overlaps( rec ) : 겹치면 True, 안겹치면 False   
G.contain(rec): 포함되면 True, 안포함되면 False   


```python
class Rectangle():
    def __init__(self, x, y, width, height):
        self.__x = x
        self.__y = y
        self.__width = width
        self.__height = height

    def __str__(self):
        return f"(x = {self.__x}, y = {self.__y}, h = {self.__height}), 면적: {self.__width * self.__height}"

    def set_x(self, x):
        self.__x = x

    def set_y(self, y):
        self.__y = y

    def set_width(self, width):
        self.__width = width

    def set_height(self, height):
        self.__height = height

    def get_x(self):
        return self.__x

    def get_y(self):
        return self.__y

    def get_width(self):
        return self.__width

    def get_height(self):
        return  self.__height

    def area(self):
        return self.__width * self.__height

r1 = Rectangle(0, 0, 100, 100)
r2 = Rectangle(0, -10, 10, 10)
r3 = Rectangle(-100, 0, 120, 100)

print('r1 = ', r1)
print('r2 = ', r2)
print('r3 = ', r3)

```

    r1 =  (x = 0, y = 0, h = 100), 면적: 10000
    r2 =  (x = 0, y = -10, h = 10), 면적: 100
    r3 =  (x = -100, y = 0, h = 100), 면적: 12000
    
