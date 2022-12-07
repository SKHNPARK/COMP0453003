# Week14 - HOL (2020110973_박석현)

### LAB 11-1 : ndarray 객체 생성하기 그리고 속성 알아보기

> 1. 0에서 9까지의 정수 값을 가지는 ndarray 객체 a를 넘파이를 이용하여 작성하여 다음과 같이 출력하여라.


```python
import numpy as np

a = np.array(list(range(10)))
print(a)
```

    [0 1 2 3 4 5 6 7 8 9]
    

> 2.range() 함수를 사용하여 0에서 9까지의 정수 값을 가지는 ndarray 객체 b를 만들고 문제 1의 결과와 같이 나타나도록 하여라.


```python
import numpy as np

b = np.array(list(range(10)))
print(b)
```

    [0 1 2 3 4 5 6 7 8 9]
    

> 3. 문제 2의 코드를 수정하여 0에서 9까지의 정수 값 중에서 다음과 같이 짝수를 가지는 ndarray 객체 c를 출력하여라.


```python
import numpy as np

c = np.array(list(range(0, 10, 2)))
print(c)
```

    [0 2 4 6 8]
    

> 4. 문제 3번 ndarray 객체 c의 shape, ndim, dtype, size, itemsize를 다음과 같이 출력하여라.


```python
import numpy as np

c = np.array(list(range(0, 10, 2)), dtype=np.int64)
print(c.shape)
print(c.ndim)
print(c.dtype)
print(c.size)
print(c.itemsize)
```

    (5,)
    1
    int64
    5
    8
    


```python
import numpy as np

a = np.array([23, 45, 67, 7, 2, 30, 34, 82])
print(a)
```

    [23 45 67  7  2 30 34 82]
    

> 이 ndarray의 max(), min(), mean() 메소드를 이용하여 최대값, 최소값, 평균을 다음과 같이 출력하여라.


```python
import numpy as np

a = np.array([23, 45, 67, 7, 2, 30, 34, 82])
print(a.max())
print(a.min())
print(a.mean())
```

    82
    2
    36.25
    

> 2. numpy.random.randint() 함수를 사용하여 0에서 99까지의 정수 값 10개를 랜덤하게 생성하시오. 이 10개의 값을 b라는 ndarray에 넣고 ndarray에서 최대값, 최소값, 평균을 다음과 같이 출력하여라


```python
import numpy as np

b = np.random.randint(0, 100, size=10)
print(b.max())
print(b.min())
print(b.mean())
```

    94
    1
    44.1
    

> 3. 위의 문제 1의 a 배열과 문제 2의 b 배열을 append() 하여 다음과 같은 배열 c를 생성하여 출력하시오.


```python
import numpy as np

a = np.array([23, 45, 67, 7, 2, 30, 34, 82])
b = np.random.randint(0, 100, size=10)

c = np.append(a, b)
print(c)
```

    [23 45 67  7  2 30 34 82  4 28  5 87  9  2 87 55 23 93]
    

### LAB 11-3 : 다차원 행렬의 생성과 활용

> 1.1에서 9까지의 모든 정수 값을 크기 순서대로 가지는 3x3  크기의 행렬 a를 생성하고, 모든 성분의 값이 2인 3x3 크기의 행렬 b를 생성하여라.


```python
import numpy as np

a = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])
b = np.array([[2, 2, 2], [2, 2, 2], [2, 2, 2]])
print(a)
print(b)

```

    [[1 2 3]
     [4 5 6]
     [7 8 9]]
    [[2 2 2]
     [2 2 2]
     [2 2 2]]
    

> 2. 다음 행렬 연산의 결과를 예상한 후 실행하고 그 결과를 적으시오.


