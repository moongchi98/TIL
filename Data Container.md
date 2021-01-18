# ![KakaoTalk_20210118_131607293 (3)](https://user-images.githubusercontent.com/77470429/104927396-b93b0300-59e4-11eb-9f0e-c1dd23dfb1dc.jpg) 1/18 Data Container

## 시퀀스형(Sequence) 컨테이너

:question: 시퀀스란?

순서가 정해진! ordered된 형식을 의미합니다. 정렬되어있는 sorted랑은 다름!

**특정 위치의 데이터를 지목할 수 있다**는 점이 매우 유용합니다.

- 종류

  1. 리스트 (list)

     **[ ]** : 대괄호 안에 , 로 데이터를 구분한 형태.

     - list 만들기

       ```python
       lunch =['불고기', '쌈밥']
       num_list=list('123456')
       ```

     - list 요소 접근

       ```python
       lunch[0]
       ```

       index 사용! **index는 무조껀 0부터 시작!**

     - list 항목 변경 및 추가

       ```python
       #추가
       lunch.append('마라탕')
       #변경
       lunch[1]='보쌈'
       ```

     - list 항목 확인

       ```python
       '보쌈' in lunch # 항목이 list에 있는지 확인, bool형 반환
       #항목 개수 세기
       list.count('마라탕')
       ```

     - list 항목 제거

       ```python
       data_list=[1,2,3,4,5,6]
       del data_list[0:3]
       #0번 부터 2번까지의 항목 제거
       data_list.pop(0)
       # index 번호를 int 형으로 입력-> 해당하는 idx의 값이 지워진다.
       data_list.remove(3)
       #()안에 있는 값을 가진 모든 항목을 제거 한다.
       ```

  2. 튜플 (tuple)

     **()** 안에 , 로 데이터를 구분한 자료형

     **수정**이 불가능하다(immutable) 

     ```python
     vegi=('감자','고구마'.'콩나물')
     vegi[0]='시금치'
     #TypeError 발생
     ```

     

     동시에 여러 변수의 값을 받거나, 값을 교환할때 튜플이 활용된다.

  3. 레인지(range)

     range (a, b, i) 

     a~b-1까지의 숫자까지, i 만큼의 스텝을 가지고 증가(감소) 한다.

- 시퀀스에서 사용하는 연산자/함수

  ```python
  #특정 원소가 포함되어 있는지 확인
  'i' in 'icecream' # True 반환
  'i' not in 'icecream' #False 반환
  #최소, 최대, 길이
  max(data_input)
  min(data_input)
  len(data_input)
  ```

  

## 비 시퀀스형(Non-sequence) 컨테이너

- 종류

  1. set

     순서가 없다! **{}** 중괄호를 통해 생성하고, **중복된 값**을 허용하지 않는다.

     빈 집합을 생성하기 위해서는 {}이 아닌, set() 으로 생성

     :star: **집합** 과 매우 유사.

     - 차집합

       set_1 - set_2

     - 합집합

       set_1 | set _2

     - 교집합

       set_1 & set_2

     set을 활용해서 list의 중복된 값들 제거 가능



2. Dictionary

   **{ }안에 key,value**로 이루어져있다.

   index가 아니라 key로 접근!

   ```python
   age= {'나현':23, '세현':26, '수민':24}
   #key값들 확인하기
   age.keys()
   #value값을 확인하기
   age.values()
   #items로 튜플로 이루어진 key,value 얻기
   age.items()
   ```

   

## 데이터의 분류

#### 변경 불가능한 데이터 vs 변경 가능한 데이터

- 변경 불가능한 데이터
  1. 리터럴 (숫자, 글자, bool)
  2. range
  3. tuple
- 변경 가능한 데이터
  1. list
  2. dict
  3. set
