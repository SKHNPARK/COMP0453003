# Week12 - HOL (2020110973_박석현)

### LAB 9-1 : 객체와 메소드 호출

> 1. 다음 메소드 호출의 결과는 무엇인가?


```python
print((200).__sub__(100))
print((200).__mul__(100))
print((200).__truediv__(100))
```

    100
    20000
    2.0
    

> 2. 다음 메소드 호출의 결과는 무엇인가?


```python
print([10, 20, 30, 40].pop())
```

    40
    

> 3. 다음 중 리스트 객체가 호출할 수 없는 메소드는 무엇인가?

1) pop()     2) keys()     3) removea()     5) get()

2) keys()

> 4. 다음과 같은 방법으로 int 클래스의 메소드와 속성을 조사하여라.


```python
print(dir(int))
```

    ['__abs__', '__add__', '__and__', '__bool__', '__ceil__', '__class__', '__delattr__', '__dir__', '__divmod__', '__doc__', '__eq__', '__float__', '__floor__', '__floordiv__', '__format__', '__ge__', '__getattribute__', '__getnewargs__', '__gt__', '__hash__', '__index__', '__init__', '__init_subclass__', '__int__', '__invert__', '__le__', '__lshift__', '__lt__', '__mod__', '__mul__', '__ne__', '__neg__', '__new__', '__or__', '__pos__', '__pow__', '__radd__', '__rand__', '__rdivmod__', '__reduce__', '__reduce_ex__', '__repr__', '__rfloordiv__', '__rlshift__', '__rmod__', '__rmul__', '__ror__', '__round__', '__rpow__', '__rrshift__', '__rshift__', '__rsub__', '__rtruediv__', '__rxor__', '__setattr__', '__sizeof__', '__str__', '__sub__', '__subclasshook__', '__truediv__', '__trunc__', '__xor__', 'as_integer_ratio', 'bit_length', 'conjugate', 'denominator', 'from_bytes', 'imag', 'numerator', 'real', 'to_bytes']
    

> 5. 다음과 같은 방법으로 list 클래스의 메소드와 속성을 조사하여라.


```python
print(dir(list))
```

    ['__add__', '__class__', '__class_getitem__', '__contains__', '__delattr__', '__delitem__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__getitem__', '__gt__', '__hash__', '__iadd__', '__imul__', '__init__', '__init_subclass__', '__iter__', '__le__', '__len__', '__lt__', '__mul__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__reversed__', '__rmul__', '__setattr__', '__setitem__', '__sizeof__', '__str__', '__subclasshook__', 'append', 'clear', 'copy', 'count', 'extend', 'index', 'insert', 'pop', 'remove', 'reverse', 'sort']
    

### LAB 9-2 : 용어 정리

> 1. 다음 용어를 정의하여라.

a) 객체 지향 프로그래밍:   
> - 프로그램을 짤 때, 프로그램을 실제 세상에 가깝게 모델링 하는 기법   
> - 클래스나 객체

b) 절차적 프로그래밍:   
> - 함수나 모듈을 만들어두고 이것들을 문제해결 순서에 맞게 호출하여 수행   
> - 그래픽 사용자 인터페이스 시스템과 같이 다양한 그래픽 요소들이 있을 경우 효과적으로 문제해결을 하기 어렵다.

c) 그래픽 사용자 인터페이스   
> - 사용자가 편리하게 사용할 수 있도록 입출력 등의 기능을 알기 쉬운 아이콘 따위의 그래픽으로 나타낸 것

> 2. 객체 지향 프로그래밍 기법과 절차적 프로그래밍 기법의 차이점을 기술하여라. 

>   객체 지향 프로그래밍:   
> - 잘 설계된 클래스를 이용하여 객체를 생성
> - 클래스는 속성과 행위를 가지도록 설계하고 이 클래스를 이용하여 실제로 상호작용       하는 객체를 만들어서 프로그램 적용시키는 방법을 사용   

>   절차적 프로그래밍:
> - 데이터들이 많아지고 함수가 많아진다면 매우 많은 화살표와 함수 호출이 필요   
> - 대규모 프로젝트에서는 큰 어려움

### LAB 9-3 : 용어 정리

> 1. 다음 용어를 정의하여라.

a) 클래스:   
- 객체를 만들어 내기 위한 설계도   

b) 객체:   
- 클래스로 구현된 모든 대상   

c) 인스턴스;   
- 객체 중에서 설계도를 바탕으로 소프트웨어 세계에 구현된 구체적인 실체   

d) 클래스의 속성   
- name, colr와 같이 나타내는 것   

e) 클래스이 행위   
- meow(), run(), walk()와 같이 속성이 하는 것

### LAB 9-4 : Dog 클래스와 인스턴스 생성

 > 1. 다음 기능을 가진 Dog 클래스와 객체를 생성해라.   
a) def bar(self): 라는 메소드를 가진다. 이 메소드를 통해 짓는 소리를 출력한다.   
b) my_dog = Dog() 라는 명령어로 Dog 인스턴스를 생성하고 my_dog로 참조한다.   
c) my_dog.bark() 라는 메소드로 개짓는 소리를 다음과 같이 출력한다. "멍멍~~"


```python
class Dog:
    def bark(self):
        print("멍멍~~")

my_dog = Dog()
my_dog.bark()
```

    멍멍~~
    

### LAB 9-5 : Dog 클래스와 인스턴스 생성

