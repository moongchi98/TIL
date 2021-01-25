# ![KakaoTalk_20210118_131607293 (3)](https://user-images.githubusercontent.com/77470429/105714360-93bb7580-5f5f-11eb-8e53-032d608ac77d.jpg)1/24 데이터 구조(Data Structure) I

> 순서가 있는 데이터 구조는 알고리즘에 빈번히 사용된다. 문자열(String), 리스트(List)가 해당! 
>
> :heavy_check_mark: 비슷한 동작을 하지만, 없는 데이터에 대해서 에러가 발생하는 메소드나 
>
> defaul 값을 return하는 메소드가 있다! 그걸 비교해서 현명하게 사용해야해!

## 문자열(String)

> immutable, ordered, iterable

1. 조회/탐색 

   - **.find(x)**

     문자열 안에서 x가 처음으로 나타나는 위치를 반환한다. 

     :wrench: 기본 값: 값이 없을 경우 -1	

   ```python
   word = 'hello!'
   word.find('h')
   >>> 0
   word.find('a')
   >>> -1
   ```

   - **.index(**)

     find와 동일하게, 문자열 안에서 x가 처음으로 나타나는 위치를 반환한다.

     :wrench: 기본 값:  에러발생

     ```python
     word = 'hello'
     word.index('a')
     >>> ValueError
     ```

2. 값 변경

   - **.replace(old,new[,count])**

     함수에서 []로 써있는 부분은 꼭 지정해주지 않아도 된다는 값.

     바꿀 대상을(old), 새로운 글자로(new) 바꿔서 출력한다. 이 때, count를 통해 변경할 횟수를 지정가능

     ```python
     word = 'hello'
     word.replace('l','') #l을 공백으로 변경
     >>> 'helo'
     word.replace('l','',2)
     >>>'heo'
     ```

   - **.strip([chars])**

     lstrip은 왼쪽의 지정해준 문자(chars)를 제거하고, rstrip은 오른쪽을 제거한다. strip의 경우 양쪽을

     제거한다. 

     :wrench: 기본 값: 공백

     이때, \n, \t와 같은 이스케이프 시퀀스도 삭제된다!

     ```python
     greeting = "		안뇽!\t"
     greeting.strip()
     >>>"안뇽!"
     ```

   - **:star:.split()**

     ()안에 문자열을 나누어줄 단위를 지정해준다. 나누어준 값들을 **리스트**로 반환한다!

     :wrench: 기본 값: 공백, 리스트 반환

     ```python
     greeting = "안녕 하세요 내 이름은"
     greeting.split()
     >>>['안녕','하세요','내','이름은']
     
     numbers = "1, 2, 3"
     numbers.split(", ")
     >>>['1','2','3']
     ```

   - :star: **'separator'.join(iterable)**

     list,string과 같이 반복가능한 각 요소들을 separator에 해당하는 구분자로 합쳐서 **문자열**로 반환!

     :wrench: 기본 값: 문자열 반환

     ```python
     greeting = "아이고 피곤해"
     ",".join(greeting)
     >>> "아,이,고, ,피,곤,해"
     numbers = ['12','34']
     "".join(numbers)
     >>>"1234"
     ```

     

3. 문자 변형

   - .capitalize()

     앞글자만 대문자로 변형하고, 나머지는 다 소문자로 바꿔 반환해준다.

     ```python
     news = "today is Monday!"
     news.capitalize()
     >>> "Today is monday!"
     ```

   - .title()

     '(어포스트로피)나 공백 이후 글자를 대문자로 만들어 반환한다.

     ```python
     news = "It's my birthday!"
     news.title()
     >>> "It'S My Birthday!"
     ```

   - .upper() / .lower()

     모두 대문자(upper)나 소문자(lower)로 만들어 반환한다.

     ```python
     greeting = 'heLlO'
     greeting.upper()
     >>>'HELLO'
     greeting.lower()
     >>>'hello'
     ```

   - .swapcase()

     대문자를 소문자로, 소문자를 대문자로 변경해 반환한다.

     ```python
     greeting = 'heLlO'
     greeting.swapcase()
     >>>"HElLo"
     ```

     

4. 문자열 검증 메소드

   .isalpha(), .isdecimal(), .isdigit()m .isnumeric(), .isspace(), .istitle(), .islower()

   다양하게 있지만 자주 쓰는 두개만 알아보자!

   - 문자인지 확인

   ```python
   'a'.isalpha()
   >>>True
   ```

   - 숫자인지 확인

   ```python
   '3'.isdigit()
   >>>True
   ```

   

## 리스트(List)

> mutable, ordered, iterable