```python
import numpy as np

a = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])
b = np.array([[2, 2, 2], [2, 2, 2], [2, 2, 2]])
print(a + b)
print(a - b)
print(a * b)
print(a / b)
print(a @ b)
print(a ** 2)
```

    [[ 3  4  5]
     [ 6  7  8]
     [ 9 10 11]]
    [[-1  0  1]
     [ 2  3  4]
     [ 5  6  7]]
    [[ 2  4  6]
     [ 8 10 12]
     [14 16 18]]
    [[0.5 1.  1.5]
     [2.  2.5 3. ]
     [3.5 4.  4.5]]
    [[12 12 12]
     [30 30 30]
     [48 48 48]]
    [[ 1  4  9]
     [16 25 36]
     [49 64 81]]
    

### LAB 11-4 : 행렬의 생성

> 1. full() 함수를 이용하여 모든 원소의 값이 2인 3x3 크기의 행렬 a1을 생성하여라.


```python
import numpy as np

a1 = np.full((3, 3), 2)
print(a1)
```

    [[2 2 2]
     [2 2 2]
     [2 2 2]]
    

> 2. arange() 함수를 사용하여 1에서 12까지 12개의 원소를 가지는 1차원 행렬 a2를 생성하여라.


```python
import numpy as np

a2 = np.arange(1, 13)
print(a2)
```

    [ 1  2  3  4  5  6  7  8  9 10 11 12]
    

> 3. arange() 함수의 step 값을 이용하여  1에서 50까지 정수 중에서 3의 배수만을 가지는 행렬 a3을 생성하여라.


```python
import numpy as np

a3 = np.arange(3, 50, 3)
print(a3)
```

    [ 3  6  9 12 15 18 21 24 27 30 33 36 39 42 45 48]
    

> 4. 0에서 20 사이에서 동일한 간격의 값을 가지는 원소 5개를 가진 a4 행렬을 생성하여라.


```python
import numpy as np

a4 = np.linspace(0, 20, 5)
print(a4)
```

    [ 0.  5. 10. 15. 20.]
    

### LAB 11-5 : 배열의 재구성

> 1. arange() 함수를 사용하여 1에서 12까지의 원소를 가지는 1차원 배열 a1을 생성하여라. 그리고 이 a1배열을 reshape() 메소드를 사용하여 2행 6열의 행렬로 재구성하여라.


```python
import numpy as np

a1 = np.arange(1, 13).reshape(2, 6)
print(a1)
```

    [[ 1  2  3  4  5  6]
     [ 7  8  9 10 11 12]]
    

> 2. arange() 함수를 사용하여 1에서 30까지의 원소를 가지는 1차원 배열 a2을 생성하여라. 그리고 이 a2 배열을 reshape() 메소드를 사용하여 3행 10열의 행렬로 재구성하여라.


```python
import numpy as np

a2 = np.arange(1, 31).reshape(3, 10)
print(a2)
```

    [[ 1  2  3  4  5  6  7  8  9 10]
     [11 12 13 14 15 16 17 18 19 20]
     [21 22 23 24 25 26 27 28 29 30]]
    

> 3. 문제 2에서 생성한 a2 배열을 reshape() 메소드를 사용하여 6행 5열의 행렬로 재구성한 행렬 a3을 생성하여라.


```python
import numpy as np

a2 = np.arange(1, 31).reshape(3, 10)
a3 = a2.reshape(6, 5)
print(a3)
```

    [[ 1  2  3  4  5]
     [ 6  7  8  9 10]
     [11 12 13 14 15]
     [16 17 18 19 20]
     [21 22 23 24 25]
     [26 27 28 29 30]]
    

> 4. 문제 3에서 생성한 a3 배열을 transpose() 함수를 사용하여 다음과 같은 전치 행렬을 생성하여라.


```python
import numpy as np

a2 = np.arange(1, 31).reshape(3, 10)
a3 = a2.reshape(6, 5)
a4 = a3.transpose()
print(a4)
```

    [[ 1  6 11 16 21 26]
     [ 2  7 12 17 22 27]
     [ 3  8 13 18 23 28]
     [ 4  9 14 19 24 29]
     [ 5 10 15 20 25 30]]
    

### LAB 11-6 : 다차원 배열의 축과 삽입 함수

