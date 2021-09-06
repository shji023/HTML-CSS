## 주요 선택자
### Type
```
tag이름 {

}
```
동일 tag가 모두 변경되기에 하나의 웹페이지에서 일관성있게 적용해야하는 경우에만 사용. 보통 css 상단부에 작성하는 것이 convention.

### Class
```
.class이름{
  color: blue;
}
```
- 중복 가능
```
.class이름 class이름{
  color: blue;
}
```
위의 경우에는 두번째 클래스 이름의 style적용
  
### ID
```
#id이름{
  color: blue;
}
```
- 유일해야됨 

## 속성선택자
속성 : HTML의 attribute
```
<a href="http://sample.com" target="_blink">
<a href="https://sample.co.kr" target="_blink">
1. 
a[target] {
  color: blue;
}

2. 
a[target="_blink"] {
  color: blue;
}

3. 문자열이 부분적으로 일치하더라도 선택되도록
a[href^="http"]{
    color: blue;
} //속성값이 http로 시작되는

a[href$=".kr"]{
    color: blue;
}//속성값이 kr로 끝나는

4. 적어도 하나
a[href*="sample"]{
    color: blue;
}//sample문자열을 가지고 있는
```

## 가상클래스 선택자
```
<div>
  <p class="hi">hi</p>
  <p class="hi">hello</p>
  <p class="hi">nice</p>
</div>

1. first-child 첫번째 자식
p:first-child {
  color:blue;
}
.hi:first-child {
  color:blue;
} //첫번째 hi의 클래스 이름을 지우면 아무 변경도 일어나지 않음. 형제들 중에서 첫번째 요소를 찾기 때문에

2. last-child 마지막 자식
p:last-child {
  color:blue;
}

3. nth-child n번째 자식
p:nth-child(2) {
  color:blue;
}
p:nth-child(2n-1) {
  color:blue;
}
p:nth-child(even) {
  color:blue;
}

4. first-of-type 첫번째 자식 
type들 중에 첫번째. 형제들 중에 첫번째를 찾지 않고 특정 타입들중에서 첫번째를 찾음. 형제들 중에서 태그를 섞어 쓸 경우에 사용
p:first-of-type{
 color: blue;
}
.클래스이름:first-of-type{
 color: blue;
} // 클래스 이름을 공유하지만 각각 다른 태그들 일 경우 각 태그의 첫번째 태그들 모두 다 선택됨

5. last-of-type 마지막 자식
p:last-of-type{
 color: blue;
}

6. nth-of-type 마지막 자식
p:nth-of-type(2n){
 color: blue;
}
```

### not
```
<form>
  <input class="username" type="email" placeholder="이메일">
  <input type="password" placeholder="password">
  <input type="submit">
</form>

input:not(.username){
    color: blue;
}
// input 태그 중 .username클래스 이름 가진 요소만 제외하고 스타일 적용하라.

input:not([type=email]){
    color: blue;
}
```

### link, visited
```
<a href="http://sample.com">sample</a>

a:link {
  color: green;
} //방문한적 없는 경우에만

a:visited {
  color: pink;
} //이미 방문한 경우
```

### hover, active, focus
```
<input type="button" value="click me">

input[type=button]:hover {
  background-color: green;
} //마우스를 올리면 색상 변경

input[type=button]:active {
  color: pink;
} //클릭할 때, 마우스 누르고 떼는 시점

input[type=button]:focus {
  color: pink;
} //특정 요소에 focusing되어있을 때
```
### enabled, disabled, checked
```
<input type="email" >
<input type="email" disabled>
<label>여성 :
<input type="radio">
</label>


input[type=email]:enabled {
  background-color: green;
} //활성화 되있는 요소에만 적용

input[type=email]:disabled {
  color: pink;
} //비활성화 되있는 요소에만 적용

input[type=radio]:checked {
  outline: 3px solid green;
} //특정 요소에 check되어있을 때
```

## 가상요소 선택자
실제로 존재하지 않는 요소나 범위를 만들어 적용
### before, after
```
<p class="fruit">apple</p>
<p class="fruit favorite">lemon</p>
<p class="fruit">banana</p>
<p class="fruit">orange</p>

.fruit::before {
  color: green;
} //가상의 존재에 스타일이 적용된 것임. 그러면 가상의 존재는 어디에?

.fruit::before {
  content: "Fruit";
  color: green;
} //복사를 해도 복사되지 않음

.favorite::before {
  content: "best";
} // 보통 뱃지나 메뉴사이의 구분 등에 사용. 꾸밈의 요소

after는 뒤에 생성됨
```
### fisrt-letter, first-line, selection
```
<p class="fruit">apple</p>
<p class="fruit">lemon</p>
<p class="fruit">banana</p>
<p class="fruit">orange</p>

.fruit::first-letter {
  font-weight: bold;
} // 첫번째 글자(a, l, b, o)만 진해짐

.fruit::before {
  content: "Fruit";
} // F가 진해짐

.fruit::first-line {
  font-weight: bold;
}  첫번째 라인만 진해짐

.fruit::selection {
  background-color: yellow;
  color: green;
} 요소를 드래그하면 스타일이 나타남
```

## 선택자 결합 - 하위, 자식
```
<div>
  <p>1</p>
  <p>2</p>
  <p>3</p>
<div>

//하위 - 스페이싱으로 구분
div p:last-of-type{
  color: green;
} // div 안에 있는 마지막 p

//자식 - 바로밑에 자식만 선택. 자손x
div > p:last-of-type{
  color: green;
}
```

## 형제 선택자, 그룹화
```
<div>
  <p>1</p>
  <span>2<span>
  <p>3</p>
  <p>4</p>
  <div>5</div>
<div>

1. 일반 형제 선택자 결합 : ~
span ~ p {
   color: green;
} // 앞에있는 선택자는 뒤에 있는 선택자보다 무조건 요소가 위에 있어야 함. 3, 4 변경됨

2. 인접 형제 선택자 결합 : +
span + p{
    background-color:green;
}//바로 인접한 경우만 변경.3 변경됨

3. 그룹화
p, span {
    color: green;
} // 여러개 한꺼번에 적용
```

## 범용 선택자
전체 선택
```
* {
 color: green;
}

class나 id 선택자는 이미 *. 이렇게 적용된 상태이지만 생략된 상태

p + * {
 //다른 선택자와도 결합 가능 
}
```

## 상속 제어하기- initial, inherit, unset
```
<div class = "parent">
  <p class = "child">1</p>
  <p class = "child">2</p>
</div>

1. initial

.parent {
  color: green;
} // 자식까지 모두 적용

.child {
  color: green;
} //다시 자식만 변경 가능

.child {
  color: initial; //상속 끊어내기 가능
  all : initial; //전체 상속 끊어내기
} 

2. inherit
.child {
  color: blue;
}

.parent * {
  all: inherit;
} 무조건 상속 받도록.

3. unset
부모로 부터 상속받아 적용된 부분만 제외하고 다 초기화
```

## 우선순위
1. 선언된 곳 <br />
   어떤 것을 더 마지막에 읽느냐에 따라
2. 명시도 높으면 적용범위 적음
   inherited < * < tag < Class/attribute/pseudo class< ID < inline style < !important(가장 강력)
3. 코드 위치
