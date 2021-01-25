# ![KakaoTalk_20210118_131607293 (3)](C:\Users\kwakn\Pictures\KakaoTalk_20210118_131607293 (3).jpg) 1/24 데이터 구조(Data Structure) II

## 세트(Set)

> mutable, unordered, iterable

1. 추가/삭제

   - .add(elem)

     elem을 set에 추가한다.

     ```python
     lunch = {'감자탕', '김치찌개'}
     lunch.add('고구마')
     print(lunch)
     >>>{'고구마', '김치찌개', '감자탕'}
     ```

   - .update(*others)

     여러가지 값을 추가하면서, iterable한 데이터를 전달해야한다!

     ```python
     lunch.update('된장찌개', '삼겹살')
     ```

   - .remove(elem)

     elem의 값을 삭제합니다.

     :wrench: elem이 set 안에 없을 경우, KeyError 

     ```python
     lunch.remove('김치찌개')
     ```

   - .discard(elem)

     remove와 동일하게 elem을 삭제하지만, 값이 없을 때 에러가 발생하지 않는다.

     :wrench: elem이 없을 경우 에러 없이 그냥 진행

     ```python
     lunch = {'감자탕', '고구마'}
     lunch.discard('김치찌개')
     print(lunch)
     >>> {'고구마', '감자탕'}
     ```

   - .pop()

     순서가 없으므로, 맨 마지막 원소가 아닌 **임의의 원소**를 제거해 반환한다.

     ```python
     lunch.pop()
     ```

     

## 딕셔너리(Dictionary)

> mutable, unordered, iterable

1. 조회

   - :star:**.get(key[,default]) **

     key에 해당하는 value값을 가지고 옵니다. 이 때, default 값을 설정해주면 key가 없을 경우

     default 값이 반환됩니다. 

     :wrench: 기본 default는 None으로, key가 없을 시 None이 반환

     ```python
     scores = {'math':80, 'science':50}
     scores.get('math')
     >>> 80
     scores.get('English',0)
     >>> 0
     ```

2. 추가 / 삭제

   - .pop(key[,default])

     key에 해당하는 값을 제거하고, 그 값을 반환한다. default를 설정해줄 경우, key가 없을 때 default가

     반환됩니다. 하지만, default 설정하지 않으면, key가 없을시 Key Error 발생

     :wrench: default 설정 X -> keyError, default 설정 O -> default 반환

     ```python
     scores = {'math':80, 'science':50}
     scores.pop('math')
     >>> 80
     scores.pop('english',0)
     >>> 0
     ```

   - .update()

     ({key:value}) 값을 제공하여, 기존의 key에 해당하는 value를 덮어씁니다.

     혹은 key가 없는 경우에는 추가됩니다.

     ```python
     scores = {'math':80, 'science':50}
     scores.update({'math':90})
     scores.update({'korean': 100})
     print(scores)
     >>> {'science' : 50, 'korean' :100, 'math': 90}
     ```



#### 딕셔너리 순회

딕셔너리에 for문을 사용하면 key값이 반환됩니다.

:question:왜? key값을 활용해서 value에 접근이 가능하기 때문!

```python
for subject in scores:
    print(subject)
>>> math
	korean
    science
```

```python
scores.keys()
>>>['math','science','korean']
scores.values()
>>>[90,50,100]
scores.items()
>>>[('math',90),('science',50),('korean',100)]
```

:star:**.items()를 사용하면 (key,value) 가 tuple형식으로 묶여서 반환**



#### Dictionary Comprehension

{}안에 조건문, 반복문을 활용해서 딕셔너리를 만들 수 있습니다.

```python
{'science' : 50, 'korean' :100, 'math': 90}
new_score = {key:value for key,value in scores.items() if value > 70}
print(new_score)
>>>{'korean': 100, 'math': 90}
```

