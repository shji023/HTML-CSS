## base
문서 안의 모든 상대 URL이 사용할 기준 URL을 지정. 문서에는 하나의 \<base>요소만 존재할 수 있음.
- 메타데이터 콘텐츠
- 전역 특성

`href` : 문서 내 상대 URL이 사용할 기준 URL. 절대 및 상대 URL 사용가능<br />
`target` : target 속성을 명시하지 않은 \<a>,\<area>,또는 \<form> 요소가 탐색을 유발했을 때 그 결과를 보여줄 기본 <u>브라우징 맥락</u>, 키워드나 저작자 정의 이름으로 지정<br />
*브라우징 맥락 - 브라우저가 Document를 표시하는 환경. 일반적으로 탭. 브라우저 창이나 페이지 내의 프레임도 가능
```
<head>
  <base href="https://github.com/shji023/TIL/" target="_blank">
</head>

<body>
  <a href="blob/main/HTML/aboutHTML.md"> About HTML Tag</a>
</body>
```

<head>
  <base href="https://github.com/shji023/TIL/" target="_blank">
</head>

<body>
  <a href="blob/main/HTML/aboutHTML.md"> About HTML Tag</a>
</body>

## noscript
페이지의 스크립트 유형을 지원하지 않거나, 브라우저가 스크립트를 비활성화한 경우 보여줄 HTML구획 정의
- 메타데이터 콘텐츠
- 전역 특성

```
<noscript>
  <p><a href="https://github.com/shji023">External Link</a></p>
</noscript>
<p>Hello!</p>
```
- 스크립트 활성화 상태
  <p>Hello!</p>
- 스크립트 비활성화 상태
  <p><a href="https://github.com/shji023">External Link</a></p>

## time
시간의 특정 지점 또는 구간을 나타냄. `datetime` 특성 지정
`datetime` : 요소의 시간 또는 날짜 값. 
- `datetime` 특성이 없는 경우 어떠한 자식 요소도 두어서는 안됨.
```
<p>The Orientation took place on <time datetime="2021-09-01 19:00">Sep 1</time>.</p>
```
<p>The Orientation took place on <time datetime="2021-09-01 19:00">Sep 1</time>.</p>

## var
수학 표현 또는 프로그래밍에서 변수의 이름 나타냄
```
width : <var>w</var>
height : <var>h</var>
```
width : <var>w</var>
height : <var>h</var>

함께 사용하는 요소 
- \<code>
- \<kbd>

## U
글자로 표현하지 않는 주석을 가진 것으로 렌더링 해야 하는 텍스트 나타냄. 맞춤법 오류 표시 등
*단순히 밑줄을 표시하기 위해서 사용해서는 안되며 밑줄을 추가하기 위해서는 css 사용하기
- 대부분의 경우 쓰지 않는 것을 권장

## data
주어진 콘텐츠를 기계가 읽을 수 있는 해석본과 연결
```
<p>Products</p>
<ul>
    <li><data value="78">cookie</data></li>
    <li><data value="79">candy</data></li>
    <li><data value="80">jelly</data></li>
</ul>
```
<p>Products</p>
<ul>
    <li><data value="78">cookie</data></li>
    <li><data value="79">candy</data></li>
    <li><data value="80">jelly</data></li>
</ul>

`value` : 기계가 읽을 수 있는 형태의 콘텐츠 해석본