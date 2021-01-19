# Control Flow

## 조건문

### if 조건문

```python
a = int(input())
if a >= 0:
    print("양수")
else :
    print("음수")
```

두 개 이상의 조건을 활용할 경우 elif 조건 사용

```python
if a > 0:
    print("양수")
elif a == 0 :
    print("0")
else:
    print("음수")
```

##  조건 표현식(Conditional Expression)

**삼항 연산자 (Ternary Operator) **라고도 부른다.

if, else를 사용하여 실행한다. :star: if 문과는 다른 형태!

if 앞에는 조건문에서 true값을 반환할때 실행되는 문법(1이 반환되는), else뒤에는 false=0이 반환될때

```python
#그냥 if문과 다르게
true_value if <조건식> else false_value #이형태로 작성

number = int(input)
result = '3의 배수가 아닙니다.'if number % 3  else '3의 배수입니다.'
print(result)
#여기서 ==0 안해도 되는건 만약, 배수라면 0을 반환해서 if문이 아닌 else문이 작동
```

## 



## 반복문

- While 반복문

  조건이 참인 경우 계속 반복적으로 코드 실행 -> 꼭 탈출 방법이 있어야 한다.

  ```python
  while True:
      print("계속 반복")
  ```

  

- for 반복문

  **enumerate()**와 함께 사용시 index, value 값을 같이 사용한다.

  enumerate()

  내장 함술, 튜플 형태로 인덱스와 값을 돌려준다.

  ```python
  for idx, menu in enumerate(lunch):
      print(idx, menu)
  #start = 원하는 시작 값을 입력하면 idx를 시작으로 1부터 설정할 수 있습니다.
  for idx, menu in enumerate(lunch, start=1):
      
  ```

- 반복문 제어

  1. break : 반복문 중단

  ```python
  while True: 
      #조건 걸어주기 어러울 때 True 한다음에, 반복문 탈출 시점에 break로 걸어준다.
      if n == 5:
          break
      print(n)
      n += 1
  ```

  2. continue 

     continue 이후의 코드를 실행하지 않고, 다음 요소로 넘어가서 반복을 수행한다.

     ```python
     for i in range(20):
         if i % 2 ==1:
             continue
         print(f'{i}는 짝수입니다.')
     print('반복 종료') #반복문 최종 종료
     ```

  3. for~else 문

     if else와는 다르다! else를 for 와 같은 수준으로 작성! 조건이 거짓이 되서 종료할 때 실행된다. break문으로 반복이 종료될 경우에는 실행이 되지 않는다. 파이썬에만 존재!ㄴ

     ```python
     for i in range (10):
         print(i)
         if i == 33: #조건이 범위 밖이라 작동 안함
             break
     else:
         print("break 작동 안햇당")
     ```

  4. pass

     아무고토 하지 않는다.

     pass와 continue 차이

     - pass 사용시

     ```python
     for menu in lunch:
         if menu =='마라탕':
             pass
         print(menu)
         #pass 사용시에는 마라탕도 출력한다
         
     ```

     - continue 사용시

       ```python
       for menu in lunch:
           if menu =='마라탕':
               continue
           print(menu)
           #continue 사용시에는 마라탕은 출력안한다
       ```

       



