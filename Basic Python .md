# ![KakaoTalk_20210118_131607293 (3)](https://user-images.githubusercontent.com/77470429/104927396-b93b0300-59e4-11eb-9f0e-c1dd23dfb1dc.jpg) 1/18 Python 

## 기초 문법

:star2:스타일 가이드 **PEP-8**을 사용한다.

#### 주석(Comment)

1. 한 줄 짜리 주석은 문장의 시작에서 #로 시작.
2.  여러줄의 주석을 작성하고 싶을 때에는 """.'''으로 표현 가능 => multiline string 이라고 한다.

```python
# 안뇽! 내이름은 주석!
# """
이렇게 하면 
주석을 여러줄로 하기
조쿠든요
"""
```

#### 코드라인

1. 1줄에 1문장!
2. 기본적으로 파이썬에서는 ;를 잘 사용하지는 않지만, 문장을 구분하는 용도로는 사용할 수 있다.

```python
print('hello');print('world')
```

3. 여러줄로 작성할 경우 역슬래시 \ 를 사용한다.

```python
print('hello\
world!')
```

4. [], {}, ()에서는 \없이도 여러줄로 작성이 가능하다.



#### 변수(Variable)

```python
height=180
```

- **할당 연산자(Assignment Operator)**

  변수는 **=**를 통해 할당된다. 수학에서의 개념과 같이 같다! 라는 의미가 아닌 저장된다는 의미!

  - type(): 해당 데이터 타입 확인
  - id(): 메모리 주소 확인

- 여러 값을 할당하기

  ```python
  #같은 값을 동시에 할당하기
  x = y = 311
  #서로 다른 값을 할당하기
  x, y = 3, 11
  ```

  - 발생가능 Error

    1. 변수의 개수> 할당되는 값

    ![image-20210118135508358](118 Python 기초.assets/image-20210118135508358.png)

    2. 변수의 개수< 할당 값

       ![image-20210118135525062](118 Python 기초.assets/image-20210118135525062.png)

- 값을 서로 **바꾸는** 경우

  - 정석적인 방법 => **temp**이용

    임시적인 저장소인 temp를 사용하는 방법

    ```python
    temp = a #temp에 a의 값을 할당한다
    a = b #a에 b의 값을 할당한다
    b = temp #b에 temp에 있던 값을 할당한다
    ```

  - python에서 사용하는 간단한 방법

    ```python
    a, b = b, a
    ```

- **식별자(Identifiers)**

  변수, 함수, 모듈 등을 구별하는데 사용되는 이름이다.

  1. 이름은 영문알파벳(대문자,소문자 구분), 밑줄(_), 숫자로 구성된다.

  2. 첫 글자에 숫자는 안된당!

  3. 내장함수, 파이썬의 키워드는 식별자로 사용 불가.(예약어)

     False, None, True, and, as, def, elif, else, if, import 등이 있다.

     print와 같은 내장함수를  식별자로 설정할 경우,  더이상 그 원래의 기능을 하지 못합니다.

     ![image-20210118172806051](118 Python 기초.assets/image-20210118172806051.png)

  ## 데이터 타입(Data Type)

  **type**함수를 활용해서 데이터 타입을 알아보는 습관도 매우 중요! :star:

  ### 숫자 타입

  1. 정수(int, ingteger)

     8진수: octal_number이라서 0o로 시작

     10진수: decimal_number, 우리가 아는 그 숫자의 형태

     2진수: binary_number, 0b로 시작

     16진수: hexadecimal_number :0x로 시작

  2. 실수, 부동소수점 (float)

     실수를 컴퓨터가 표현하는 과정에서, 같은 값으로 일치 되지 않는 floating point rounding error가 발생한다. ->**같은 값인지 비교하는 과정에서 오류 발생 **-> 어떻게 해결할수 있는지 코딩하기 :pencil:

     - 반올림하기

     ```python
     round(1,5 -0,8,2)
     #round(,자리수)
     ```

     - 에러 없이 값 비교하기 (abs, sys.float_into.epsilon, math.isclose())

     ```python
     #1.기본처리
     a= 1.5 - 0.8
     b= 0.7
     
     abs(a-b) <= 1e-10 
     #절대값을 이용해, 오차의 절대값이 0.00000~1보다 작은지를 비교한다.
     #bool형 반환
     #2. sys 모듈로 처리
     #epsilon은 float 연산에서 반올림 함으로써 발생하는 오차 상환
     import sys
     abs(a-b) <=sys.float_into.epsilon
     #3. python에서 사용 가능한 math 모듈 사용
     import math
     math.isclose(a,b)
     ```

  3. 복소수 (Complex)

     허수부를 j로 표현한다.

     - 복소수를 문자열로 변환할경우, 중앙 연산자 사이의 공백은 없어야한다.

     ```python
     complex('1+2j') 
     ```

  ### 문자타입(String)

  ### 기본 구조

  - 큰 따옴표(" "), 작은따옴표(' ') 를 사용해야하고, 시작과 끝이 같은 종류여야 한다.

    또한 """, '''  사용하여 다중 문자열을 나타낼 수 있다.

  ```python
  '오늘 저녁 뭐먹지'
  """
  오늘 저녁은 뭐먹지?
  카레?
  마라탕?
  """
  ```

  - 사용자에게 입력받은 input()은 기본적으로 str이다.
  - 문자열은 +연산자를 사용하여 이어 붙일 수 있다.

- **이스케이프 시퀀스** (\\\)

  문자열을 활용하는 경우, 특수문자 혹은 조작을 하기 위하여 사용되는 것으로 \를 활용하여 이를 구분합니다.

  1. 문자열 안에서, 문장부호 (',")를 나타내고 싶을 때에는 \\"의 방식으로 나타낸다.
  2. \n 줄바꿈
  3. \t 탭
  4. \r 캐리지리턴
  5. \n Null
  6. \\\ : \\

  ```python
  print("줄을 바꾸고 싶다면\n탭을 쓰고 싶다면 \t어때")
  ```

  - **옆 으 로 출 력 하 고 싶 다 면 **

    ```python
    print("리스트를 옆으로 출력하고 싶다면,",end="")
    print("옆으로 하면서 강조를 한다면~", end="!")
    ```

    end=" "안에는 다양한 기호 사용가능!

- **String interpolation**

  1. %-formation

     data type을 지정해줘야 하는 번거로움이 있다.

     - %d: 정수
     - %f : 실수
     - %s :문자열

     ```python
     name='배고파'
     a=2.35
     b=3
     print("나는 %s를 출력하고 싶고, %f와 %d를 나타내고싶어 %(name,a,b))
     ```

  2.  str.format

     ```python
     dinner='칼국수'
     print("오늘 저녁은 {}".format(dinner))
     ```

  3. f-strings

     파이썬 3.6 이후 지원하는 기능으로 아주 편-안. 하지만, 다른 방법도 사용할 줄 알아야겠지?

     ```python
     print(f'오늘 저녁은{dinner}야. 맛있겠징?')
     ```

     - 형식 지정

     ```python
     import datetime
     today = datetime.datetime.now() #현재 날짜, 시간을 받아오는 함수
     %y:년도, %m:월, %d:일 %A: 요일
     ```

     - 연산 및 출력형식

     ```python
     e=2.71828
     print(f'건강해지기 위해서는 하루 {e:.2}의 물을 마셔주어야해. {e*2}만큼 마시면 더 좋고')
     ```

     

### Boolean 타입 (참/거짓)

- True, False로 이루어진 bool타입.

  :pencil: 0, (), []. {}, '', None 등은 **False**를 반환한다.

- None 타입

  값이 없음을 나타내기 위해 사용한다. 대문자 필수!

  ​	

### 형 변환

1. 암시적 형변환(Implicit Type Conversion)

   파이썬이 자동으로 형변환을 해준다.

   - bool형 -> int 형

     True =1, False=0 이용	

     ```python
     print(False+3)
     print(True+3)
     ```

   - int, float, complex의 범위

     다른 형식의 숫자형을 더할 경우, 더 큰범위의 type으로 출력 된다.

2. 명시적 형변환(Explicit Type Conversion)

   사용자가 의도적으로 형변환을 해주는 것

   - int()

     ```python
     int('5')
     int(7)
     ```

   - float()

     ```python
     float(6)
     float('3.8')
     ```

   - str()

     int, float, list, tuple, dictionary를 문자열로 변환 가능.

     

### 연산자

1. 산술 연산자

   ```python
   3+5
   3-5
   3*5
   10/5 #나눗셈
   10//2 #몫
   10%3 #나머지
   a**b #a의 b승
   ```

2. 비교 연산자

   ```python
   a=10, b=5, #문자열도 가능
   a < b
   a <= b
   a > b
   a >= b
   a == b
   a != b
   a is b #객체 아이덴티티
   a is not b #부정된 객체 아이덴티티 여기서는 true 반환
   ```

3. 논리 연산자

   ```python
   a and b # a도 True, b도 True 여야 True 반환
   a or b # 둘 중 하나만 True 여도 True 반환
   ```

   **단축 평가** :pencil:

   첫 번째 값 (a) 이 확실할 경우, 두 번째 (b) 값은 확인하지 않음을 통해, 실행 속도를 증가 시킨다.

   ```python
   #1.
   False and True #a가 바로 false임으로, 뒤의 b를 검사할 필요 없이, 바로 false 반환
   #2. 
   True or False #a가 바로 true 이므로, 뒤의 b 검사 안하고 바로 true 반환
   ```

4. 복합 연산자

   ```python
   a += b
   a -= b
   a *= b
   a /= b
   a //=b
   a %= b
   a **= b # a=a**b
   ```

5. 기타 연산자

   - Identity

     ==는 값 자체만 비교하므로, True를 반환하고, is는 object를 검사하기 때문에(쉽게 말해서 주소) False를 반환한다.

   ```python
   a == b, a is b
   ```

    - slicing/indexing

      []을 통해서 값을 접근하고, [a:b]를 통해서 a~b-1까지의 값을 슬라이싱한다.

      ```python
      str_input="아이고 힘들다."
      str_input[0]
      str_input[0:3]
      ```

      

## 추가 공부

- **juypter notebook** 사용하는 이유?

  REPL(Read Eval Print Loop) 중에 하나

  markdown이랑 코드랑 같이 작성이 가능하고, 코드를 블락 단위로 실행이 가능하여서 사용한다.

  맨 아랫줄 표현식의 결과 값을 화면에 나타낸다 -> Out이라는 값과 함께

  print를 사용할 경우: 무조건 아래에 출력(Out)이 없다.


  만약 return이 없는 함수를 맨 마지막에 호출하거나 실행하였다?

  -> 당연히 Out도 출력되지 않는다



- 표현식

  내가 입력한 식이 어떤 하나의 값을 나타내는 식

- 문장 
  - 할당문: 어떤 변수에 어떤 값을 할당하는 코드-> 표현식은 아니다
  - not 할당문 : if radius >10: 처럼 그냥 문장
  - print문은 표현식. 화면에 출력하는 건 그냥 print의 역할! 어떤 값을 지정하지는 않는다, 다만 None이란 값을 가진다. (Out으로 나오지 않는다. )
