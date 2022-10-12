# Week6 - Jump to Python (2020110973_박석현)

### Q1

> 주어진 자연수가 홀수인지 짝수인지 판별해 주는 함수(is_odd)를 작성해 보자.


```python
def is_odd(n):
    if n % 2 == 1:
        return True
    return False
```

### Q2

> 입력으로 들어오는 모든 수의 평균 값을 계산해 주는 함수를 작성해 보자.


```python
def calculator(*numbers):
    my_list = []
    for number in numbers:
        my_list.append(number)
    return sum(my_list) / len(my_list)
```

### Q3

> 다음은 두 개의 숫자를 입력받아 더하여 돌려주는 프로그램이다.


```python
input1 = int(input("첫번째 숫자를 입력하세요:"))
input2 = int(input("두번째 숫자를 입력하세요:"))

total = input1 + input2
print("두 수의 합은 %s 입니다" % total)
```

    첫번째 숫자를 입력하세요:3
    두번째 숫자를 입력하세요:6
    두 수의 합은 9 입니다
    

### Q4

> 다음 중 출력 결과가 다른 것 한 개를 골라 보자.   
print("you" "need" "python")   
print("you"+"need"+"python")   
print("you", "need", "python")   
print("".join(["you", "need", "python"]))


```python
print("you", "need", "python")
```

    you need python
    