> 1. 1에서 100까지의 랜덤 정수 15개를 np.random.randint()를 통해서 생성하여라. 이렇게 생성한 정수 값들을 (3, 5)의 shape을 가지는 행렬 a에 다음과 같이 저장하여 출력하여라.


```python
import numpy as np

a = np.random.randint(1, 101, 15).reshape(3, 5)
print(a)
```

    [[97  9 60 82  3]
     [ 9 38 38 35 24]
     [35 98 62 29 87]]
    

> 2. 문제 1에서 생성한 a 행렬에 대해 열방향의 최대값, 최소값, 평균을 각각 다음과 같이 출력하시오.


```python
import numpy as np

a = np.random.randint(1, 101, 15).reshape(3, 5)
print(a.max(axis=0))
print(a.min(axis=0))
print(a.sum(axis=0) / 15)
```

    [57 89 98 28 79]
    [39 17 27 10 24]
    [ 9.8        11.13333333 10.6         4.13333333 11.66666667]
    

> 3. 문제 1에서 생성한 a 행렬에 대해 행방향의 최대값, 최소값, 평균을 각각 다음과 같이 출력하시오.


```python
import numpy as np

a = np.random.randint(1, 101, 15).reshape(3, 5)
print(a.max(axis=1))
print(a.min(axis=1))
print(a.sum(axis=1) / 15)
```

    [100  85  93]
    [ 7 23  4]
    [19.33333333 18.26666667 15.26666667]
    

### LAB 11-7 : 배열의 인덱싱과 슬라이싱

> 1. 1에서 10까지의 원소를 가지는 1차원 배열 a를 생성하여라. 이 a를 인덱싱하여 [2, 4, 6, 8]의 원소를 가진 배열 b를 생성하여 다음과 같이 출력하여라.


```python
import numpy as np

a = np.arange(1, 11)
b = a[1: 9: 2]
print(a)
print(b)
```

    [ 1  2  3  4  5  6  7  8  9 10]
    [2 4 6 8]
    

> 2. 문제 1에서 생성한 배열 a를 슬라이싱하여 다음과 같은 배열 b, c, d, e, f를 생성하여라.


```python
import numpy as np

a = np.arange(1, 11)
b = a[5:]
c = a[6:]
d = a[:3]
e = a[:10:2]
f = a[10:: -2]
print(b)
print(c)
print(d)
print(e)
print(f)
```

    [ 6  7  8  9 10]
    [ 7  8  9 10]
    [1 2 3]
    [1 3 5 7 9]
    [10  8  6  4  2]
    

### LAB 11-8 : 3차원 배열의 인덱싱

> 1. (4, 3, 2) 형태의 3차원 배열을 다음과 같이 인덱스와 원소 값이 나타나도록 출력하시오.


```python
import numpy as np

a = np.arange(0, 24).reshape(4, 3, 2)

print('{:13s}{:5s}'.format('index', 'element'))
for i in np.ndindex(a.shape):
    print('{}{:7d}'.format(i, a[i]))
```

    index        element
    (0, 0, 0)      0
    (0, 0, 1)      1
    (0, 1, 0)      2
    (0, 1, 1)      3
    (0, 2, 0)      4
    (0, 2, 1)      5
    (1, 0, 0)      6
    (1, 0, 1)      7
    (1, 1, 0)      8
    (1, 1, 1)      9
    (1, 2, 0)     10
    (1, 2, 1)     11
    (2, 0, 0)     12
    (2, 0, 1)     13
    (2, 1, 0)     14
    (2, 1, 1)     15
    (2, 2, 0)     16
    (2, 2, 1)     17
    (3, 0, 0)     18
    (3, 0, 1)     19
    (3, 1, 0)     20
    (3, 1, 1)     21
    (3, 2, 0)     22
    (3, 2, 1)     23
    

> 2. (4, 3, 2) 형태의 3차원 배열을 concatenate() 함수를 사용하여 다음과 같은 배열로 만드시오.


