제로 베이스의 'HTML - 임베디드요소' 강의를 듣고 내용을 정리하였습니다.
## img
문서에 이미지 삽입
- 빈 요소 <br />

`src` : <b>필수 특성</b>, 이미지 경로 지정
- 상대 경로 : "https://~"
- 절대 경로 : "images/Icon.svg"

`alt` : 이미지의 텍스트 설명. 스크린 리더가 사용자에게 이미지를 설명할 때 필요함. 만약 이미지를 불러오지 못했을 때도 원래 어떤 이미지가 존재했는지 설명할 수 있음. <br />
`title` : 마우스를 올렸을 때 이미지 설명 나타냄<br />
`width` : 이미지 픽셀 기준 고유 너비. 단위 없는 정수<br />
`height` : 이미지 픽셀 기준 고유 높이. 단위 없는 정수<br />
*width랑 height 중 하나만 설정하더라도 원본 비율에 맞춰 같이 변경됨

## 이미지 유형
래스터 - 확대를 하면 깨짐
- jpeg : 이미지 압축에 적합 (많이 사용됨)
- png :  투명도가 필요할 경우
- gif : 여러장의 이미지. 애니메이션 표현
- webp : 구글이 만든 이미지 포맷. 품질이나 압축률이 우수하지만 지원하지 않는 브라우저가 많음
  <hr />
벡터 - 확대를 해도 깨지지 않음
- svg : 다양한 크기로 정확하게 그려야하는 아이콘이나 그래프 등에 사용
## 반응형 이미지
### srcset
여러개의 이미지 파일 쉼표로 구분. Internet Explorer 지원x
- 이미지의 URL
- 공백 + 너비서술자(w) or 밀도 서술자(x)
- 브라우저 사이즈를 늘이면 끝없이 늘어남
```
<img
  src="images/small.jpg"
  srcset="images/small.jpg 100w,
          images/medium.jpg 200w, 
          images/large.jpg 300w"
  alt="sample"
/>
```
### sizes
- max-width, min-width
```
<img
  src="images/small.jpg"
  srcset="images/small.jpg 250w,
          images/medium.jpg 450w, 
          images/large.jpg 700w"
  alt="sample"
  sizes="(min-width: 700px) 700px,
         (min-width: 450px) 450px,
         250px"
/>
<img
  src="images/small.jpg"
  srcset="images/small.jpg 250w,
          images/medium.jpg 450w, 
          images/large.jpg 700w"
  alt="sample"
  sizes="(max-width: 450px) 250px,
         (max-width: 700px) 450px,
         700px"
/>
```
## video
- 자식요소로 텍스트, \<a>,\<source> 등 사용가능.

`src` : 삽입할 동영상의 주소 명시<br />
`controls` : 재생할 수 있는 툴<br />
`autoplay` : 자동 재생, 하지만 웹 페이지를 들어가자마자 자동 재생 되는 것은 사용자 경험에 좋지 않기에 소리가 있는 동영상은 웹 브라우저가 자동재생을 막음. 꼭 자동재생을 해야한다면 소리를 없애는 `muted` 사용하기<br />
`poster` : 썸네일 기능. 없으면 첫번째 프레임 포스터로 설정됨.

## audio
비디오와 거의 동일.
- multiple source 가능 

## canvas, iframe
**\<canvas>** 마크업은 할 수 있되 그림을 그리는 등 추가기능은 javascript 사용하기<br />
**\<iframe>** 현재 문서 안에 다른 HTML삽입
<iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3163.744682126815!2d126.9868574145682!3d37.53751542980339!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x357ca249029c7327%3A0x3f34d9a9d34be398!2z7ISc7Jq47Yq567OE7IucIOyaqeyCsOq1rCDsnbTtg5zsm5Drj5kg64W57IKs7Y-J64yA66GcNDbquLg!5e0!3m2!1sko!2skr!4v1630582540120!5m2!1sko!2skr" width="400" height="350" style="border:0;" allowfullscreen="" loading="lazy"></iframe>