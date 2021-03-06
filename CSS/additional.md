## border-image
주위에 이미지를 그림, 일반 테두리를 대체함[shorthand]
- border-image-source
- border-image-slice
  - 이미지를 여러 개의 영역으로 나눔. 나눠진 영역이 요소의 테두리 이미지를 이룸
  - 한개의 값 : 모든 분할선의 위치가 각각의 기준 모서리에서 동일한 거리만큼 떨어진 곳
  - 두개의 값 : 상하분할선 좌우분할선
- border-image-width
  - 한개의 값 : 상하좌우
  - 두개의 값 : 상하 좌우
- border-image-outset
  - 테두리상자와 테두리 이미지의 거리 설정
- border-image-repeat
  - 모서리 영역을 요소의 테두리 이미지 크기에 밎춰 조절
```
border-image: url("/sample.png")
```

## @supports
CSS 규칙은 주어진 하나 이상의 CSS 기능을 브라우저가 지원하는지에 따라 다른 스타일 선언을 할 수 있게하는 방법 제공. 
```
HTML
<section>
  <h1>브라우저가 CSS variables를 지원하면, 텍스트는 파란색일 것이고 그렇지 않으면 회색일 것입니다.</h1>
</section>

section {
  color: gray;
}
CSS
@supports(--css: variables) {
  section {
    --my-color: blue;
    color: var(--my-color, 'blue');
  }
}
```

## Darkmode
- prefers-color-scheme : 미디어 쿼리를 통해 감지 
  - like - 라이트 모드인지
  - dark - 다크 모드인지 

## clear
```
clear:both;
```
float한 박스들의 바로 아래 박스에게 주변을 흐르지 않고 원래대로 배치하도록 하는 속성

## white-space
스페이스와 탭, 줄바꿈, 자동 줄바꿈 처리 속성  
- normal : 연속 공백을 하나로 합침.
- nowrap : 연속 공백을 하나로 합침. 줄바꿈은 br요소
- pre : 연속 공백 유지. 줄바꿈은 개행과 br요소
- pre-wrap : 연속 공백 유지, 줄바꿈은 개행과 br요소, 자동줄바꿈
- pre-line : 연속 공백 하나로 합침, 줄바꿈은 개행과 br요소, 자동 줄바꿈

## clip-path
요소의 클리핑 범위를 지정. 클리핑 범위 안의 부분은 보여지고 바깥은 숨겨짐
```
clip-path: circle(40%);
clip-pthr: url("sample.svg");
```

## will-change
요소에 예상되는 변화의 종류에 관한 힌트를 브라우저에 제공
```
will-change: scroll-position;
will-change: content;
```
scroll-position : 스크롤 위치의 변경에 대한 기대
content : 요소의 내용 대한 변경 기대
- 브라우저가 미리 변이를 준비하게 해 원할하고 역동적인 애니메이션이 가능하게 함