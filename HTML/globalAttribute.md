제로 베이스의 'HTML - 전역속성' 강의를 듣고 내용을 정리하였습니다.<br />

전역 속성 : 어떤 tag에도 적용될 수 있는 속성
## class, id
고유 식별자. <br />
`id`
문서 전체에서 고유한 이름을 가지고 사용해야한다
- 공백이나 스페이스 탭 포함 불가
- 이름에서 의미를 구분하려면 _ 및 - 로 구분
  
`class`
문서 전체에서 여러 개의 태그가 같은 이름의 class 사용 가능
- 공백이나 스페이스 탭 포함 가능 (하나의 클래스에 여러개의 이름 사용할 때)
- 이름에서 의미를 구분하려면 _ 및 - 로 구분

## style
하나의 요소에만 스타일 속성을 적용할 때 사용. 하지만 외부 css에 작성하는 것을 권장

## title
추가 정보를 제공하는 텍스트
```
<div>
  <div title="hi">hi</div>
  <div>hello</div>
<div>

<div title="안녕">
  <div title="hi">hi</div>
  <div >hello</div>
<div>
```
<div title="hi">
  <div>hi</div>
  <div>hello</div>
<div>

<div title="안녕">
  <div title="hi">hi</div>
  <div >hello</div>
<div>

## lang
콘텐츠를 읽고 있는 사용자의 언어 명시. 웹 접근성을 높이기 위한 수단.

## data
data-*
존재하지 않는 속성 만들어서 사용. javascript가 접근하게 하기 위해

## draggable
- boolean값 명시 필수
```
<img src="sample.svg" draggable="false">
```
속성의 존재 이유 : js 에게 이벤트 발생으로 인식하지 않게 하기 위해

## hidden
시각적 방식 외에도 스크린 리더 등 다른 모든 표시 방식에서 숨겨짐.<br />
개발자 도구로 보면 존재 - 보안을 위해서 가리는 경우에는 hidden속성을 사용하면 안됨.<br />
*주의 : `display: flex`를 지정한 요소는 hidden 특성이 존재하더라도 화면에 보이게됨.