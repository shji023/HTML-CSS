## 제목 H1 - H6
6단계의 구획 제목을 나타냄. h - heading 
```
<h1>Heading level1</h1>
<h2>Heading level2</h2>
<h3>Heading level3</h3>
<h4>Heading level4</h4>
<h5>Heading level5</h5>
<h6>Heading level6</h6>
```
> <h1>Heading level1</h1>
> <h2>Heading level2</h2>
> <h3>Heading level3</h3>
> <h4>Heading level4</h4>
> <h5>Heading level5</h5>
> <h6>Heading level6</h6>
### 기능
- 웹브라우저가 h1-h6태그를 사용해 자동으로 목차를 만드는 작업 가능하게함
- h1, h2... 순차적 기입 권장
- 글씨 크기를 위해 제목 태그 사용하지 말기 (css font-size 속성 사용)
  - 웹 브라우저마다 다른 글씨 크기를 갖기 때문
- 페이지 당 하나의 h1 태그 사용하기
  - 가장 중요한 제목이므로 전체 페이지의 목적을 설명, SEO에도 더 적합

## 본문
### p
하나의 문단을 나타냄. HTML에서 문단은 text로 구성되어 있지 않아도 이미지나 입력 폼 등 서로 관련있는 콘텐츠 무엇이나 가능
- 블록레벨 요소

고려사항
- 여백을 위해 \<p>태그 삽입 시 스크린리더 사용자에게 부정적 경험제공. 스크린 리더가 문단의 존재를 알려주지만 내용이 존재하지 않기에 혼란 야기.

### br : 줄바꿈 요소 line-break
텍스트 안에 줄바꿈을 생성.
- 빈 요소
- 여백을 늘리기 위해 \<br>을 많이 사용하면 안됨. css 활용하기

고려사항
- 문단 구분을 \<br>로 하는 것은 나쁜 사례, 문단의 구분을 위해서 p태그 사용하기 

### blockquote,q
공통적으로 인용 목적
차이점
- \<blockquote> : 블록
- \<q> : 인라인
```
<blockquote>이 부분은 blockquote를 활용한 인용문 입니다.</blockquote>

<q>이 부분은 q를 활용한 인용문 입니다.</q>
```
<blockquote>이 부분은 blockquote를 활용한 인용문 입니다.</blockquote>

<q>이 부분은 q를 활용한 인용문 입니다.</q>

*p태그 내부에는blockquote 사용x - p태그는 자식 태극 block요소이면 자동으로 p태그가 닫힘

**속성 Attribute**

`cite` : 인용문의 출처 문서나 메시지를 가리키는 URL, 인용문의 맥락 혹은 출처 정보를 가리킬 용도.

