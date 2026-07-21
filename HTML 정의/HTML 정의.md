## HTML
<empty-block/>
### 웹표준 정의
>
	웹페이지를 구성할 때 모든 브라우저와 플랫폼에서 일관되게 작동하도록 보장하는 국제 표준 규칙.
	W3C(World Wide Web Consortium)와 WHATWG(Web Hypertext Application Technology Working Group)에서 정의함.
	- HTML5, CSS3, JavaScript 등은 모두 웹표준 기술의 일부
	- 웹표준 준수 시 다양한 브라우저와 기기에서 동일한 사용자 경험 제공
<empty-block/>
### DTD 정의
> 문서 형식 정의(DTD, Document type Definition)는 HTML이 어떤 버전(HTML5, HTML4, XHTM 등)으로 작성되었는지 정의한다. 생략할 경우 웹 브라우저가 비표준 모드(Quirks mode)로 동작하므로 써주는 게 좋다. HTML의 DTD는 `<!DOCTYPE html>` 다.
<empty-block/>
### HTML 정의
> HTML은 Hyper Text Markup Language의 약어로 웹페이지의 구조를 설계하는 언어다. 태그 \<\>를 사용해 콘텐츠를 브라우저에 표시하고 웹사이트의 기본 뼈대를 만든다.<br>HyperText: 링크를 클릭해 문서 간 이동할 수 있는 기능<br>Markup: 태그를 사용하여 문서의 구조(제목, 문단, 목록 등)를 정의하는 방식
<empty-block/>
---
### HTML 기본 문법
<empty-block/>
<callout>
	**기본 문법**
	> 기본적으로 시작태그와 종료태그는 짝을 이루지만 예외도 있다. `<img> <br> <hr> <input> …` 
	\<tagname attribute="value"\> contents \</tagname\>  `<div class="item">one</div>`
	<span color="gray">┗━━━━━━━━  </span>element <span color="gray"> ━━━━━━━━┛</span>
	---
	**기본 용어**
	- element: 요소  `<div class="item">one</div>`
	- open tag: 시작 태그  `<div class="item">`
	- close tag: 종료 태그  `</div>`
	- attribute: 속성  `class="item"`
	- value: 값  `"item"`
	- contents: 컨텐츠  `one`
	---
	**Semantic Tag**
	> HTML5에서 도입된 시맨틱 태그는 태그 이름 만으로 문서 내 콘텐츠의 의미와 구조를 명확히 표현하는 요소다. 의미와 역할이 분명해 코드 가독성 및 유지보수에 도움을 준다. 
	`<header> <main> <section> <article> <figure> <figcaption> <aside> <time> …`
	**Non-semantic Tag**
	** **`<div> <span> …`
</callout>
<empty-block/>
---
### HTML 기본 구조
<empty-block/>
```html
<!DOCTYPE html>                 <!-- 문서의 유형을 알려준다. 이 문서가 HTML5 문서임을 선언 -->
<html lang="ko">                <!--시작 태그. HTML문서의 시작을 나타내며 lang 속성을 이용하여 문서의 기본언어가 한국어임을 명시-->
<head>                          <!-- 브라우저에게 전달할 문서의 메타 데이터와 제목 등을 포함하는 머리말 -->
    <meta charset="UTF-8">      <!-- 문서의 문자 인코딩을 UTF-8 으로 설정 -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0">  <!-- 반응형 웹 디자인을 위한 뷰포트 설정 -->
    <!-- 
        viewport: 사용자에게 실제 보여지는 직사각형 영역. 반응형 웹 디자인을 위한 뷰포트 설정  
        width=device-width : 뷰포트의 너비를 디바이스의 너비만큼 설정 
        initial-scale=1.0 : 페이지가 처음 로드될때 기본 확대/축소 수준을 지정 
    -->
    <title>Basic</title>     <!-- 웹페이지 명. 현재 로드된 웹 페이지, HTML 문서를 표현하는 객체 -->
</head>
<body>                          <!-- 문서의 본문, 브라우저에 ViewPort(웹페이지를 사용자가 보는영역)에 표시되는 내용 -->
    <!--  
        <!DOCTYPE html>     :   이 문서가 HTML5 문서임을 선언    
        <html lang="ko">    :   HTML문서의 시작을 나타내며  lang 속성을 이용하여 문서의 기본언어가 한국어임을 명시
        <head>              :   문서의 메타데이터와 제목등을 포함하는 머리말
        <meta charset="UTF-8"> : 문서의 문자 인코딩을 UTF-8 으로 설정
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        : 반응형 웹 디자인을 위한 뷰포트 설정
        : width=device-width : 뷰포트의 너비를 디바이스의 너비만큼 설정   
        : initial-scale=1.0 : 페이지가 처음 로드될때 기본 확대/축소 수준을 지정 
        <title>Document</title>                    
        <body>              :   문서의 본문, 브라우저에 ViewPort(웹페이지를 사용자가 보는영역)에 표시되는 내용 
    -->

</body>
</html> <!--종료 태그-->
```
<empty-block/>
**주요 태그 설명**
<table header-row="true">
<tr>
<td>**태그**</td>
<td>**설명**</td>
</tr>
<tr>
<td>\<!DOCTYPE html\></td>
<td>HTML5 문서 선언</td>
</tr>
<tr>
<td>\<html\></td>
<td>HTML 문서 전체 감싸는 루트 요소</td>
</tr>
<tr>
<td>\<head\></td>
<td>문서 메타데이터 (제목, 인코딩, 링크 등)</td>
</tr>
<tr>
<td>\<meta charset="UTF-8"\></td>
<td>문자 인코딩 설정</td>
</tr>
<tr>
<td>\<title\></td>
<td>브라우저 탭에 표시될 제목</td>
</tr>
<tr>
<td>\<link\></td>
<td>외부 CSS 파일 연결</td>
</tr>
<tr>
<td>\<script\></td>
<td>외부 JS 파일 연결</td>
</tr>
<tr>
<td>\<body\></td>
<td>실제 화면에 보여지는 콘텐츠 영역</td>
</tr>
</table>
---
### HTML 전체 구조
```html
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>문서 제목</title>
  <!-- 외부 스타일시트 -->
  <link rel="stylesheet" href="style.css" />
</head>
<body>

  <header>
    <!-- 상단 영역 -->
  </header>

  <nav>
    <!-- 메뉴/내비게이션 -->
  </nav>

  <main>
    <!-- 주요 콘텐츠 영역 -->
  </main>

  <aside>
    <!-- 사이드바 -->
  </aside>

  <footer>
    <!-- 하단 영역 -->
  </footer>

  <!-- 외부 스크립트 -->
  <script src="script.js"></script>
</body>
</html>
```
<empty-block/>
**HTML 구조 요약**
<callout>
	head: 설정 정보 (보이지 않는 정보)<br>body: 실제 콘텐츠 (화면에 표시되는 정보)<br>시맨틱 태그(header, main, footer 등)는 문서 구조 파악을 돕기 위한 태그
</callout>
<empty-block/>
