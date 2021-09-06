## CSS
Cascading Style Sheets<br />
모듈별(font, table, animation)로 각자 버전 존재 - 웹 브라우저마다 다를 가능성이 있음<br />
**Cascading**(위에서 아래로 흐름) - 여러개의 스타일이 하나의 요소에다가 적용되어 있음. 이 중 어떤 스타일을 채택할 것인지 규칙 필요. 또한 위에서 적용한 스타일을 아래에서 가지게 됨. 
- 룰 기반의 언어<br />
  셀렉터 {<br />
    속성 : 값;<br />
  }
- 특정 요소(selector를 통해 선택) 및 집합의 스타일 규칙 적용 가능
- 주석 : /* */

## 적용 방법
1. embedded
  ```
  <head>
    <style>
    p {
        color: blue;
    }
    </style>
  </head>
  ```
2. inline <br />
   지양하는 방법
  ```
  <body>
    <p style="color:blue">hi hello</p>
  </body>
  ```
3. external <br />
   권장하는 방법
  ```
  <head>
    <link rel="stylesheet" href="style/main.css"/>
  </head>
  ```
   `rel`: 현재 파일과 외부 파일의 관계 명시

## Cascading 원칙
1. 스타일 우선순위
   - 브라우저에서 정의된 스타일(user agent) < 개발자가 선언한 스타일 < 사용자가 구성한 스타일
   - tag < class스타일 < id스타일 <인라인 스타일
   - 소스코드의 순서가 뒤에 있으면 덮어씀
2. 스타일 상속
   - 부모요소의 스타일 속성이 자식요소로 전달
     - 자식에서 재 정의하면 부모의 스타일 덮어씀
   - 상속이 되지 않는 속성이 있음(배경 이미지, 배경 색 등)
   