1. 값 추가/ 삭제

   - :star: **.append(x)**

     x를 list의 맨 마지막에 추가한다. 

     ```python
     menu = ['떡볶이', '감자탕']
     menu.append('오뎅탕')
     print(menu)
     >>>['떡볶이', '감자탕', '오뎅탕']
     ```

   - **.extend(iterable)**

     list, string, tuple, range와 같이 반복가능한 데이터를 list에 추가하는 것!

     여러개 추가할때 용이

     :warning:string의 경우 각 문자별로 쪼개져서 들어간다!

     ```python
     menu.extend(['비빔면','짬뽕'])
     print(menu)
     >>>['떡볶이', '감자탕', '오뎅탕', '비빔면','짬뽕']
     menu.extend("오늘뭐먹지?")
     >>>['떡볶이', '감자탕', '오뎅탕', '비빔면','짬뽕','오','늘','뭐','먹','지','?']
     ```

   - .insert(i, x)

     정해진 위치(i)에 값 x를 추가한다

     이 때, 맨 마지막에 추가하고 싶을 경우, i = len(list)

     :wrench: 고정 값: list의 길이를 벗어나는 i 값에서는 맨 마지막에 아이템이 추가된다 -> 기존 list 길이 기준

     ```python
     menu = ['짬뽕', '짬짜면']
     menu.insert(1,'탕수육')
     print(menu)
     >>>['짬뽕', '탕수육','짬짜면']
     ```

   - .remove(x)

     값이 x인 값을 list에서 삭제한다. 단, 앞에서 부터 딱 한번만!

     :wrench: x가 list에 없을 경우, ValueError 발생

     ```python
     numbers = [1, 1, 2, 3, 4]
     numbers.remove(1)
     print(numbers)
     >>>[1, 2, 3, 4]
     ```

   - :star:**.pop(i)**

     정해진 위치 i의 해당하는 값을 삭제하며, 이 때 삭제한 값을 반환한다.

      remove는 값을 지정해주고 삭제, pop은 인덱스를 지정해주고 해당 값을 삭제 & 삭제한 값 반환!

     :wrench: 지정해주지 않을 경우, 마지막 항목을 삭제한다.

     ```python
     numbers = [1, 2, 3, 4]
     del = numbers.pop() #삭제되는 값이 반환된다는 것 이용
     >>> 4
     print(numbers)
     >>> [1, 2, 3]
     print(f'삭제된 값은 {del}입니다.' )
     ```

   - .clear()

     모두 삭제

     ```python
     numbers.clear()
     ```

     

2. 탐색/ 정렬

   - .index(x)

     x값을 찾아 그 index를 반환

     :wrench: x가 없을 경우 ValueError 발생

     ```python
     numbers = [1, 2, 3]
     numbers.index(2)
     >>> 1
     ```

   - :star: **.count(x)**

     list 안의 x 값의 개수를 반환

     ```python
     numbers = [1, 1, 3, 4, 1]
     numbers.count(1)
     >>>3
     ```

   - .sort()

     오름차순으로 정렬한다. 원본 list를 변형시킨다.

     :wrench: None을 리턴, 원본 변형

     ```python
     age = [13, 28, 14]
     age.sort()
     print(age)
     >>[13, 14, 28]
     ```

   - .reverse()

     list를 반대로 뒤집는다 ! 정렬해서 말고 그냥!

     ```python
     name = ['세현','나현','후준']
     name.reverse()
     print(name)
     >>>['후준','나현','세현']
     ```

3. **:question: 리스트복사**

   list를 얕은 복사할 경우에는 id가 동일해서, 하나를 수정할 경우 복사본도 수정된다

   다시 말해, list, dict, set와 같은 mutable 데이터들을 복사할 경우에는 주의가 필요하다

   ```python
   origina_list = ['a', 'b', 'c']
   copy_list = original_list
   copy_list[0] = 'z'
   print(copy_list, original_list) 
   >>> ['z', 'a', 'b', 'c'] ['z', 'a', 'b', 'c']
   ```

   :heavy_check_mark: 다만 새로운 list를 생성해서 복사할 경우에는 id가 달라진다.

   리스트 복사 방법

   - slice[:] 사용

   ```python
   numbers = [1, 2, 3, 4]
   new_numbers = numbers[:]
   new_numbers[0] = 10
   numbers[2]= 50
   print(new_numbers, numbers)
   >>>[10, 1, 2, 3, 4] [1, 2, 50, 3, 4]
   ```

   - list() 사용

   ```python
   numbers = [1, 2, 3, 4]
   new_numbers = list(numbers)
   ```



​	:warning: **shallow copy의 한계-> 2차원 배열**

​	list 안의 list처럼 2차원 배열에서는, 위의 방법으로 copy를 할 경우, 가장 큰 1차원 배열은 id가 다르지만

​	안의 배열은 동일 id기 때문에, 수정사항이 그대로 반영된다.

```python
l1 = [[1, 2, 3], 4, 5]
l2 = list(l1)
l2[2] = 6
l1[0][1] = '이거'
print(l1,l2)
>>>[[1, 이거, 2, 3], 4, 5] [[1, 이거, 2, 3], 4, 6, 5]
```



**깊은 복사** 

안의 모든 mutable도 새롭게 값이 변경된다.

```python
import copy
l1 = [[1, 2, 3], 4, 5]
l2 = copy.deepcopy(l1)
l2[2] = 6
l1[0][1] = '이거'
print(l1,l2)
>>>[[1, 이거, 2, 3], 4, 5] [[1, 2, 3], 4, 6, 5]
```



4. :star: **List Comprehension **

   []안에 표현식과 제어문을 통해서 리스트를 생성한다.

   ```python
   odd_list = [i for i in range (1,11) if i % 2 == 1]
   print(odd_list)
   >>>[1, 3, 5, 7, 9]
   ```



## Iterable 데이터 구조에 적용가능한 Built-in-Function

### map(function, iterable)

순회가 가능한 데이터 (iterable)에 포함된 모든 요소에 function을 적용하여 결과를 반환한다

```python
a = map(int,input().split())
#input받은 문자열을, int함수를 적용시켜 int로 변경해서 반환
```

### filter(function, iterable)

iterable의 포함된 요소에서 function을 적용했을 때 True인 것들만 반환한다.

사용자 정의 함수를 function으로 사용 가능

```python
def even(n):
    return n % 2
number = [13, 14, 15]
even_num =  list(filter(even, number))
print(even_num)
>>> [14]
```



### zip(*iterables)

여러개의 iterable 객체를 모아 tuple로 구성된 결과를 반환한다.

```python
a = ['사과', '딸기']
b = ['꿀', '우유']
pair = list(zip(a,b))
```

