# ![KakaoTalk_20210118_131607293 (3)](C:\Users\kwakn\Pictures\KakaoTalk_20210118_131607293 (3).jpg)1/20 함수(Function) II

## 1. 함수와 스코프

함수는 내부 공간(Scope)를 생성한다.

:heavy_check_mark: 지역 스코프(local scope) : 함수로 생성된 공간

​		지역 변수 (local variable) : 지역 스코프에 정의된 변수

:heavy_check_mark: 전역 스코프(global scope): 코드 어느 곳에서든 참조가 가능한 공간

​		전역 변수 (global variable): 전역 스코프에 정의된 변수



```python
x = 1 #전역 스코프

def ex_func(y): #지역스코프
    z = 5 #지역스코프
    print(x) #여기서는 전역 스코프의 값 1 출력, 만약 함수 안에 x 값이 있다면 그 값 출력
    print(y)
    print(z)
ex_func(3)
print(x)
print(y) #y,z는 local이므로 출력이 안된다. NameError 발생
print(z)
```

### 이름 검색 (Resolution) 규칙

식별자들은 이름공간(namespace)라는 곳에 저장되어있는데! 거기서 찾아 올때 **LEGB RULE** 순서를 지키면서 찾아온다.

1. Local scope
2. Enclosed Scope : 상위 함수
3. Global Scope
4. Built- in Scope : 내장 함수, 속성

:question: 만약, global variable 과 local variable의 이름이 같으면?

```python
x = 5
def local_scope():
    x = 10
local_scope()
print(x)#여기서 사용되는 x는 global x이므로, 5의 값을 가진다.
#출력 값 : 5
```

전역 변수를 global로 바꾸는 방법 =>  **global.변수이름**

```python
x = 5
def local_scope():
    global.x = 10
local_scope()
print(x) #이제 함수안의 x 값이 global 값으로 저장되어 있으니까!
#출력 값 : 10
```

## 2. 재귀 함수(Recursive function)

:star: 함수 내부에서 자기 자신을 호출하는 함수!

반복문과 원리는 동일하다. **Base Case** 설정이 가장 중요하다.

만약, 어렵다면 그림을 그려가면서 규칙을 잡아가는게 중요하다! 점화식과 동일함!

1. 팩토리얼 계산

   ```python
   def factorial(x):
       if x == 1:
           return 1
       else:
           return x * factorial (x-1)
   ```

2. 피보나치 수열

   0 번째 항은 정의마다 다르다! 여기서는 f(0) = 1로 설정

   ```python
   def fibo(n):
       if x < 2:
           return 1
       else:
           return fibo(n-1)+fibo(n-2)
   ```

   ```python
   #반복문 사용
   def fibo(n):
       a, b = 1, 1
       i = 0
       while i < n-1:
           a, b = b, a + b
           i += 1
        return b
   ```

   

