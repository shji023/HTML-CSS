## 컨테이너 
**\<div>**

플로우 컨텐츠를 위한 통용 컨테이너. "순수" 컨테이너로서 아무것도 표현하지 않음
- 특징 : 의미를 가지고 있지 않다. 대신 다른 요소 여럿을 묶어 `class`나 `id`속성으로 꾸미기 쉽게 도움. 문서의 특정 구역이 다른 언어임을 표시. 블록 레벨 요소.

**\<span>**

구문 컨텐츠를 위한 인라인 컨테이너.

## 시멘틱 웹이란
- Semantic: 의미의, 의미론적인
- 요소의 의미를 고려하여 구조를 설계하고 코드를 작성한다. 

**의미론적 마크업 사용 시 이점**
- <b>검색 엔진</b>은 의미론적 마크업을 분석하여 페이지의 검색 랭킹에 영향을 줄 수 있는 중요한 키워드로 간주
- 시각 장애가 있는 사용자가 <b>스크린리더</b>로 페이지를 탐색할 때 의미론적 마크업 푯말로 사용할 수 있음
- 의미가 없는 끊임없는 `div`들을 탐색하는 것보다 의미있는 코드 블록을 찾는 것이 훨씬 쉬움
- 개발자에게 태그 안에 채워질 데이터 유형을 제안함
- <b>Semantic naming</b>은 적절한 정의요소/ 구성요소의 naming을 반영

## header, footer
**\<header>**

소개 및 탐색에 도움을 주는 콘텐츠. 제목 로고, 검색 폼, 작성자 이름 등의 요소 포함
- \<header> 내에 또 다른 \<header>, \<footer> 넣을 수 없음

**\<footer>**

일반적으로 구획의 작성자, 저작권 정보, 관련 문서 등의 내용을 담음
- \<footer> 내에 또 다른 \<header>, \<footer> 넣을 수 없음

## nav
문서의 부분 중 현재 페이지 내, 또다른 페이지로의 링크를 보여주는 구획을 나타냄. 주로 메뉴, 목차, 색인 등
- 보통 목록 태그 사용
  ```
  <nav>
    <ul>
      <li><a href="#">Home</a></li>
      <li><a href="#">About</a></li>
      <li><a href="#">Contact</a></li>
    </ul>
  </nav>
  ```
- \<footer>의 링크들은 모든 웹페이지에 전체를 아우를 수 있는 경우가 많지만 \<nav>링크들은 현재 페이지 기준

## aside
문서의 주요 내용과 간접적으로만 연관된 부분을 나타냄. 주로 사이드 바 혹은 콜아웃 박스로 표현
- 부가적인 정보이기에 없어도 크게 문제 되지 않음

## main
\<body>의 주요 컨텐츠를 나타냄
- 하나보다 많은 \<main>이 존재해서는 안됨
- InternetExplorer 지원 x
- 모든 컨텐츠를 포함하는 바깥에 위치

## article
독립적으로 구분해 배포하거나 재사용할 수 있는 구획. 게시판과 블로그 글, 메거진이나 뉴스 기사 등
- 하나의 문서가 여러개의 \<article> 가질 수 있음
- 보통 \<article>을 식별할 제목이 필요
- \<article> 안에\<section>사용가능
- \<section> 안에\<article>사용가능

## section
문서의 독립적인 구획을 나타내며, 더 적합한 의미를 가진 요소가 없을 때 사용한다. 
- \<article>으로 쓰일 수 없다면 \<section>으로 사용
- 보통 \<section>을 식별할 제목이 필요