# ![KakaoTalk_20210118_131607293 (3)](C:\Users\kwakn\Pictures\KakaoTalk_20210118_131607293 (3).jpg) 01/27 Object Oriented Programming

## 1. 객체(Object)

Python에서 우리가 쓰는 모든건 객체이다.

객체는 타입(type), 속성(attribute), 조작법(method)를 가진다.

### 타입과 인스턴스

- 타입

  공통된 속성과 조작법을 가지는 객체들을 모아놓은거

- 인스턴스(Instance)

  특정 타입의 예시!!

  ```python
  number = 5
  type(number)
  >>> int
  ```

  

  :star: **type비교하기 **

  ```python
  #1.
  type(number) is int
  #2
  isinstance(number,type)
  ```

  특히 isinstance를 사용할 경우에는 (변수의 이름, type종류)를 입력해서 비교한다.



### 속성과 메서드

> 우리가 여태까지 list, string, dict등등에서 썼던 .함수()들이 메서드였다..!

- 속성

  객체의 상태/데이터를 의미하는데, 가장 대표적인게 복소수에서 실수/ 허수

  `object.attribute` 의 형식으로 사용한다.

  ```python
  complex_num = 5+4j
  complex_num.real
  >>>5.0
  complex_num.imag
  >>>4.0
  ```

  

- 메서드

  특정 객체에 적용할 수 있는 동작들을 의미한다.

  `object.method()` 형식으로 작성한다.

  ```python
  a = "Hi"
  a.replace('i',"")
  ```

  :heavy_plus_sign: 객체에 내장되있는 method나 attribute 확인하기

  ```python
  a = list
  dir(a)
  ```

  

## 2. 객체 지향 프로그래밍 (OOP)

> 매우 간단히, 내가 이해한대로만 기술하자면 **객체가 주인공이 되어서 모든 행동의 주체가 되게 코드를 짠다**

- 장점

  코드의 직관성 상승, 활용의 용이성, 변경의 유연성

  ```python
  #1
  my_upper('Hello')
  #2
  'Hello'.lower()
  ```

  2번이 객체 지향 프로그래밍의 예시이다. 1번의 경우 우리의 객체가 그냥 함수의 요소로 들어갔지만 (내 의미론 수동적인 상태) , 2번은 우리의 객체, 소문자로 바꿔라! 와 같이 행동의 주체가 된 느낌..!

### Class

type: 공통 속성을 가진 객체들을 분류해놓은 모음 (class)

class: 객체들의 분류(class)를 정의할 때 쓰는 키워드!

:star: class 생성법

```python
class Class_Name:
    pass
```

 :star: instance 생성법

```python
instance_name = class()
```

###  method 생성법  

> **instance를 사용할 경우에는 꼬옥 self사용!**

```python
class Animal:
    def groal(self):
        return'아르르르'
    
```

- :star:**매직매서드**

  __가 있는 메서드는 특별한일을 하기 위해 만들어진 메서드들이다!

```python
'__new__',
'__reduce__',
'__reduce_ex__',
'__repr__',
'__rmod__',
'__rmul__',
'__setattr__',
'__sizeof__',
'__str__',
```

- 생성자 메서드 **__init__**

  인스턴스 객체가 생성될 때 자동으로 호출되는 함수이다. 함수 안에 생성자를 활용해서

  자동으로 인스턴스의 속성을 정의할 수 있다.

  ```python
  def __init__(self, name):
      self.name = name
     #self는 필수! name은 필수가 아니다. name처럼 우리가 원하는 값을 이용가능
  ```

- 소멸자 메서드 __del__

  객체가 소멸될 때 자동으로 실행되는 함수

  ```python
  def __del__(self):
      print("빠이!")
  ```

- __str___(self)

  우리가 map을 출력할 경우에 `<__main__.Person object at 0x0000022B4F6A1E20>` 처럼 출력되는데, 

  이 것이 str때문!

  str메서드는 객체 출력시(print) 보여줄 내용을 정의해놓은 함수이다!

### 속성의 정의 

데이터나 클래스의 객체들이 가지게 될 상태나 데이터를 의미한다.

```python
class Animal:
    def __init__(self, name ='공룡'):
        #입력받은 name을 인스턴스 변수 self.name으로 할당
        #이렇게 되면 우리가 인스턴스 선언할때 name을 꼭 전달해줘야해!
        #물론, default 값도 설정 가능!
        self.name = name 
       
dog = Animal('굥아지')
```

:question: self 란?

인스턴스 자신을 뜻하는 것으로, 호출시 첫번째 인자로 인스턴시 자신이 전달되게 하는 것!



