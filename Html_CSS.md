# 2월 1일 HTML & CSS

Hyper 상태: 데이터가 다중으로 연결되어있는 상태

Hyper Text : HyperLink를 통해 텍스트로 이동한다. 

Mark up: 태그 등을 이용하여 문서나 데이터의 구조를 명시하는 언어이다. 프로그래밍 언어와는 다르게 단순하게 데이터를 표기만 한다.



## HTML(Hyper Text Markup Language)

웹 페이지를 작성하기 위한 언어, 웹 컨텐츠의 의미와 구조를 정의한다.

#### :hotel: **기본구조**

```html
<!--html 작성 문서임을 알려주는 코드-->
<!DOCTYPE html> 
<html lang="ko">
<head> 
    	<!--인코딩 정보, 닫는 태그가 없다-->
       <meta charset="UTF-8">
    	<!--상단 탭의 제목-->
       <title>Document</title>
</head>
<body>
    <h1>
        <!--브라우저에 실제 나타나는 내용-->
         나의 첫번째 HMTL
    </h1>
    <!--네이버란 단어에 링크를 걸어준다!-->
    <a herf="https://www.naver.com">네이버</a>
        
</body>
</html>
```

+ vs code에서 **!**하고 Tab을 누르면 자동으로 양식이 촤라랏!

:person_with_blond_hair: **HEAD**

 문서 제목, 문자코드(인코딩)와 같이 해당 문서 정보를 담고 있으며, **브라우저에 나타나지 않는다. **

CSS선언 혹은 외부로딩 파일 지정등도 작성하다. 단순히 글자가 크고 굵은게 다가 아니라, 중요한 내용이란 것!

- Open Graph Protocol

  메타정보에 해당하는 제목, 설명 등을 쓸 수 있도록 정의. 카카오톡으로 링크보내게 되면 링크아래에 요약본으로 나오는 내용들있지? 그건 자동으로 컴퓨터가 head등에서 중요 내용을 뽑아내는거다!

:muscle:**Body**

실제로 웹 페이지에 나타나는 구조



:page_facing_up: **TAG & Element**

```html
<open_tag>내가 하고싶은 말들</open_tag>
```

대부분의 태그는 오픈태그와 닫는 태그로 이루어져있고, 그 사이에 내가 작성할 내용을 적는다!

여는태그+내용+닫는태그 = 요소

:fire: 속성(attribute)

```ht
<a href="https://google.com"></a>
```

```html
<a></a> <!--a 태그,링크를 만들어주는 역할-->
href <!--a 태그의 속성명-->
"https://google.com" <!--a 태그의 속성값-->

```

태그별로 속성이 다 다르다, 물론 같이 공용으로 사용되는 애들도 있다. (html global attribute)

 -> 그런데 작동 안할 수도 있다

속성명과 속성값의 구조는 마치 key,value같이 생겼다.  그러나, **공백은 절대 No! 쌍따옴표("")를 사용한다**



#### :star: **시맨틱태그(Semantic Tag)**

html5에서 의미론적 요소를 담은 태그들이 등장한다. 만능 div를 대체해서

물론 작성과정에서 시간이 더 오래걸릴 수도 있지만, 명시적이고 굉장히 알기 쉽다.

- non-semantic :`div`, `span` content에 대한 설명을 제공하지 x

  div는 divison의 약자, 각각의 블록을 형성해 레이아웃을 잡는 용도로 많이 사용된다. class 속성을 같이 사용!

  span 태그 사이에 객체가 들어간다면, 그 객체는 inline객체 (객체의 크기만큼만 공간이 할당된다)

- semantic : `h1`, `table`  content에 대한 설명을 자세히 제공

Html 5에서 새로 등장한 친구들중 대표적인 것을 알아보자

- header :문서 전체나 section의 상단에 위치하는 정보 영역
- aside :사이드에 위치하여, 메인콘텐츠와 관련성이 적은 콘첸츠를 나타낸다
- footer: 문서나 섹션의 하단 정보 영역



