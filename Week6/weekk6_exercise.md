> 1. 사용자로부터 임의의 수를 연속적으로 입력받도록 하시오. 이 수들에 대한 평균값, 최댓값, 최솟값을 반환하는 함수 mean_of_n(nums), max_of_n(nums), min_of_n(nums)을 구현하여 다음과 같이 출력하여라.


```python
def mean_of_n(nums):
    my_list = []
    for num in nums:
        my_list.append(num)
    return sum(my_list) / len(my_list)


def max_of_n(nums):
    my_list = []
    for num in nums:
        my_list.append(num)
    return max(my_list)


def min_of_n(nums):
    my_list = []
    for num in nums:
        my_list.append(num)
    return min(my_list)


stdin = tuple(map(int, input("정수를 여러 개 입력하시오 : ").split()))
print("평균값은 {:.1f}".format(mean_of_n(stdin)))
print("최댓값은", max_of_n(stdin))
print("최솟값은", min_of_n(stdin))
```

    정수를 여러 개 입력하시오 : 3 45 32 5 7 8 4 44 5 90 17
    평균값은 23.6
    최댓값은 90
    최솟값은 3
    

> 2. 직각삼각형의 빗변을 이루는 선분의 양 끝점을 나타내는 두 좌표 (x1, y1), (x2, y2)를 입력받아 직각삼각형의 면적을 구하는 프로그램을 작성하여라. 이때 4개의 좌표값을 입력으로 받아 직각삼각형의 면적을 반환하는 area(x1, y1,x2, y2) 함수를 구현하시오   
단, x2>x1이고 y2>y1이다.


```python
def area(x1, y1, x2, y2):
    height = y2 - y1
    width = x2 - x1
    return width * height * 0.5


x1 = int(input("x1 좌표를 입력하시오 : "))
y1 = int(input("y1 좌표를 입력하시오 : "))
x2 = int(input("x2 좌표를 입력하시오 : "))
y2 = int(input("y2 좌표를 입력하시오 : "))
print("직각삼각형의 면적은 :", area(x1, y1, x2, y2))
```

    x1 좌표를 입력하시오 : 0
    y1 좌표를 입력하시오 : 0
    x2 좌표를 입력하시오 : 3
    y2 좌표를 입력하시오 : 4
    직각삼각형의 면적은 : 6.0
    

> 3. 쉼표 단위로 구분된 정수를 임의의 수만큼 입력받은 후 이 숫자들을 오름차순으로 정렬하여 출력하시오.   
힌트: split( ) 메소드를 사용한다.


```python
stdin = list(map(int, input("쉼표로 구분된 정수를 여러 개 입력하시오: ").split(",")))
print("입력된 정수의 리스트:", stdin)
stdin.sort()
print("정렬된 정수의 리스트:", stdin)
```

    쉼표로 구분된 정수를 여러 개 입력하시오: 56,67,89,34,24,300,99
    입력된 정수의 리스트: [56, 67, 89, 34, 24, 300, 99]
    정렬된 정수의 리스트: [24, 34, 56, 67, 89, 99, 300]
    

> 9. 3개 숫자를 오름차순으로 정렬하여 출력하는 sort3() 함수를 작성하시오. 사용자로부터 3개의 숫자를 입력받고 이들 숫자를 오름차순으로 출력하는 테스트 프로그램을 작성하시오(힌트 : sort3() 함수의 매개변수로 입력된 정수는 리스트의 append() 메소드를 통해서 추가한 후 리스트의 sort() 메소드를 이용하여 정렬하시오. 정렬된 리스트를 a라 하면 a[0], a[1], a[2] 인덱스를 사용하여 출력하시오.


```python
def sort3(a, b, c):
    my_list = []
    my_list.append(a)
    my_list.append(b)
    my_list.append(c)
    my_list.sort()
    return my_list

print("세 수를 입력하세요")
a = int(input())
b = int(input())
c = int(input())
print("정렬된 리스트는 다음과 같습니다 :", sort3(a, b, c)[0], sort3(a, b, c)[1], sort3(a, b, c)[2])

```

    세 수를 입력하세요
    3
    2
    5
    정렬된 리스트는 다음과 같습니다 : 2 3 5
    

> 10. 삼각형의 밑변(width), 높이(height)를 입력받아서 삼각형의 면적을 구하는 cal_area(width, height)라는 함수를 정의하여라. 사용자로부터 삼각형의 밑변과 높이를 입력받은 후, 이 함수를 이용하여 다음과 같은 결과를 얻는 프로그램을 작성하여라.


```python
def cal_area(width, height):
    return width * height * 0.5

w = int(input("밑변을 입력하시오 : "))
h = int(input("높이를 입력하시오 : "))
print("삼각형의 면적 :", cal_area(w, h))
```

    밑변을 입력하시오 : 20
    높이를 입력하시오 : 15
    삼각형의 면적 : 150.0
    


```python

```