## 3. 인스턴스 & 클래스 변수

#### 인스턴스 변수

인스턴스의 속성이자 각 인스턴스들의 고유한 변수이다!

`self.변수명`으로 정의되고, 그렇게 사용된다!

```python
class Animal:
    def __init__(self, name ='공룡'):
        self.name = name # 인스턴스 변수!
```

#### 클래스 변수

클래스의 속성, 모든 인스턴스가 공유하며 클래스 선언 내부에서 정의된다!

`class이름.변수명`으로 정의!

```python
class Animal:
    poulation = 0 #이게 class 변수!
#호출법
Animal.population
```

```python
class Animal:
    types = "공룡"
    
    
tiger = Animal.() #인스턴스 선언
tiger.types
>>>'공룡'
tiger.types = '호랑이' #tiger인스턴스의 클래스 변수 값 변경
tiger.types 
>>> '호랑이'
Animal.types #클래스 변수 값 자체에는 영향 X
>>> '공룡'
```



:bulb: 이름공간 탐색 순서 : **인스턴스 -> 클래스**



## 4. 메서드의 종류

#### 인스턴스 메서드

말 그대루 인스터스가 사용하는 메서드! 일단 클래스 안에서 정의되는 메서드의 default는 인스턴스 메서드!

(나머지 애들은 골뱅이 붙여야해) 

:pushpin: **호출시 첫번째 인자로 self=자기자신이 전달되! 정의할때도 항상 써줘야해!**



#### 클래스 메서드

클래스가 사용하는 메서드! **`@classmethod`**를 사용해서 정의를 시작한다!

첫 번째 인자로, 클래스 자신 cls가 전달된다



#### 스태틱 메서드

클래스가 사용하는 메서드이긴 하지만, 호출시 어떠한 인자도 전달되지 않아!

즉, 우리가 지정해주지 않으면 작동 X `@staticmethod`로 정의 시작

```python
class Animal:
    
def instance_method(self):
    return self
@classmethod
def class_method(cls):
    return cls
@staticmethod
def static_method(anything):
    return anything
```

호출법

```python
#인스턴스 선언
Tiger = Animal()

#인스턴스
Tiger.instance_method()
#클래스
Animal.class_method()
#스태틱
Amimal.static_method(5)
#value 넣어줘야 스태틱 작동
```

인스턴스에서 클래식, 스태틱 메서드는 호출하지 말아라....접근은 가능하지만 그냥 하지마..



## 5. 상속

:star: **class의 가장 큰 특징**

부모클래스의 모든 속성이 자식 클래스에게 모두! 상속된다.

- 상속방법

  ```python
  class ChildClass(ParentClass):
  ```

- 상속확인방법

  ```python
  issubclass(ChildClass, ParentClass)
  ```

  대표적인 타입 비교함수들에도 상속 관계가 존재!

  ```python
  type(False) is int
  >>> False
  isinstance(False, int)
  >>>True
  ```

  isinstance는 False(boolean)값을 자동으로 0으로 변환해서 비교하여 true가 반환.

  하지만 type( ) is 는 같은 class인 경우에만 True 반환한다

#### 메서드 오버라이딩

> 기본적으로 자녀클래스는 부모의 모든 속성, 메소드를 사용이 가능하지만. 만약에 부모의 메서드에서 새로 추가하거나, 재정의할때는 상속받은 클래스에서 같은 이름의 메서드로 덮어 쓴다!

```python
class Animal:
    def __init__(self,name):
        self.name = name
    def groal(self):
        print(f'아르르!')
```

```python
class Dog(Animal):
    def __init__(self, name, type): #이렇게 type을 추가로 받고 싶을경우!
        self.name = name
        self.type = type
    def groal(self): #출력값을 바꾸고 싶을 경우
        print('멍멍!')

```

##### super()

그런데, 부모클래스의 내용을 사용하면서 진짜 하나만 추가하거나 이러면 코드를 전체 다 쓰는건 귀찮을 때 사용!

```python
class Animal:
    def __init__(self,name):
        self.name = name
    def groal(self):
        print(f'아르르!')
        
class Dog(Animal):
    def __init__(self, name, type): #이렇게 type을 추가로 받고 싶을경우!
        super().__init__(name) #원래있던 변수만
        self.type = type #추가한 변수만 정의
    
```



### 다중 상속

> 두개 이상의 클래스를 상속받을 때! 순서가 중요하다! 우선, 받은 부모클래스의 메소드, 속성은 다 사용가능

```python
class Mom:
    pass
class Dad:
    pass
class Baby(Mom,Dad):
    pass
```

