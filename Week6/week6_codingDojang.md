### 29.3 연습문제: 몫과 나머지를 구하는 함수 만들기

> 다음 소스 코드를 완성하여 x를 y로 나누었을 때의 몫과 나머지가 출력되게 만드세요.   
```python
x = 10
y = 3
 
                                 
                                 
 
quotient, remainder = get_quotient_remainder(x, y)
print('몫: {0}, 나머지: {1}'.format(quotient, remainder))
```


```python
x = 10
y = 3

def get_quotient_remainder(x, y):
    q = x // y
    r = x % y
    return q, r

quotient, remainder = get_quotient_remainder(x, y)
print('몫: {0}, 나머지: {1}'.format(quotient, remainder))
```

    몫: 3, 나머지: 1
    

### 30.6 연습문제: 가장 높은 점수를 구하는 함수 만들기

> 다음 소스 코드를 완성하여 가장 높은 점수가 출력되게 만드세요.
```python
korean, english, mathematics, science = 100, 86, 81, 91
 
                                             
...
                                             
 
max_score = get_max_score(korean, english, mathematics, science)
print('높은 점수:', max_score)
 
max_score = get_max_score(english, science)
print('높은 점수:', max_score)
```


```python
korean, english, mathematics, science = 100, 86, 81, 91

def get_max_score(*scores):
    score_list = []
    for score in scores:
        score_list.append(score)
    return max(score_list)


max_score = get_max_score(korean, english, mathematics, science)
print('높은 점수:', max_score)
 
max_score = get_max_score(english, science)
print('높은 점수:', max_score)
```

    높은 점수: 100
    높은 점수: 91
    

### 31.4 연습문제: 재귀호출로 회문 판별하기

> 다음 소스 코드를 완성하여 문자열이 회문인지 판별하고 결과를 True, False로 출력되게 만드세요. 여기서는 재귀호출을 사용해야 합니다.
```python
def is_palindrome(word):
                                    
    ...
                                    
 
print(is_palindrome('hello'))
print(is_palindrome('level'))
```


```python
def is_palindrome(word):
    if len(word) < 2:
        return True
    if word[0] != word[-1]:
        return False
    else:
        return is_palindrome(word[1:-1])
    
    
print(is_palindrome('hello'))
print(is_palindrome('level'))
```

    False
    True
    


```python

```
