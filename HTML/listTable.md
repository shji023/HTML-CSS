제로 베이스의 'HTML - 목록과 표' 강의를 듣고 내용을 정리하였습니다.

## 목록
### ul - unordered list
```
<ul>
  <li>첫번째 목록
  <ul>
    <li>하위 목록
    <ul>
      <li>그 다음 하위 목록
    </ul>
  </ul>
</ul>
```
<ul>
  <li>첫번째 목록
  <ul>
    <li>하위 목록
    <ul>
      <li>그 다음 하위 목록
    </ul>
  </ul>
</ul>

### ol - ordered list
정렬된 목록. 기본적으로 숫자 목록<br />
`type` : 1, A, a, I, i 사용가능<br />
`start` : 시작하는 숫자 설정 가능<br />
`reversed` : 순서 역전. boolean으로 표현
### li
각각의 단일 아이템 표현<br />
`value` : 시작하는 숫자 설정 가능. 개별 아이템 숫자 변경 가능



## 정의 목록 d - definition, description
### dl, dt, dd
설명 목록. ul, ol 과 달리 두개의 자식 태그를 가질 수 있음. 주로 용어 사전 구현이나 메타데이터(키-값 쌍 목록) 표시
```
<dl>
  <dt>용어</dt>
  <dd>설명</dd>
</dl>
```
<dl>
  <dt>용어</dt>
  <dd>설명</dd>
</dl>

- 하나의 용어 하나의 설명 
- 하나의 용어 여러개의 설명 
- 여러개의 용어 하나의 설명
- 여러개의 용어 여러개의 설명 가능 
- 하나의 그룹은 div로 감싸기 가능
  - dt와 dd의 형제로 div를 사용하면 안됨

## 표
table 태그를 가지고 layout을 만드는 것은 지양. 복잡한 자료를 한눈에 정리할 때만 사용하기
### table tr th td
**\<tr>** : table row (행, 가로줄)<br />
**\<th>** : table head (행이나 열을 대표하는 요소)<br />
**\<td>** : table data <br />
구획 가능
**\<thead>**
**\<tbody>**
**\<tfoot>**<br />
*thead를 사용하였으면 tr을 형제 태그로 사용하면 안됨. 나머지 태그들도 tbody나 tfoot로 묶어주기
```
<table>
  <thead>
    <tr>
        <th colspan="2">제철 과일 </th>
    </tr>
    <tr>
        <th scope="col">계절</th>
        <th scope="col">과일 </th>
    </tr>
  </thead>
  <tbody>
    <tr>
        <th  scope="row">봄</th>
        <td>딸기</td>
    </tr>
    <tr>
        <th scope="row">여름</th>
        <td>수박</td>
    </tr>
    <tr>
        <th scope="row">가을</th>
        <td>감</td>
    </tr>
    <tr>
        <th scope="row">겨울</th>
        <td>귤</td>
    </tr>
  </tbody>
</table>

```
<table>
  <caption>제철 과일</caption>
  <thead>
    <tr>
        <th scope="col">계절</th>
        <th scope="col">과일 </th>
    </tr>
  </thead>
  <tbody>
    <tr>
        <th  scope="row">봄</th>
        <td>딸기</td>
    </tr>
    <tr>
        <th scope="row">여름</th>
        <td>수박</td>
    </tr>
    <tr>
        <th scope="row">가을</th>
        <td>감</td>
    </tr>
    <tr>
        <th scope="row">겨울</th>
        <td>귤</td>
    </tr>
  </tbody>
</table>

`scope` :  어떤 것(행과 열 중)을 대표하는지 표시 
`colspan` : 숫자로 몇 열의 크기 만큼 차지할 것인지 표시
`rowspan` : 숫자로 몇 행의 크기 만큼 차지할 것인지 표시

## caption
표의 설명 또는 제목
- table 요소의 첫번째 자식
- table이 만약에 \<figure>로 감싸져 있으면 \<figcaption> 사용하기