:globe_with_meridians: 시맨틱웹

웹에 존재하는 페이지들에 메타데이터를 부여해, 웹페이지를 **의미, 관련성** 을 가지는 데이터베이스로 구축



#### :atom_symbol: **Element**

1. 블록 요소

   하나의 태그가 전체 공간을 차지한다. 즉, 다른 태그가 그 공간에 이어서 올 수 없다.

2. 인라인 요소

   자신의 컨텐츠 너비만큼만 차지한다



#### :pencil: **text 관련요소**

1. 그룹 컨텐츠

   ```html
   <!-- 순서 있는 list -ol -->
   <ol>
      <li>떡볶희</li>
      <li>라면</li>
   </ol>
   <!-- 순서 없는 list ul -->
   <ul>
      <li>떡볶희</li>
      <li>라면</li>
   </ul>
   ```

2.  텍스트 관련 요소

   `<b>`와 `<strong>`의 비교

   `<b>` 는 글씨를 강조하면서, 중요한 의미라는 (sementic)역할도 한다,

   반면, `<strong>` 은 그냥 단순히 글자만 굵게!

   `<br>`은 줄바꿈!

3. 제목 과 문단

   ```html
   <!-- 제목 h1~h6 tag로 만들어준다 숫자가 커질 수록 글자가 작아져! -->
   <h1>
       나는야 제목!
   </h1>
   <!-- 문단 -->
   <p>
       p는 하나의 단락을 그룹핑하도록 해줘. 즉 단락을 만들어주지!
   </p>
   <hr> <!-- 나는 구분선을 추가해줭 -->
   ```

   



#### `<form>` 요소

form은 서버에서 제공될 데이터를 한번에 제공한다. 특히, 다양한 input 형식이 있다.

```html
<form action="#">
      <div>
        <label for="name">이름이 뭐에요</label><br>
        <input type="text" id="name" autofocus>
      </div>
      <div>
        <label for="region">사는곳은 어디에요</label><br>
        <select name="region" id="region">
            <option value="한국">한국</option>
        </select>
```

`<label>`을 통해서 form과 label을 연결한다. 

`<input>`에서 가장 중요하게 알아야할 것이, **type**이다!

type: 태그 모양을 다양하게 변경이 가능하다. radio, text, checkbox, password등이 있다.

id(혹은 name) : 태그 이름을 저장한다.

autofocus: 페이지가 실행되면 자동으로 이 속성에게 포커스 이동

`<select>`를 사용하면,  그 바 아래로 내려와서 하나 선택하는거,, 



:bulb: 아주 작은 vs 코드 팁

`ctrl+d` 중복되는 단어가 선택되어서 수정이 용이!

`shift+alt+위/아래` 그 코드 복붙,,

`Alt+b` 하면 페이지 실행

## CSS(Cascading Style Sheets)

:hotel: **기본구조**

```css
<style>
    p {
      color: red;
      border: 1px solid black;
    }
```

`;`으로 끝내는거 진짜 왕 중요!

#### :books: CSS 적용 방법

1. 인라인

```css
<h1 style = "color:red; font-size:20px;">제목이당<\h1>
```

​	태그 안에 직접 지정하여서 사용하고, html과 섞어서 사용한다!

2. 내부 참조

```css
<style>
*{
    color : red;
}
h2{
    color : orange;
}
.my-class {
    color : green;
}
#hello {
    color: blue;
}
```

`style` 태그 내부에 기입하는 방식을 의미한다. 

우선 쓴 코드가 가장 아래에 깔리고, 아래에 있는 코드가 제일먼저 보인다(우선순위를 배제하고)



3. **외부 참조** :star:

   외부의 css파일을 head에 선언한 link를 통해서 불러온다

   

#### :fork_and_knife: **선택자**

> html문서에서 특정한 요소를 선택하여 스타일링 하기위해서는 반드시선택자라는 개념이 필요

1. 기본 선택자

- 전체 선택자 `*`
- 요소 선택자 `element이름`