> 1. 다음 기능을 가진 Dog 클래스를 생성하고 인스턴스와 메소드를 호출하여라.   
a) name 이라는 속성을 가진다.   
b) def __init__(self, name): 이라는 초기화 메소드를 가진다. 이 메소드를 통해서 이름을 초기화 한다.   
c) def bark(self): 라는 메소드를 가진다. 이 메소드를 통해 짓는 소리를 출력한다.   
d) my_dog = Dog('Jindo') 라는 명령어로 my_dog 인스턴스를 생성한다.   
e) my_dog.bark() 라는 메소드로 개짓는 소리를 다음과 같이 출력한다. "멍멍~~"


```python
class Dog():
    def __init__(self, name):
        self.name = name
    def bark(self):
        print("멍멍~~")

my_dog = Dog('Jindo')
my_dog.bark()
```

    멍멍~~
    

### LAB 9-6 : Dog 클래스와 문자열화 메소드

> 1. 다음 기능을 가진 Dog 클래스를 생성하고 인스턴스와 메소드를 호출하여라.   
a) name 이라는 속성을 가진다.   
b) def __init__(self, name): 이라는 초기화 메소드를 가진다. 이 메소드를 통해서 이름을 초기화 한다.   
c) my_dog = Dog('Jindo') 라는 명령어로 my_dog 인스턴스를 생성한다.   
d) Dog 클래스의 __str__() 메소드를 정의하여 print('my_dog의 정보 :', mydog)와 같은 명령문에 대해 다음과 같은 출력이 나타나도록 하여라.   
my_dog의 정보 : Dog(name = Jindo)


```python
class Dog():
    def __init__(self, name):
        self.name = name
    def __str__(self):
        return (f"my_dog의 정보 : Dog(name={self.name})")

my_dog = Dog('Jindo')
print(my_dog.__str__())
```

    my_dog의 정보 : Dog(name=Jindo)
    

### LAB 9-7 : 정수 객체의 is 연산

> 1. 다음 코드의 수행 결과는 무엇인가? 결과를 적고 그 이유를 설명하여라.


```python
n = 100
m = 100

if n is m:
    print('n is m')
else:
    print('n is not m')
```

    n is m
    

정수는 메모리를 절약하기 위해서 같은 저장 위치를 참조한다.

### LAB 9-8 : 특수 메소드의 응용

> 1. 앞서 배운 __mul__()과 __truediv__() 메소드를 이용하여 두 벡터의 곱셈과 나눗셈 기능을 구현하여라. v1이 (30, 40)이고 v2가 (10, 20)이라고 가정하고 다음과 같은 결과가 나타나도록 출력문을 작성하여라.


```python
class Vector2D:
    def __init__(self, x, y):
        self.x = x
        self.y = y
    def __str__(self):
        return "({}, {})".format(self.x, self.y)
    def __mul__(self, other):
        return Vector2D(self.x * other.x, self.y * other.y)
    def __truediv__(self, other):
        return Vector2D(self.x / other.x, self.y / other.y)
v1 = Vector2D(30, 40)
v2 = Vector2D(10, 20)
v3_mul = v1 * v2
v3_div = v1 / v2
print("v1 * v2 =", v3_mul)
print("v1 / v2 =", v3_div)
```

    v1 * v2 = (300, 800)
    v1 / v2 = (3.0, 2.0)
    

> 2. 앞서 배운 __neg__() 메소드 이용하여 벡터의 음의 벡터를 구하시오. v1이 (10, 20)일 경우 출력 값은 다음과 같다.


```python
class Vector2D:
    def __init__(self, x, y):
        self.x = x
        self.y = y
    def __str__(self):
        return "({}, {})".format(self.x, self.y)
    def __neg__(self):
        return Vector2D(-self.x, -self.y)

v1 = Vector2D(10, 20)
v1_neg = v1.__neg__()
print("-v1 =", v1_neg)

```

    -v1 = (-10, -20)
    

### LAB 9-9 : 벡터의 크기 비교하기

> 1. 앞서 배운 비교 연산자에 해당하는 특수 메소드를 이용하여 두 벡터의 크기를 비교하는 프로그램을 작성하시오. v1이 (30, 40)이고 v2가 (10, 20)이라고 가정하면 다음과 같은 결과가 나타나도록 출력문을 작성하여라.


```python
class Vector2D:
    def __init__(self, x, y):
        self.x = x
        self.y = y
    def __lt__(self, other):
        return self.x < other.y and self.y < other.y
    def __le__(self, other):
        return self.x <= other.y and self.y <= other.y
    def __ge__(self, other):
        return self.x >= other.y and self.y >= other.y
    def __gt__(self, other):
        return self.x > other.y and self.y > other.y
v1 = Vector2D(30, 40)
v2 = Vector2D(10, 20)
v3_lt =v1 < v2
v3_le =v1 <= v2
v3_ge =v1 >= v2
v3_gt =v1 > v2

print("v1 > v2", v3_gt)
print("v1 >= v2", v3_ge)
print("v1 < v2", v3_lt)
print("v1 <= v2", v3_le)
```

    v1 > v2 True
    v1 >= v2 True
    v1 < v2 False
    v1 <= v2 False
    

### LAB 9-10 : __dict__를 이용한 인스턴스변수의 조회

> 1. 다음과 같은 코드의 수행 결과는 무엇인가?


```python
class Rect:
    def __init__(self, width, height):
        self.width = width
        self.height = height

r1 = Rect(100, 200)
print(r1.__dict__)
print(r1.__dict__['width'])
```

    {'width': 100, 'height': 200}
    100
    

> 2. 다음과 같은 코드의 수행 결과는 무엇인가?


```python
class Rect:
    def __init__(self, width, height):
        self.__width = width
        self.__height = height

r1 = Rect(100, 200)
print(r1.__dict__)
print(r1.__dict__['_Rect__width'])
```

    {'_Rect__width': 100, '_Rect__height': 200}
    100
    