### pre - preformatted
미리 서식을 지정한 텍스트를 나타냄. HTML에서 작성한 내용 그대로 표현. 텍스트는 보통 [고정폭글꼴](#고정폭글꼴)을 사용해 렌더링, 요소 네 공백문자를 그대로 유지

**고정폭글꼴**

모든 글자가 고정된 폭을 가짐 
```
<pre>
  IIIII
</pre>
<p>
  IIIII
</p>
```
<pre>
  IIIII
</pre>
<p>
  IIIII
</p>

### figure, figcation
\<figure> 요소는 독립적인 콘텐츠를 표현한다. \<figcation> 요소를 사용해 설명을 붙일 수 있음
- \<pre> 나 \<blockquote> 처럼 자체로 독립적인 내용을 담고있는 태그를 묶어서 위나 아래에 설명을 붙일 때 사용
```
<figure>
  <pre>
    Bid me discourse, I will enchant thine ear, Or like a fairy trip upon the green, Or, like ..
  </pre>
  <figcation>by William Shakespeare<figcation>
</figure>
```
<figure>
  <pre>
    Bid me discourse, I will enchant thine ear, Or like a fairy trip upon the green, Or, like ..
  </pre>
  <figcation>by William Shakespeare<figcation>
</figure>

### hr
이야기 장면 전환, 구획 내 주제 변경 등, 문단 레벨 요소에서 주제의 분리를 나타냄
- 빈 요소

### abbr, address, cite, bdo
**\<abbr>** 

abbreviation (준말,약어)/ 이니셜 작성 후 원래 의미 나타낼 때 사용

```<abbr title="World Wide Web">WWW</abbr>```

<abbr title="World Wide Web">WWW</abbr>

*title속성은 global 속성으로 abbr 태그의 속성 뿐 만 아니라 p태그 등 여러 태그의 속성으로 사용 가능

<br/>

**\<address>**

주소. 메일, SNS, 웹사이트 통칭

```<address> website address : <a href="https://sample.com">sample</a></address>```
<address> website address : <a href="https://sample.com">sample</a></address>
*기본적으로 약간 기울여서 나타내짐

<br/>

**\<cite>** 

인용의 출처
  - blockquote의 속성 `cite`와 다른점 : 직접적으로 웹페이지에 명시함

<br/>

**\<bdo>**

bidirectional override
```<p><bdo dir="rtl">이 글은 오른쪽에서 왼쪽으로 작성합니다.</bdo></p>```

<p><bdo dir="rtl">이 글은 오른쪽에서 왼쪽으로 작성합니다.</bdo></p>
*rtl : right to left <br />
*ltr : left to right

## 포매팅
단순히 나열되어있는 문단이나 문장 중에서 특정 의미를 띄고 있는 경우 포매팅을 활용하여 주의를 끌거나 강조

### b, strong
**\<b>**

굵은 글씨 요소
- 요약 키워드, 리뷰의 제품명, 특별한 중요성을 가지고 있지는 않지만 굵게 표시할 부분에 사용
- 특정 부분을 강조하기 위해 사용해야함. 전체를 굵은 글씨로 적용해서는 안됨.

**\<strong>**

높은 중요도 요소
- 보통 굵은 글씨로 표현

### i, em
공통적으로 기울임꼴로 표시

**\<i>**

어떤 이유로 주위와 구분 해야하는 부분. 기술 용어, 외국어 구절, 등장인물의 생각 등

**\<em>**
텍스트의 강세를 나타냄
*strong 태그는 더욱 긴급한 내용

### mark, small, sub, sup
**\<mark>**

현재 맥락에 관련이 깊거나 중요해 표시 또는 하이라이트한 부분

```<p> 이 부분은 <mark>하이라이트</mark> 입니다.</p>```
<p> 이 부분은 <mark>하이라이트</mark> 입니다.</p>

- mark태그는 스크린 리더가 읽지 못함

**\<small>**

덧붙이는 글이나, 저작권과 법률 표기 등 작은 텍스트

```<p> 이 부분은 <small>덧붙임 글</small> 입니다.</p>```
<p> 이 부분은 <small>덧붙임 글</small> 입니다.</p>

**\<sup>**

활자 배치를 위 첨자로 해야 하는 인라인 텍스트 지정

```<p><var>a<sup>2</sup></var></p>```
<p><var>a<sup>2</sup></var></p>

**\<sup>**

활자 배치를 아래 첨자로 해야 하는 인라인 텍스트 지정

```<p><var>O<sub>2</sub></var></p>```
<p><var>O<sub>2</sub></var></p>

### del, ins, code, kbd
**\<del>**
문서에서 제거된 텍스트의 범위를 나타냄

```<p> 이 부분은 <del>제거된 부분</del> 입니다.</p>```
<p> 이 부분은 <del>제거된 부분</del> 입니다.</p>


**\<ins>**

문서에서 추가된 텍스트의 범위를 나타냄

```<p> 이 부분은 <ins>덧붙임 글</ins> 입니다.</p>```
<p> 이 부분은 <ins>덧붙임 글</ins> 입니다.</p>

**속성 Attribute**
- `cite` : 어떤 이유로 삭제가 되었는지 표시
- `datetime` : 변경된 일시 표시

**\<code>**

짧은 코드 조각을 나타내는 스타일을 사용해 자신의 콘텐츠를 표시
- pre태그 와의 차이점 : code - 인라인 코드 요소

```<p>The <code>push()</code> methods adds...</p>```
<p>The <code>push()</code> methods adds...</p>

<br />

**\<kbd>**

요소는 키보드 입력, 음성 입력 등 임의의 장치를 사용한 사용자의 입력을 나타냄

```<p>Please press <kbd>Ctrl<kbd></p>```
<p>Please press <kbd>Ctrl<kbd></p>

## a 태그와 하이퍼링크
HTML \<a>, 앵커 요소는 href특성을 통해 다른 페이지나 같은 페이지의 어느 위치 등 다른 URL로 연결할 수 있는 하이퍼링크를 만듬. \<a>안의 콘텐츠는 링크 목적지의 설명을 나타내야함
- 절대경로
  
  ```<a href="https://www.mozilla.com">Mozilla</a>```

  <a href="https://www.mozilla.com">Mozilla</a>
- 상대경로
  
  ```<a href="browser.md">browser 파일</a>```

  <a href="browser.md">browser</a>
- 이메일/전화
  
  ```<a href="mailto:sss@email.com">Send Email</a> <a href="tel:555-5309">(555) 5309</a>```

  <a href="mailto:sss@email.com">Send Email</a>
  <a href="tel:555-5309">(555) 5309</a>

`href` : 하이퍼링크가 가리키는 URL. 링크는 HTTP 혹은 HTTPS기반 URL일 필요는 없음. 
`target` : 링크한 URL을 표시할 위치. 목적지를 어디에 띄울 것인가
- `_self`: 기본값. URL이 현재 창에서 열림
- `_blank`: URL이 새 탭에서 열림

## Entity
HTML에 특수 문자 포함 <, >, ", & 등의 예약어를 그대로 표현하고 싶을 때 사용

`<` : \&lt; <br/>
`>` : \&gt; <br/>
`"` : \&quot; <br/>
`'` : \&apos; <br/>
`&` : \&amp; <br/>
`spacing` : \&nbsp;