- 클래스 선택자 `.class이름`

  클래스 선택자는 마침표문자로 시작하면, 해당 클래스가 적용된 문서의 모든 ㅎ아목을 선택

- id 선택자 `#id이름`

  #문자로 시작하며 기본적으로 클래스 선택자와 같은 방식으로 사용

  그러나, id는 문서당 한번만 사용할 수 있으면 요소에는 단일 id값만 적용할 수 있다.

#### css 적용 우선순위

1. 중요도(importance)

   ```html
   h2{
         color:darkviolet !important;
      }
   ```

   `!important` 

   정말정말특수한 상황에만 사용-> 질서를 다 무시하는 거이므로!

2. 인라인

3. id 선택자

4. **class 선택자** 

   강추 맨..

5. 요소 선택자



#### :family: CSS 상속

자식 요소 프로퍼티는 부모의 프로퍼티를 모두 상속받지 않는다! 받는거, 안받는거 구분이 중요하다.

- 상속 :ok_hand:

   text관련요소(font,color,text-align)

- 상속 :x:

  box model(width, height, margin,padding,border..)

  position 관련 요소



#### (상대)크기 단위

- px(픽셀)

- %

- **em**

  요소에 지정된 값이 기준이 된다. 상속되었다면 그 값의 배수, 배수가 되므로 원하는 값과 달라진다.

  ```html
  <style>
      .em {
        font-size: 1.5em;
      	}
  <ul class="em">
      <li class="em">1.5em</li>
      <li class="rem">1.5rem</li>
  ```

  class em의 경우에는 상속을 받아 원래 16에서 * 1.5 * 1.5 배가 된 값의 px을 가지게 된다.

- **rem** 

  최상위 요소(html)의 사이기준으로 배수 단위를 가짐 (html은 16px이 기본)

  ```html
  html{
        font-size: 16px;
        padding:10rem;
      }
  <!-- 160px이 된다 -->
  ```

  

#### BOX MODEL구성

1.MARGIN

테두리 바깥의 외부 여백, 배경색을 지정할 수 없다

2.BORDER

테두리 영역

3.PADDING

테두리 안쪽의 내부 여백 요소에 적용된 배경색,

4.CONTENT

글이나 이미지등 요소의 실제 내용



박스 모델의 구성은 4방향!

```css
.margin{
	margin-top :10px;
	margin-rigth:20px;
    margin-bottom:30px;
    margin-lefet:40px;
}
.border{
    border-width:2px;
    border-style:
        
}

```

shorthand를 통해서 표현 가능!

```css
/*값 하나는 상하좌우*/
.margin{
    margin:10px;
}
/*값 두개는 상하/좌우*/
.margin{
    margin:10px 20px;
}
/*값 세게는 상/좌우/하 */
margin{
    margin:10px20px30px
}
/*네개는 상우하좌*/
margin{
    margin:10px20px30px40px
}
```



:straight_ruler: width 측정

​	CSS는 그 content자체의 width를 측정한다.

​	-> 실제로 출력은 border를 포함하므로, 우리의 원하는 것과는 다른 사이즈!

​	우리는 그래서 border까지 포함하는 방법을 box-sizing으로 설정한다.

```css
box-sizing: border-box;
```



+ 마진 상쇄

  형제끼리 마진이 덮어씌워짐(큰 값의 애로)

  top bottom에서만 상쇄



# css display

1. `display:block`

   줄바꿈이 일어나는 요소

   화면전체의 가로 요소를 차기 =< 기본 넓이의 100% 나머지는 margin이 되는거야

   `div`, `ul` ,`ol` ,`li`, `p` ,`hr`, `form`

2. 인라인 요소

   콘텐츠 영역 만큼만! 특성상 너비, 마진값 줄 수 없다

   `span`,  `a`,  `img`



`inline-block:` 부모 너비를 전부다 차지 x

기본적으로는 inline의 너비와 높이를 가지지만, 지정해서 width,height를 변경할 수 있다.