```python
print(np.concatenate((a[0, 0], a[1, 0]), axis=0))
print(np.concatenate((a[0, 0], a[2, 1]), axis=0))
print(np.concatenate((a[0], a[1]), axis=0))
print(np.concatenate((a[0], a[1]), axis=1))
print(np.concatenate((a[0, 0], a[1, 0]), axis=0))
```

    [0 1 6 7]
    [ 0  1 14 15]
    [[ 0  1]
     [ 2  3]
     [ 4  5]
     [ 6  7]
     [ 8  9]
     [10 11]]
    [[ 0  1  6  7]
     [ 2  3  8  9]
     [ 4  5 10 11]]
    [0 1 6 7]
    

### LAB 11-9 : 2차원 배열의 슬라이싱

> 1. 아래 그림과 같이 0에서 15까지의 연속적인 값을 원소로 가지는 4x4 크기의 2차원 배열 a를 생성하여라. 이 a에 대하여 인덱싱과 슬라이싱을 적용하여 다음과 같은 b, c, d, e 배열을 구하여라.


```python
a = np.arange(0, 16).reshape(4, 4)
print('행렬 a :')
b = a[:, 1]
print('b =', b)
c = a[2, 1:]
print('c =', c)
d = a[:2, :2]
print('d =', d)
e = a[1:3, 1:3]
print('e =', e)
```

    행렬 a :
    b = [ 1  5  9 13]
    c = [ 9 10 11]
    d = [[0 1]
     [4 5]]
    e = [[ 5  6]
     [ 9 10]]
    

> 2. 문제 1에서 생성한 배열 a를 슬라이싱하고 평탄화 연산을 하여 다음과 같은 배열 f, g, h를 생성하여라.


```python
f = a[0:2, 0:3].flatten()
print('f =', f)
g = a[2:, :].flatten()
print('g =', g)
h = np.concatenate((a[1, 1:4], a[3, 1:4])).flatten()
print('h =', h)
```

    f = [0 1 2 4 5 6]
    g = [ 8  9 10 11 12 13 14 15]
    h = [ 5  6  7 13 14 15]
    

### LAB 11-10 : 연립방정식 풀이

> 1. 다음과 같은 연립방정식의 해를 구하시오.   
이 연립방정식의 해 x, y, z를 다음과 같이 출력하시오.


```python
import numpy as np
A = np.array([[1, 1, -1], [2, -1, 3], [1, 2, 1]], dtype='int32')
B = np.array([0, 9, 8], dtype='int32')
x = np.linalg.solve(A, B)
print('x = {:4.1f}, y = {:4.1f}, z = {:4.1f}'.format(x[0], x[1], x[2]))
```

    x =  1.0, y =  2.0, z =  3.0
    

> 2. 1번 문제의 연립방정식은 다음과 같은 행렬 A를 가진다. 이 행렬의 행렬식을 linalg.det() 함수를 사용하여 다음과 같이 구하여라.


```python
A = np.array([[1, 1, -1], [2, -1, 3], [1, 2, 1]], dtype='int32')
det = np.linalg.det(A)
print('det(A) = {:4.1f}'.format(det))
```

    det(A) = -11.0
    

> 3. 3x3 행렬 A의 행렬식은 다음과 같이 정의할 수 있다. 문제 2번의 A 행렬의 행렬식-11이 아래 수식의 가장 오른쪽 항의 행렬식의 연산과 그 결과가 같음을 보이시오. 이를 위하여 3개의 2x2 행렬의 행렬식과 각각의 행렬식에 a, -b, c를 곱한 값을 더하시오.


```python
det = np.linalg.det(A)
print('det(A) =', det)
a1 = np.array([[-1, 3], [2, 1]])
a2 = np.array([[2, 3], [1, 1]])
a3 = np.array([[2, -1], [1, 2]])
det = 1 * np.linalg.det(a1) - 1 * np.linalg.det(a2) - 1 * np.linalg.det(a3)
print('det(A) = {:4.1f}'.format(det))
```

    det(A) = -11.000000000000002
    det(A) = -11.0
    
