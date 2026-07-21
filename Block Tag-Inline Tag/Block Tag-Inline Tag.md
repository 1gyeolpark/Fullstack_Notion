<empty-block/>
## **Block Tag/Inline Tag 정의, 비교**
> 블록 태그는 줄 전체를 차지하므로, 기본적으로 인라인 태그 내부에 블록 태그를 포함할 수 없지만, HTML5부터 조건에 따른 예외 태그가 있다.  `<a> <ins> <del> <canvas> …`
<table header-row="true">
<tr>
<td>**구분**</td>
<td>**Block Tag**</td>
<td>**Inline Tag**</td>
</tr>
<tr>
<td>기본 동작</td>
<td>**줄 전체**를 차지</td>
<td>**내용만큼만** 차지</td>
</tr>
<tr>
<td>줄바꿈</td>
<td>태그 전후에 자동 줄바꿈 발생</td>
<td>줄바꿈 없음</td>
</tr>
<tr>
<td>너비/높이 지정</td>
<td>width, height 지정 가능</td>
<td>기본적으로 지정 불가</td>
</tr>
<tr>
<td>레이아웃</td>
<td>구조 배치에 사용</td>
<td>텍스트 내부 강조나 기능에 사용</td>
</tr>
<tr>
<td>중첩 가능</td>
<td>블록 내부에 다른 블록/인라인 태그 포함 가능</td>
<td>인라인 내부엔 블록 태그 포함 불가 (HTML5에선 일부 허용됨)</td>
</tr>
</table>
## Block Tag 예시
<empty-block/>
<table header-row="true">
<colgroup>
<col width="281">
<col>
</colgroup>
<tr>
<td>**태그**</td>
<td>**설명**</td>
</tr>
<tr>
<td>\<div\></td>
<td>대표적. 문서 분할 태그</td>
</tr>
<tr>
<td>\<p\></td>
<td>문단(Paragraph) 나누는 태그</td>
</tr>
<tr>
<td>\<h1\> \~ \<h6\></td>
<td>제목(Heading) 태그</td>
</tr>
<tr>
<td>\<ul\>, \<ol\>, \<li\></td>
<td>목록(List) 관련 태그</td>
</tr>
<tr>
<td>\<section\>, \<article\>, \<header\>, \<footer\></td>
<td>시맨틱 블록 태그</td>
</tr>
<tr>
<td>\<form\>, \<table\></td>
<td>폼, 표 관련 블록 태그</td>
</tr>
</table>
```html
<div>
	<h1>제목</h1>
	<p>단락</p>
</div>
```
<empty-block/>
---
## Inline Tag 예시
<empty-block/>
<table header-row="true">
<colgroup>
<col width="269">
<col>
</colgroup>
<tr>
<td>**태그**</td>
<td>**설명**</td>
</tr>
<tr>
<td>\<span\></td>
<td>인라인 태그</td>
</tr>
<tr>
<td>\<a\></td>
<td>다른 페이지 등 이동 하이퍼링크 태그</td>
</tr>
<tr>
<td>\<img\></td>
<td>이미지 태그</td>
</tr>
<tr>
<td>\<strong\>, \<em\></td>
<td>강조 태그</td>
</tr>
<tr>
<td>\<label\>, \<input\>, \<select\>, \<textarea\></td>
<td>폼 관련 인라인 태그</td>
</tr>
</table>
```html
<div>
    <p><strong>주의:</strong>비밀번호는 8자 이상의 영문, 숫자 조합이어야 합니다.</p>
</div>
```
<empty-block/>
