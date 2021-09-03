제로 베이스의 'HTML - 폼 요소' 강의를 듣고 내용을 정리하였습니다.
## form
정보를 제출, 사용자와 interaction
```
<form action="http://server.com/login" method="post">
  <label>이메일</label>
  <input type="email" name="userEmail">
  <label>비밀번호</label>
  <input type="password" name="userPassword">
  <button type=""submit>로그인</button>
</form>
```
`action` : 양식 데이터를 처리할 프로그램의 URI.<br />
`method` : get, post
### \<input>
- 빈 요소
  
`name` : 서버에 값을 보낼 때 이름 설정 <br />
`id` : 한 문서 안에서 구분할 때 사용
### \<label>
- 가능하면 접근성이 좋게 text로 작성
  
`for` : 해당하는 `id`와 연결하여 어떤 input의 label인지 명시한다. `name`과는 겹쳐도 상관없음 / 라벨의 자식요소로 input을 넣으면 for 사용하지 않아도됨

## fieldset, legend
**\<fieldset>**<br />input과 label을 묶을 때 <br />
- block 요소

**\<legend>** <br />부모 fieldset의 설명을 나타냄
- 첫번째 자식이어야함
```
<form action="http://server.com/survey" method="post">
  <fieldset>
    <legend>기본 정보</legend>
    <label>이름
      <input type="text" name="name">
    </label>
    <label>나이
      <input type="text" name="age">
    </label>
  </fieldset>
  <fieldset>
    <legend>추가 정보</legend>
    <label>특기
      <input type="text" name="skill">
    </label>
    <label>취미
      <input type="text" name="hobby">
    </label>
  </fieldset>
  <button type=""submit>설문조사완료</button>
</form>
```
`disabled` 속성 지정할 경우 한 fieldset안의 모든 자손 컨트롤 가능

## input
### type
```
<label>telType : 
  <input type="tel" name="tel">
</label>
<label>numberType : 
  <input type="number" name="num">
</label>
<label>rangeType : 
  <input type="range" name="range">
</label>
<label>dateType : 
  <input type="date" name="date">
</label>
<input type="reset" value="초기화">
<label>체크박스 : 
  <input type="checkbox" name="check1" checked>
  <input type="checkbox" name="check2">
</label>
<label>라디오버튼 : 
  <input type="radio" name="radio" value="1">
  <input type="radio" name="radio" value="2">
</label>
```
### name, placeholder, autocomplete, required, disabled, readonly
`name`: 서버에 전송되는 이름 <br />
`placeholder` : 힌트값 미리 표시<br />
`autocomplete` : 양식 자동완성. 후보값 보여줌<br />
`required` : 꼭 입력해야함. 안할 시 경고 뜸<br />
`disabled` : 입력하지 못하게함. 데이터 자체도 전송 안됨<br />
`readonly` : 읽기전용 <br />

### step, min, max
`min` : 최소숫자<br />
`max` : 최대숫자<br />
`step` :  해당 숫자 만큼 증가/감소

## button 
```
<button type="reset"></button>
<button type="reset"></button>
<button type="reset"></button>
```
- 자식에 text값 지정하지 않으면 글자없이 버튼만 나타남
- text 값 아니어도 다른 요소 삽입 가능 (input과의 차이점)
- 다만, 텍스트를 함께 넣어 접근성을 높이는 것이 좋음

## select option, optgroup
```
<select id="fruit" name="fruit">
  <option>melon</option>
  <option>apple</option>
  <option>orange</option>
</select>
```
- 기본값 첫번째 option

`value` : 서버로 보내기 위해<br />
`selected` : 기본값 설정<br />
`required` : 필수 선택<br />
**\<optgroup>** : option 그룹화

## input - list, datalist
선택지 추천
- input과 함께 사용함
```
<label>과일
  <input type="text" name="fruit" list="fruitlist"> 
</label>
<datalist id="fruitlist">
  <option>melon</option>
  <option>apple</option>
  <option>orange</option>
</datalist> 
```
## textarea
\<input>은 한줄의 텍스트만 입력을 받지만 \<textarea>는 여러줄 가능
```
<label> 소감
  <textarea type="text" name="comment" rows="6" cols="30"> </textarea>
</label>
```
*나중에 css로 resize none 해야 textarea크기 고정됨