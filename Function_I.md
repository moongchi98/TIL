# ![KakaoTalk_20210118_131607293 (3)](https://user-images.githubusercontent.com/77470429/105180887-786ef580-5b6e-11eb-8368-32076cf36c2f.jpg)
1/20 함수(Function) Part.I

# 함수(Function)

특정한 기능을 하는 코드의 집합! 재사용이 가능해서 용이!

## 1. 함수의 선언 & 호출

```python
#함수의 선언
def <함수이름> (parameter):
    <실행할 코드 블럭>
    return value

#함수의 호출
<함수이름>(parameter)
#예시
def hi(name):
    return (f'안녕!{name}'')
hi('나현')
    
```

return을 통해서 함수의 값(output)을 저장한다

## 2. 함수의 Output

함수는 항상 **한개의! 객체**(숫자,문자,리스트 종류는 상관없다!)만 반환한다.

:star: **Return**을 사용해야 output이 반환됩니다.

1. :pencil:**Return vs print **

   - Return

     함수가 의미하는 출력(output) 이다. 

   ```python
   def sum(a, b):
       result = a + b
       return result
   print(sum(1, 2))
   #출력 값 3
   ```

   함수 실행시 result에 a + b 값이 저장되어 반환한다.

   - Print

   우리가 실행하는 Terminal에 값을 나타내기만 할 뿐, print 자체는 어떤 값을 저장하지는 않는다

   그렇기 때문에 None을 반환!

```python
def sum(a, b):
    result = a + b
    print(result)
print(sum(1, 3))
#출력 값 :None
```

2.  Tuple 형태로 묶어서 반환

   ```python
   def sum(a, b):
       result = a + b
       return '합', result
   sum (1,3)
   #반환 결과('합',3)
   ```

   반환 결과가 여러개로 생각될 수도 있지만, 하나의 tuple로 묶여서 출력되는거다!

   return에서 여러개를 **,** 로 이어서 return 한다면 **한개의! tuple**로 반환된다

## 3. 함수의 입력

- 매개변수(parameter) & 인자(argument)

  ```python
  def lunch (menu):
      return (f'오늘의 점심은 {menu}')
  lunch('마라탕')
  ```

  menu는 매개변수, '마라탕'은 인자에 해당한다!

  input을 이용하여 입력값을 인자로 넘겨줄 수 있다!

- 기본 인자 값 (Default Argument Values)

  인자를 지정하지 않아도 기본 값을 설정하는 것!

  ```python
  def lunch (menu='마라탕'):
      return (f'오늘의 점심은 {menu}')
  lunch()
  #출력 : 마라탕
  ```

  단! 여러 매개변수를 사용할 경우, 기본 인자값 다음에 기본 값이 없는 인자를 사용할 수는 없다! 파이썬이 어떤게 어떤건지를 모르니까!

  ```python
  def lunch (menu='마라탕', dinner)
  #이러면 에러 발생
  ```

- 위치 인자 (Positional Arguments)

  함수의 기본. 지정해주는 위치 fun(x,y)  처럼 주어진 위치에 따라 인자가 판단된다.

- 키워드 인자 (Keyword Arguments)

  함수를 호출 할 때, 직접 변수를 명시하면서 사용할 수 있다.! 그렇다면 순서 무관!

  ```python
  def lunch (menu, dessert):
      return (f'오늘의 점심은 {menu},후식은 {dessert}')
  lunch(dessert='딸기',menu='마라탕')
  ```

- 여러 개의 인자 사용하기!

  1. 가변 인자 리스트(Arbitrary Arguments List)

     ```python
     print('방가방가')
     print('방가방가','내이름은')
     print('방가방가','내이름은','코난')
     ```

     print는 인자의 개수가 정해지지 않는다.

      매개변수에 *args(이름은 변경 가능, 다만 통상적으로 args 사용!)

     가변 인자 리스트는 매개변수 리스트의 마지막에 사용해야 한다. 

     tuple 형태로 처리된다.

     ```python
     def menus(*args):
         print(args)
     menus('제육','불고기','된장찌개')
     ```

  2. 가변 키워드 인자 (Arbitrary Keyword Arguments

     dictionary 형태로 처리가 된다. **kwarg를 매개변수로 사용한다.

     ```python
     def address(**kwargs):
         print(kwargs)
     address(시='서울',구='광진')
     ```

     
