## 브라우저 

### 주요기능
- 사용자가 선택한 자원을 서버에 요청, 브라우저에 표시한다. 
- 자원의 주소는 URI(Uniform Resource Identifier)에 의해 정해짐

### 기본구성요소

![브라우저 주요 구성 요소](https://user-images.githubusercontent.com/60960130/131249653-ae4be9c5-e33b-4939-8e7e-8af828dc33db.png)

- 사용자 인터페이스 - URI를 입력할 수 있는 주소 표시 줄, 이전/다음 버튼, 북마크, 새로고침/로드중지 버튼/홈버튼 등.  요청된 페이지 창 제외한 나머지 모든 부분
- 브라우저 엔진 - 사용자 인터페이스와 렌더링 엔진 사이의 동작을 제어
- [렌더링엔진](#렌더링엔진) - 요청한 콘텐츠 화면에 표시. HTML 및 XML문서와 이미지를 표시 가능
- 통신 - 네트워크 호출에 사용됨(ex. HTTP 요청)
- UI 백엔드 - 플랫폼에서 명시하지 않은 일반적인 인터페이스로서, OS 사용자 인터페이스 체계를 사용.
- 자바스크립트 해석기 - 자바스크립트 코드를 해석 및 실행.
- 자료저장소  - 자료 저장, HTML5 명세에는 브라우저가 지원하는 '웹 데이터 베이스'가 정의되어 있다.

### #렌더링엔진

![렌더링엔진 동작과정](https://user-images.githubusercontent.com/60960130/131249776-d69a8467-832e-47cd-a422-febf0ff848b4.png)

- HTML문서 [파싱](#파싱)
- 태그→ [DOM](#DOM) 노드 변환
- 스타일 요소 파싱
- 렌더 트리 생성

*더 나은 사용자 경험을 위해 모든 HTML을 한꺼번에 파싱할때 까지 기다리지 않고 배치와 그리기 과정 먼저 시작 

### HTML 파서

HTML 파서는 HTML 마크업을 파싱 트리로 변환한다.

### #파싱

브라우저가 코드를 이해하고 사용할 수 있는 구조로 변환하는것

결과 : 파싱트리(parse tree), 문법 트리(syntax tree)

컴파일과정 : 소스코드 → 파싱 → 파싱트리 → 변환 → 기계코드

### #DOM 

문서 객체 모델 (Document Object Model)

예시

```jsx
<html>
  <body>
   <p>Hello World</p>
   <div><img src="example.png" /></div>
  </body>
</html>
```

![DOM트리](https://user-images.githubusercontent.com/60960130/131249833-d72c3f53-e651-4808-84d8-a0c908267043.png)

위의 과정을 통해 HTML 마크업은 DOM(Document Object Model)으로 변환되고, CSS 마크업은 CSSOM(CSS Object Model)으로 변환됨.

변환 후 렌더트리로 결합. 이를 기반으로 브라우저는 웹페이지에 표시

### Javascript 처리

렌더링 엔진 대신 자바스크립트 엔진이 담당 

**동작과정**

1. HTML 파서 : script 태그 부분에서 DOM 생성 프로세스 중지. 자바스크립트 엔진으로 제어 권한을 넘김. (자바스크립트 코드 실행 위해) 
2. 자바스크립트 엔진 : 제어 권한을 넘겨 받음. script 태그 내의 자바스크립트 코드 또는 script 태그의 src 어트리뷰트에 정의된 자바스크립트 파일을 로드, 파싱 후 실행. 
3. 자바스크립트의 실행이 완료 시 다시 HTML 파서로 제어 권한을 넘김. 브라우저가 중지했던 시점부터 DOM 생성을 재개.

브라우저는 동기(Synchronous)적으로 HTML, CSS, Javascript을 처리

[출처] <br/>
[https://developers.google.com/web/fundamentals/performance/critical-rendering-path/constructing-the-object-model?hl=ko](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/constructing-the-object-model?hl=ko)

[https://poiemaweb.com/js-browser](https://poiemaweb.com/js-browser)

[https://d2.naver.com/helloworld/59361](https://d2.naver.com/helloworld/59361)