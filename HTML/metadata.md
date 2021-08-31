## 메타데이터의 역할
데이터를 설명

## title
HTML \<title> 요소는 브라우저의 제목 표시줄이나 페이지 탭에 보이는 문서 제목을 정의. 텍스트만 포함할 수 있으며 태그를 포함하더라도 무시.
- 가능한 부모 요소 : 다른 \<title> 요소를 포함하지 않은 \<head>

즐겨찾기의 이름으로 들어감

### 페이지 제목과 SEO
페이지 제목은 SEO 에 큰 영향을 준다.
검색 엔진이 결과 페이지의 순서를 결정하는  구성 요소 중 하나가 페이지 제목.

제목 작성 요령
- 콘텐츠를 설명하는 문장을 넣기. 용어와 정의를 짝지어 넣기(하나 혹은 두개의 단어 x)
- 글자 수 제한(55~60 글자)
- 단순한 단어 나열 금지
- 제목의 중복 피하기

## meta tag
### 문서정보
HTML \<meta> 요소는 \<base>, \<link>, \<script>, \<style>, \<title>과 같은 다른 메타관련 요소로 나타낼 수 없는 메타데이터를 나타냄 <br />
- 빈 요소
  
**속성(Attribute)**
`name` : `name`과 `content` 특성을 함께 사용하면 문서의 메타데이터를 이름-값 쌍으로 제공할 수 있음. `name`은 이름, `content`는 값 담당
- 종류
  - `application-name`
  - `author`
  - `description`
  - `generator`
  - `keywords`
  - `referrer`

### 문자 인코딩
`charset` <br />
페이지의 문자 인코딩을 선언. 이 특성이 존재할 경우, "utf-8"의 대소문자 구분 없는 ASCII 으로 표현

### 뷰포트
```
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

- `width=device-width` :  웹페이지를 접속하는 기기의 가로와 실제 가로를 동일하게 (가로너비 꽉차게)
- `initial-scale` :  장치 너비와 뷰포트 너비의 비율을 정의
- `user-scalable` :  확대 가능 여부(yes/no)
  - `maximum-scale` / `minimum-scale` : 확대 비율 최대 최소 (0.0 ~ 1.0)
  
### MIME 타입
클라이언트에게 전송된 문서의 다양성을 알려주기 위한 메커니즘
예시
```
<link href="style/main.css" rel="stylesheet" type="text/css"> 
```
- `type="text/css"` : href="style/main.css" 문서의 경로만 가르킬 뿐 어떤 타입인지 명시해주지 않았기에 타입 속성을 활용하여 명시 

**일반적인 구조**
> type/subtype
- text/plain
- text/html
- image/jpeg
- image/png
- audio/mpeg
- audio/ogg
- audio/*
- video/mp4

## style
HTML \<style> 요소는 문서나 문서 일부에 대한 스타일 정보를 포함
```
<style>
p {
    color: blue;
}
</style>
```
\<style> 요소는 \<head> 안에 위치해야 하지만 일반적으로 외부 스타일 시트에 작성하고 \<link> 요소로 연결

## script
HTML \<script> 요소는 데이터와 실행 가능한 코드를 문서에 포함할 때 사용. 보통 JavaScript 코드 작성

- 외부 스크립트 연결
```
<script src="sample.js"></script>
```
- 내부 인라인 스크립트
  - head 또는 body에 위치 가능 (보통 body 마지막에 위치하는 것을 권장, 웹 브라우저에 다 렌더링 된 후 script실행시키기 위함)
```
<script>
  alert("Hello World!");
</script>
```