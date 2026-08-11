## JS 기본 구조
```clojure
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
    /* CSS 작성 */
    </style>
</head>
<body>
    <!-- HTML 작성 -->
    
    <script>
		    // JS 작성
    </script>
</body>
</html>
```

---

## 이론으로 이동

### Scope(스코프)<br>: 변수&함수 접근 범위

<table header-row="false" header-column="true">

<colgroup>

<col width="239.66666666666666">

<col width="439.65625">

</colgroup>

<tr color="gray_bg">

<td>스코프</td>

<td>특징</td>

</tr>

<tr>

<td>글로벌 스코프(Global Scope)</td>

<td>전역 스코프. 코드 내라면 모두 접근 가능</td>

</tr>

<tr>

<td>함수 스코프(Function Scope)</td>

<td>지역 스코프. 선언된 함수 안에서만 접근 가능<span color="gray"> —\> var 해당</span></td>

</tr>

<tr>

<td>블록 레벨 스코프(Block Level Scope)</td>

<td>지역 스코프. 블록\{\} 안에서만 접근 가능<span color="gray"> —\> let, const 해당</span></td>

</tr>

<tr>

<td>모듈 스코프(Module Scope)</td>

<td>지역 스코프. 모듈 내부에서만 접근 가능하며, 다른 모듈에서 접근하려면 export / import를 사용해야 한다.</td>

</tr>

<tr>

<td>렉시컬 스코프(Lexical Scope)</td>

<td>정적 스코프. 함수 호출 위치가 아닌, 함수 정의 위치의 상위 스코프를 상속하는 규칙이다.</td>

</tr>

<tr>

<td>스코프 체인(Scope Chain)</td>

<td>변수가 함수 내부에 존재하지 않으면 상위(외부)로 올라가며 찾을 수 있다. 연결고리를 따라 간다고 보면 된다.<br><span color="gray">내부→외부 가능 / 외부 → 내부 불가</span></td>

</tr>

</table>

### closure(클로저) \*\*\*좀더정리<br>: 함수 선언 시 환경 기억/참조

> 함수 선언 당시의 환경을 기억해 함수가 실행 된 이후에도, 외부에서 호출되더라도 접근해 참조할 수 있다. 데이터 은닉, 상태 관리 등에 사용한다.

### CallBack(콜백)함수 \*\*정리필요

> .

### **const(상수), let(변수), var(변수)**<br>: 변수 선언

> const는 변경하면 안되는 불변 변수 선언 시 주로 사용. 변수 자체는 재할당 할 수 없지만 내부 속성 값은 변경 가능. 따라서 기본적으로 const를 사용하고 값이 변경될 수 있는 변수 선언 시 let을 사용한다. var은 사용하지 않는 게 좋다.

<table header-row="true" header-column="true">

<colgroup>

<col width="91.65625">

<col>

<col width="95.65625">

<col width="147.65625">

<col>

</colgroup>

<tr>

<td>키워드</td>

<td>재선언</td>

<td>재할당</td>

<td>특징</td>

<td>스코프<br>(함수 외 선언 시 모두 전역 스코프)</td>

</tr>

<tr>

<td>const</td>

<td>불가능 X</td>

<td>불가능 X</td>

<td>가장 안전. 심볼릭 상수.</td>

<td>블록 레벨 스코프</td>

</tr>

<tr>

<td>let</td>

<td>불가능 X</td>

<td>가능 O</td>

<td>값이 바뀔 때만 사용</td>

<td>블록 레벨 스코프</td>

</tr>

<tr>

<td>var</td>

<td>가능 O</td>

<td>가능 O</td>

<td>비추천. 오류 위험. 호이스팅 O</td>

<td>함수 스코프(블록 레벨 스코프 무시)</td>

</tr>

</table>

### Types<br>: 타입

<table header-row="true" header-column="true">

<colgroup>

<col>

<col width="484">

</colgroup>

<tr>

<td>원시타입(**Primitive Types)**</td>

<td>설명</td>

</tr>

<tr>

<td>**숫자(Number)**</td>

<td>숫자, 정수  `20`</td>

</tr>

<tr>

<td>**문자열(String)**</td>

<td>문자. " " ,  ' ' , \`\` 사용. \$\{value\} 통해 문자열에 변수, 함수 호출 및 산술 표현식 직접 삽입은 백틱(\` \`)만 가능  `\`HELLO WORLD\`\`</td>

</tr>

<tr>

<td>**불리언(Boolean)**</td>

<td>true 또는 false 값. TF. 이진수에서는 True- 1/False- 0. `true`</td>

</tr>

<tr>

<td>**null**</td>

<td>비어 있는 값 명시적 표현. null이라는 값을 할당받았다.<br>변수 초기화. 공간 형성 o + 기본값 null 삽입 \<- 개발자가 의도한 값<br>콘솔에서는 null로 표시되며, 타입은 null이나, js오류로 object로 표시되고 있다.  `let vol = null;`</td>

</tr>

<tr>

<td>**undefined**</td>

<td>정의되지 않은 값. 값을 할당받지 못했다.        <br>공간 형성 x, 기본값 생략 \<- 개발자가 의도하지 않은 예외<br>따라서 콘솔에서는 undefined로 표시되며, 타입도 undefined다.  `let vol2;`</td>

</tr>

<tr>

<td>**심벌(Symbol)**</td>

<td>ES6에서 추가된 고유 식별자</td>

</tr>

<tr>

<td>**BigInt**</td>

<td>매우 큰 정수</td>

</tr>

<tr color="gray_bg">

<td>참조 타입 (Reference Types)</td>

<td>**설명**</td>

</tr>

<tr>

<td>객체(Object)</td>

<td>키(Key)와 값(Value)의 집합, 배열(Array), 함수(Function) 등<br> `{"name" : "사과", "color" : "빨간색", "harvest": "8월"};`</td>

</tr>

</table>

### 추상화

> 부모 클래스에서 정의하며, 자식 클래스에서 반드시 구현(오버라이딩)해야만 사용할 수 있는 메소드.<br>여러 객체에서 공통적인 특징(속성, 메서드)만 추출하여 뼈대(추상 클래스)를 만든다.

### Literal(리터럴)& **Literal Notation(**리터럴 표기법)

<callout>

	**리터럴**

	특정한 자료형의 값을 직접 표현하는 방식으로, 변수에 넣는 변하지 않는 고정된 데이터 값 자체를 말한다. 이름(식별자)이 없는 상수. let age = 25; 에서는 `25`가 정수 리터럴.

	---

	**리터럴 표기법**

	리터럴을 사용해 객체나 값을 정의하는 문법적 방식. <br>**종류**: 정수 리터럴, 실수/부동소수점 리터럴, 문자 리터럴, 문자열 리터럴, 불리언 리터럴, null 리터럴, 템플릿 리터럴 `console.log(\`Text\`);`, 배열 리터럴 `"HELLO"` , 객체 리터럴 `{name: 'Kim'};`

	---

	**객체 리터럴 구조**
	```javascript
const myCar = {
	// 속성
	owner: "홍길동",
	//기능
	Accel: function(){}
	};
	
myCar["color"] = "검정"; // 속성 추가 가능
	```
	---

	**보간법**

	백틱(\`)과 \$\{\}을 사용해 문자열 내부에 변수를 직접 삽입한다. `console.log(\`Text ${plus}\`);`

</callout>

### Symbolic(심볼릭)

> 식별자를 지정해 사용하는 상수. 키워드를 사용하여 변수처럼 이름을 선언하고 값을 대입한다. 프로그램 실행 중 값이 변경되지 않는다. 가독성이 좋아지고, 유지보수가 쉽다. 고정적인 숫자는 심볼릭을 사용하는 게 좋다. `const` 

---

## JS 함수

### Hoisting(**호이스팅)**

> 인터프리터가 코드를 실행하기 전에 함수, 변수, 클래스 또는 import의 선언이 코드 맨 위로 끌어올려진 것처럼 보이는 현상. **코드 선언 위치와 상관없이 실행 전 최상단으로 끌어올려져 실행된다.  <br>(**ex. `function` , `var` )

### function()\{\} VS const=()⇒\{\}<br>: 함수 선언문  VS 함수 표현식

> 함수 표현식은 ECMA6 이후 등장한 문법으로 호이스팅이 불가하다.  코드의 안정성, 가독성, 그리고 유지보수를 높이기 위해서 const를 주로 사용한다.<br>**<br>호이스팅(Hoisting)<br>**인터프리터가 코드를 실행하기 전에 함수, 변수, 클래스 또는 import의 선언이 코드 맨 위로 끌어올려진 것처럼 보이는 현상. **코드 선언 위치와 상관없이 실행 전 최상단으로 끌어올려져 실행된다.**

<table header-row="true" header-column="true">

<colgroup>

<col width="91.00000762939453">

<col width="285">

<col width="323.0000305175781">

</colgroup>

<tr>

<td>항목</td>

<td>function; 함수 선언문<br>Function Declaration</td>

<td>const; 함수 표현식<br>Function Expression</td>

</tr>

<tr>

<td>구문</td>

<td>`function(){}`</td>

<td>`const=()⇒{}`</td>

</tr>

<tr>

<td>간결성</td>

<td>상대적으로 길고 중복되는 느낌</td>

<td>return과 \{\} 생략 가능하여 매우 간결</td>

</tr>

<tr>

<td>호이스팅</td>

<td>O  (선언 전 호출 가능)</td>

<td>X  (선언 후 호출 필수)</td>

</tr>

<tr>

<td>생성자 new</td>

<td>O  (사용 가능)</td>

<td>X  (사용 불가)</td>

</tr>

<tr>

<td>스코프</td>

<td>함수 스코프<br>(지역 변수. 선언된 함수 안에서만 접근 가능)</td>

<td>블록 레벨 스코프<br>(지역 변수. 블록\{\} 안에서만 접근 가능)</td>

</tr>

<tr>

<td>재선언</td>

<td>재선언 가능 (위험)</td>

<td>재선언 불가</td>

</tr>

<tr>

<td>this 바인딩</td>

<td>동적 바인딩(Dynamic Binding)<br>(실행 시점 기준 this 동적 결정)</td>

<td>렉시컬 바인딩(Lexical Binding)<br>(생성 시점 기준 this 정적 고정. 정의된 위치 상위 스코프 this 상속)</td>

</tr>

<tr>

<td>arguments</td>

<td>함수 내부에서 arguments 객체 사용 가능<br>`function sum() { // 인자 정의 안해도 ok<br>console.log(arguments); // 10`</td>

<td>arguments 지원X (대신 Rest 파라미터 ...args 사용)<br>`const sum = (...args) => { // args  배열 생성<br>console.log(args[0]); // 10`</td>

</tr>

<tr>

<td>객체 안 <br>메서드</td>

<td>key: value 형태: `keyname: function() {}`<br>최신 축약:  `keyname() {}`<br>객체 안 한정 메서드 축약 표현 사용 가능</td>

<td>메서드 내부 콜백 함수로 많이 사용</td>

</tr>

</table>

### **console.log()<br>: 콘솔 출력_디버깅**

> 개발자 도구(F12) 콘솔에 문자열로 메시지를 출력해 디버깅한다.
```javascript
console.log(item);
// 예시 
const item = {"name" : "사과", "color" : "빨간색", "harvest": "8월"};
```

### **alert()<br>: **웹페이지 팝업 알림
```javascript
alert('HELLOWORLD');
```

### **typeof<br>: 반환값 확인**

> 변수나 값의 데이터 타입을 문자열로 반환한다. 값의 종류를 확인할 때 사용한다. 
```javascript
console.log(typeof "Hello")     // "string"
console.log(typeof 10)          // "number"
console.log(typeof true)        // "boolean"
console.log(typeof undefined)   // "undefined"
console.log(typeof null)        // "object" (null이지만 js오류로 object 표기)
console.log(typeof [])          // "object"
console.log(typeof function(){})// "function"
```
### **onclick<br>: 버튼 클릭**

> 버튼을 클릭했을 때 자바스크립트 코드를 실행하는 인라인 이벤트 핸들러 함수. <br><span color="gray">보안 위험, 사용 지양.  —\> 대안: .addEventListener</span>
```javascript
<button onclick="javascript코드">버튼이름</button> 
```

### **javascript:void(0)<br>: 링크 무효화**

> \<a\> 태그의 href 속성에 사용해 링크 기능을 무효화시킨다. 페이지 이동이나 새로고침 없이 자바스크립트 동작만 실행하게 할 수 있다. <span color="gray">ex) onClick과 결합해 버튼으로 이용</span>
```javascript
<a href="javascript:void(0)">BTN</a>
```

---

## **document 함수**

> 브라우저가 불러온 웹 페이지(HTML 문서) 전체를 가리키는 객체로, DOM(Document Object Model) 트리의 진입점이다. HTML 요소와 관련된 작업을 도와주는 다양한 메소드를 제공한다. <br><span color="gray">DOM: HTML 문서를 브라우저가 이해할 수 있는 트리(Tree) 구조로 만든 객체 모델. </span>

### Array.from()<br>:유사배열→배열

<callout>

	유사배열은 배열 같지만 객체이므로 forEach(), map() 등 유용한 함수를 직접 사용할 수 없기 때문에 Array.from() 또는 Spread 연산자 \[…item\] 으로 변환하는 과정이 필요하다.

	예외적으로 querySelectorAll()는 유사배열이지만 forEach()를 직접 사용할 수 있다.

	---

	**기본 배열(Array)**: 직접 선언 `const arr =[1,2];` , 배열로 변환 `Arrayfrom()` , `[…item]`

</callout>
```javascript
const items = document.getElementsByClassName("thing");

const arr1 = Array.from(items);  // Array.from()
const arr2 = [...items];   // Spread 연산자 [...] 
```
### .innerHTML<br>: HTML 출력, 수정

> HTML 콘텐츠를 가져오거나 내용을 변경할 때 사용한다. <br><span color="gray">보안 위험, 사용 지양.  —\> 대안: .textContent  / .insertAdjacentHTML() / createElement()</span>
```javascript
document.getElementById("b1").innerHTML = "Hello World!";  // id가 "b1"인 요소 내용 변경

const element = document.getElementById('b1');  // 효율 위해 변수 정의
element.innerHTML = '<p style="color: blue;">안녕하세요!</p>';  // HTML 태그 포함 내용 삽입
```
### - 요소 선택

### **.getElementById(id)<br>: 특정 id 가진 요소 선택**

> 요소 하나만 선택된다.
```javascript
this.curSpeed += 10;  // curSpeed의 값 +10
// style.width: HTML 요소의 가로 너비(width)를 동적으로 변경하는 코드
document.getElementById('gauge').style.width=`${this.curSpeed *2}px`; // id가 "gauge"인 요소 선택해 가로너비 curSpeed px 만큼 증가
document.getElementById('curSpeed').value=this.curSpeed; // id가 "curSpeed"인 요소 선택 후 값에 curSpeed 삽입
```
### .getElementsByClassName(name)<br>: 특정 class 가진 모든 요소 선택

> 이보다 더 편리한 querySelectorAll 사용 추천.<br>forEach() `<Array.from() 필요`, for …of, for로 개별 요소에 접근할 수 있다.
```javascript
const item = document.getElementsByClassName("thing");  // "thing" class인 모든 요소 선택
const itemArray = Array.from(item);  // 배열로 변환

itemArray.forEach((item, index) =>{
	item.textContent= `${index}번째`;
});
```
### .getElementsByTagName(tag)<br>: 특정 tag 가진 모든 요소 선택

> 이보다 더 편리한 querySelectorAll 사용 추천.<br>forEach() `<Array.from() 필요`, for …of, for로 개별 요소에 접근할 수 있다.
```javascript
document.getElementsByTagName("li");
```
### .querySelector(cssSelector)<br>: CSS 선택자 만족하는 첫번째 요소 선택

>

### .querySelectorAll(cssSelector)<br>: CSS 선택자 만족하는 모든 요소 선택

### - 요소 생성&변경

> **포함관계: 객체(Object) \> 노드(Node) \> 요소(Element)<br>**객체: 키(key)과 값(value)으로 구성된 프로퍼티(Property)들의 집합<br>노드: DOM 트리 구조에 참여하는 텍스트, 주석, 태그 등의 객체<br>요소: 노드 중 \<div\>, \<p\> 같은 HTML 태그 객체

### .createElement(tagName)<br>: 새로운 요소 노드 생성

### .createTextNode(text)<br>: 새로운 텍스트 노드 생성

### .appendChild(node)<br>: 자식 노드 추가

### .removeChild(node)<br>: 자식 노드 제거<br>

### .write(text)<br>: 문서에 텍스트 또는 HTML 출력

> <span color="gray">보안 위험, 사용 지양.  —\> 대안: .textContent / .insertAdjacentHTML()</span>

### .write()<br>: 출력

> 괄호 안 내용을 브라우저가 페이지에 즉시 삽입하는 함수. 사용 지양.
```javascript
document.write('<h1>HELLO WORLD</h1>');
document.writeln('<h1>HELLO WORLD</h1>');   // 하단 자동 줄바꿈
```

## - 이벤트 처리<br>

### **.**addEventListener('EventType',() ⇒\{\})<br>: 요소에 이벤트 리스너 추가

<br>
```javascript

```
<callout icon="💡" color="gray_bg">

	click, input, keydown, change, scroll, resize, DOMContentLoaded

</callout>

문서 전체 이벤트:<br>DOMContentLoaded: DOM 트리 구조가 로드된 시점에 이벤트 발생.

---

## JS 실습(다른 페이지로)

### HTML JS 직접 삽입 {toggle="true"}

	코드가 지저분해지고 유지보수가 힘들어 권장되지 않는다.
	```html
<body>
    <!-- button's onClick 이벤트 속성 -->
    <button onclick="alert('HELLOWORLD')">BTN_1</button>
    <button onclick="alert(10+20)">BTN_2</button>
    <button onclick="alert('HELLOWORLD\nHELLOWORLD\nHELLOWORLD')">BTN_3</button>

    <!-- a's href -->
    <a href="javascript:void(0)">BTN_1</a>
    <a href="javascript:alert('HELLOWORLD')">BTN_2</a>
    <a href="javascript:alert(10+30)">BTN_3</a>
    <a href="javascript:console.log(obj);">BTN_4</a>

    <script>
        const obj = {"name" : "홍길동", "age" : "30", "addr": "대구"};
    </script>
</body>

	```

---

### .write() {toggle="true"}

	<callout>

		**document.write()<br>**괄호 안 내용을 브라우저가 페이지에 즉시 삽입하는 함수. 텍스트 뿐만 아니라 HTML태그도 인식해 렌더링한다. writeln은 자동줄바꿈된다. `document.write('<h1>HELLO WORLD</h1>');`

	</callout>
	```html
<body>
    <script>
        document.write('<h1>HELLO WORLD~~~</h1>');
        document.writeln('<h2>HELLO WORLD!</h2>'); // 다음줄 자동 줄바꿈
        document.write('<h3>HELLO WORLD...</h3>');
    </script>
    <!-- 화면 로딩 후 onclick 이벤트 실행 시 초기화되어 HELLO WO..만 확인 -->
    <button onclick="document.write('<h1>HELLO WO..</h1>')">ADD</button>
</body>
	```

---

### .**getElementById()** {toggle="true"}

	<callout>

		**getElementById()<br>**주어진 문자열과 일치하는 id 속성을 가진 요소를 찾고, 이를 나타내는 Element(요소)를 반환한다.<br>`getElementById('d1')`

	</callout>
	```html
<body>
    <button onclick="document.getElementById('d1').innerHTML='<h2>abcd</h2>'">변경</button>
    <div id="d1">HELLOWORLD</div>

    <script>
        const d1El=document.getElementById('d1');
        d1El.innerHTML='<h2>Test</h2>'
    </script>
</body>
	```

---

### Types {toggle="true"}
	```html
<body>
    <script>

        // number: 숫자
        console.log("number: 숫자 10");
        console.log(typeof 10);
        console.log(typeof 10.5);
        console.log("-------------------")

        // string: 문자
        console.log("string: 문자 HELLO WORLD");
        console.log(typeof "HELLO WORLD");
        console.log(typeof 'HELLO WORLD');
        console.log(typeof `HELLO WORLD`);
        console.log("-------------------")
        
        // object: 객체 --> {key: value, key: value}
        console.log(typeof {});
        console.log("object: 객체", {"name" : "홍길동", "age" : "30", "addr": "대구"});
        console.log(typeof {"name" : "홍길동", "age" : "30", "addr": "대구"});
        console.log("-------------------")
        
            // object - 포함된 값 중 -> 
            // null: 빈값임을 명시 (null이라는 값을 할당받음)
            // ㄴ 변수 초기화(공간 형성 o + 기본값 null 삽입 <- 개발자가 의도한 값)
            let vol = null;
            console.log("null: 빈값");
            console.log(typeof vol);
            console.log("-------------------")
        
        // undefined: 정의되지 않은 값 (값을 할당받지 못함)
        // ㄴ 공간 형성 x, 기본값 생략 <- 개발자가 의도하지 않은 예외)     
        let vol2;
        console.log("undefined: 정의되지 않은 값(예외)");
        console.log(vol2);
        console.log(typeof vol2);
        console.log("-------------------")
        
        // boolean: TF. 이진수에서는 True- 1/False- 0.
        console.log(typeof true);
        console.log(typeof false);

    </script>
</body>
	```

---

### 보간법 {toggle="true"}
	```html
<body>
    <!-- 
        보간법
        변수, 함수 호출 및 산술 표현식을 문자열에 직접 삽입할 수 있는 기능
        ${value} 형식을 사용, 백틱(``)에만 사용가능
    -->

    <script>
        // 변수 지정: let, 상수 지정: const
        // " ", ` `, ' ' = 문자열. 백틱은 변수 삽입이 가능하므로 백틱으로 많이 사용
        let str1 = "hello";
        let str2 = "world";
        console.log(str1+str2);

        let str3 = `TEST1: ${str1} / ${str2}`;
        let str4 = `TEST2: ${10 + 20 + 30}`;
        let str5 = `TEST3: ${10 > 20}`;
        console.log(str3);
        console.log(str4);
        console.log(str5);
    </script>
</body>
	```

---

### 음
```html
    <body>
    <h1>MYCAR</h1>
    <div>
        <h2>속성</h2>
    </div>
    <div>
        <label>owner</label> <input id="owner" readonly/>
    </div>
    <div>
        <label>category</label> <input id="category" readonly/>
    </div>
    <div>
        <label>fuelType</label> <input id="fuelType" readonly/>
    </div>
    <div>
        <label>curSpeed</label> <input id="curSpeed" readonly/>
    </div>
    <div>
        <label>fulAmount</label> <input id="fulAmount" readonly/>
    </div>
    <div>
        <button onclick="myCar.Accel()">가속</button>
        <button onclick="myCar.Break()">감속</button>
        <button onclick="myCar.toString()">상태확인</button>
    </div>
    <div>
        <label>속도</label>
        <div id="gauge" style="height: 50px; width: 1px; background-color: orange;"></div>
    </div>
    <hr>
    
    <script>

        /* object? 사물, 객체 {key: value}
        Property(속성), 기능

        MyCar: 
        속성: 소유자, 브랜드명, 속도, 연료타입, 연료량...
        기능: 가속하다, 감속하다, 시동을 건다, 시동을 끈다...
        */ 

        /* 추상화: 공통적인 속성과 기능을 정의해 상위 클래스 생성
           객체 리터럴 방식: 중괄호( {} ) 안에 0개 이상의 속성의 이름(Key)과 값(value)을 콜론( : )으로 연결한 쌍을 쉼표( , )로 구분하여 나열하는 형태 */

        // const: Constant(상수)의 약자로, 한 번 설정하면 값이 변경되지 않는 불변 변수를 선언할 때 사용하는 키워드. 변수 자체는 재할당 할 수 없지만 내부 속성 값은 변경 가능.

        // 객체 리터럴 방식을 사용해 myCar라는 객체를 정의하고 속성을 추가해 자동차의 정보를 저장하는 구조

       const myCar = {    // 불변 변수 const
					
						// 객체 리터럴 방식 {키:값}으로 정의
						
            // 속성  
            owner: "홍길동",
            category: "SUV",
            fuelType: "디젤",
            curSpeed: 0,
            fulAmount: 100,   

            //기능
            Accel: function(){        // 함수 선언문 function 사용
                this.curSpeed += 10;  // curSpeed의 값 +10
                console.log("가속처리 완료. 현재 속도: ",this.curSpeed)
                // style.width: HTML 요소의 가로 너비(width)를 동적으로 변경하는 코드
                // gauge id 가진 요소 선택 후 가로 너비를 curSpeed px 만큼 증가시킨다.
                document.getElementById('gauge').style.width=`${this.curSpeed}px`;
                // curSpeed id 가진 요소 선택 후 값에 curSpeed 삽입
                document.getElementById('curSpeed').value=this.curSpeed;
            },
            
            Break: function() {
                this.curSpeed -= 10;  // curSpeed의 값 -10
                console.log("감속처리 완료. 현재 속도:",this.curSpeed)
                // gauge id 가진 요소 선택 후 가로 너비를 curSpeed *2px 만큼 감소시킨다.
                document.getElementById('gauge').style.width=`${this.curSpeed *2}px`;
                // curSpeed id 가진 요소 선택 후 값에 curSpeed 삽입
                document.getElementById('curSpeed').value=this.curSpeed;              
            },

            toString: function(){
                console.log(this.owner, this.category, this.fuelType, this.curSpeed, this.fulAmount)
            }
        };

        console.log(myCar);
        
        // document.getElementById(id);: 주어진 문자열과 일치하는 id 속성을 가진 요소를 찾고, 이를 나타내는 Element객체를 반환. ID는 문서 내에서 유일해야 하기 때문에 특정 요소를 빠르게 찾을 때 유용.
        
        // 초기화
        // 페이지가 로드될 때 myCar 객체 초기 데이터 요소들에 딱 한 번 출력.
        document.getElementById('owner').value = myCar.owner;
        document.getElementById('category').value = myCar.category;
        document.getElementById('fuelType').value = myCar.fuelType;
        document.getElementById('curSpeed').value = myCar.curSpeed;
        document.getElementById('fulAmount').value = myCar.fulAmount;

        const tori = {
            // 속성
            name: "토리",
            kind: "포메라니안",
            age: "2",
            weight: 4.8,

            // 기능
            sound: function(){console.log(`${this.name}가 멍멍 짖습니다!`)},
            toString: function(){console.log(this.name, this.kind, this.age, this.weight)}
        }
        
        console.log(tori);
        tori.toString();
        tori.sound();
				
        tori["color"] = "검정";   // 객체 속성 추가
        console.log(tori);
        tori.sound();

    </script>

</body>
</html>
```

---

# 26-03-20 실습

### 호이스팅 Hoisting {toggle="true"}
	```html
<script>

    /*
        호이스팅
        변수와 함수의 정의가 코드 실행 전에 메모리에 미리 저장되는 현상
        function 예약어 사용 시 호이스팅 처리 됨
        var 예약어 사용 시 호이스팅 처리됨
        cf) 변수 지정: let, var / (심볼릭) 상수 지정: const
    */

    // const tmp = 10;
    // console.log("tmp",tmp);
    // tmp=20;
    // console.log("tmp",tmp);
    

    // 변수 HOISTING
    a = 10;
    console.log('a',a);
    var a;

    let b;
    b = 10;
    console.log('b',b);

    // 함수 HOISTING

    h1();
    function h1() {
        console.log("Hello world");
    }
    h2();
    const h2 = () =>{
        console.log("Hello world2");
    }

    /*
        var 변수는 가급적 사용 지양
        function은 목적에 따라 사용여부 결정. (처음에 만든 효과를 주고 싶으면 적용)
        function은 기본적으로 이름 부여 가능. (익명 함수/이름 부여 함수 선택 가능)
        화살표 함수는 기본적으로 익명함수 처리.
    */

</script>
	```

### 스코프 Scope {toggle="true"}
	```c++
    <script>

        /*
            스코프(SCOPE)란
            변수나 함수가 접근할 수 있는 범위
            전역 스코프(Global Scope)와 지역 스코프(Local Scope)로 구별
            전역 스코프: 모든 지역에서 접근 가능
            지역 스코프: 특정 영역({})에서만 접근 가능
            - 함수 스코프: 함수 본문{} 내에서 선언된 변수는 함수 내부에서만 접근 가능
            - 블록 스코프: if, while...{} 블록 내에서만 접근 가능
            
            렉시컬(Lexical) 스코프: 변수를 선언한 위치에 따라 스코프 결정
         */

         // 전역 스코프
         var g_val =  "전역변수 확인!";

         function a(){
            console.log('a func(..)', g_val);
         }
         a();

         if(true){
            console.log('if..',g_val);
         }
         console.log({key1:g_val});
         
         // 함수 스코프(함수 내에서만 사용되는 변수 범위, 만약 함수 범위 아니면 전역 스코프, var에 적용)

         function a() {
            var n1 = 10;
            console.log("n1",n1);
         }
         a();

         // 함수 스코프 영역이 아니라면 var 은 전역 스코프로 적용됨
         // 부연 ---> var은 함수 스코프(지역 변수 선언, 선언된 함수 안에서만 접근 가능)지만 블록 레벨 스코프를 무시해 블록 안에서 작성했더라도 바깥에서 불러올 수 있다.

         for(var i=0 ; i<3 ; i++) console.log("i",i);
         console.log('end i: ', i);
         
         // 블록 스코프({}내에서만 유효한 범위)
          if(true){
             let v_1 ="블럭 내에서만 사용되는 지역변수"
             var v_2 ="블럭 내에 사용한 var 변수"
             console.log("v_1", v_1);        
             console.log("v_2", v_2);
         }
         console.log("---------");
         console.log("v_2", v_2);        // 불러와 적용된다.
         console.log("v_1", v_1);        // 블록레벨 스코프라  Uncaught ReferenceError: v_1 is not defined 오류 띄운다.

        
        // 렉시컬 스코프

        const name = "Global Scope";

        function outer() {
            const name = "Outer Local Scope";   // 더 가까운 곳 따름

            function inner() {
                console.log(name);
            }
            inner();
        }

        outer();

        window.name= "김길동"

        const b = {
            name: "홍길동",
            age: 55,
            addr: "대구",
            
            talk: function(){
                console.log(`${this.name}님이 말합니다.`); // function's this: 호출 당시 기준
                console.log(this);
            },
            walk: ()=>{
                console.log(`${this.name}님이 걷습니다.`); // ()=>{}'s this: 탄생 시점 기준(렉시컬)
                console.log(this); // 정의된 위치 상위 스코프 this 상속. window 
            }
        }
        b.talk();
        b.walk();

        const f1 = () => {
            console.log('f1...',this); // 상위 스코프(window객체)의 this를 가져옴  
        }
        f1();
        function f2() {
            console.log('f2...',this); // 호출방법에 따라 this가 달라짐
        }
        f2();

    </script>
	```

### 클로저 Closure {toggle="true"}
	```c++
    <script>
        /*
            클로저
            클로저는 내부 함수가 외부 함수의 변수에 접근할 수 있는 방법을 의미한다.
            정보 은닉: 클로저를 사용하여 외부에서 접근할 수 없도록 변수를 보호하고, 
            함수를 통해서만 접근 가능하도록 제한할 수 있다.

            데이터 보존: 클로저를 사용하여 함수가 생성될 당시 환경을 유지하면서, 
            함수 내에서 데이터를 영구적으로 보존할 수 있다.
            비동기 처리: 클로저를 사용하여 비동기적인 작업에서 결과를 유지하고, 
            필요한 때에 접근할 수 있다.
        */

         //외부함수(전역)
         function outer(){
             //상태값 보관
             let state = 0;
            
             //내부함수()
             function setState(n){
                 state = n;      //렉스컬 스코프(outer의 state에 접근가능)
                 console.log('state..',state);
             }

             return setState;  //함수이름을 리턴하면 만들어진 함수의 위치정보(메모리주소) 가 반환
         }
         const closureFunc = outer();
         closureFunc(10);
         closureFunc(20);
         closureFunc(30);
         closureFunc(40);

        // 전역에서 선언 시 전역스코프가 된다.
         var x = 'global x'; // 전역스코프(Window)
         let n1 = 10; // 전역스코프(Declarative Environment Recode(Script 스코프) : const,let 시 저장되는 전역스코프 )
         console.log(window.x);
         console.log(window.n1); //x

        //  Outer 함수 내의 지역 스코프
        function outer(){
            var x = 'outer.x';
            var y = 0;
            console.log('outer x: ',x);
            console.log('outer y: ',y);

            // inner 함수 내의 지역 스코프
            function inner() {
                var x = 'inner x';
                console.log('inner x', x);

                // if 블록 지역 스코프
                if(true){
                    console.log('x',x);
                    var x = "if x"
                    console.log('x',x);  
                }
            }
            inner();
        }
        outer();

    </script>
	```
### 콜백 Callback {toggle="true"}
	```c++
    <script>
        /*
            콜백 함수(Call Back)
            함수를 호출하는 시점이 바뀌어진 형태의 함수
            기존방식: 사용자(개발자)가 함수 직접정의 -> 정의된 함수를 호출(call)하여 결과를 반환받는 방식
            callback: 콜백 함수에 인자로 로직이 담긴 함수를(함수주소) 전달하여 콜백함수로부터 처리된 결과를 반환받는 방식
        */

        // 함수 정의
         function func1(n1, n2){ 
             console.log("func1(n1,n2)..call");
             return n1+n2;
         }

         // 함수 실행(CALL)
         const r1 = func1(10, 20);   // Call-by-Value: 값(Value) 전달을 통한 함수 직접 실행(Call)
         console.log("r1", r1);
        
         // 콜백함수(n1, n2: Value, logic: function 함수명(함수의 위치, 메모리 주소: 참조값))
         function callbackFunc(n1, n2, logic){
             console.log("callbackFunc start ------------");
             const result = logic(n1, n2);   // 외부로부터 받은 함수를 내부에서 call
             console.log("result",result);
             console.log("callbackFunc end ----------");
         }
         callbackFunc(100, 200, func1); // 콜백 함수의 call
         console.log("-------1------");
         callbackFunc(10, 20, (n1, n2)=> {return n2-n1});
         console.log("-------2------");
         callbackFunc(500, 300, (n1, n2) => {return (n1>n2) ?n1-n2  :n2-n1;});        

         // Callback 함수로 Map 만들기
         const arr = [
             { "id": "111", "name": "티모", age: 555, "addr": "대구" },
             { "id": "222", "name": "렝가", age: 333, "addr": "인천" },
             { "id": "333", "name": "워윅", age: 222, "addr": "부산" },
             { "id": "444", "name": "문도박사", age: 111, "addr": "울산" },
             { "id": "555", "name": "이즈리얼", age: 99, "addr": "창원" }
         ]

         // 제공되는 배열함수 map
         const r1 = arr.map((item)=>{return {"id":item.id, "addr":item.addr}})
         console.log('r1',r1);
        
         // 콜백함수로 만든 유사 map
         function customMap(array, func) {
             // console.log(array);            
             let newArray = [];
             for (let i= 0; i<array.length; i++){
                 // console.log(array[i]);
                 const newItem= func(array[i])
                 console.log(newItem);
                 newArray.push(newItem);
             }
             return newArray;
         }

         // 콜백함수 실행
         const r2 = customMap(arr,(item)=>{return{"id":item.id,"addr":item.addr}})
         console.log("r2", r2);
        
         console.log("---------------");
        
        // 미니문제
        // 여기에 작성하세요(점수가 n점 이상인 학생만 pass)

        // 기대 출력
        // [ { name: '철수', grade: 'pass' },
        //   { name: '민수', grade: 'pass' },
        //   { name: '태호', grade: 'pass' } ]        

         const students = [
             { name: "철수", score: 85 },
             { name: "영희", score: 42 },
             { name: "민수", score: 91 },
             { name: "지현", score: 55 },
             { name: "태호", score: 73 }
         ];
        
        
         function customMap2(students,cutline,func){
             let newArray = [];
             for (let i= 0; i<students.length; i++){
                 //console.log(students[i]);
                 const passItem= func(students[i], cutline);

                 if(passItem) newArray.push(passItem);
             }
             return newArray;    
         }

        
         const result = customMap2(students, 60, (item,cutline)=>{return (item.score >= cutline) && {'name':item.name, 'grade':'pass'}});
       
         console.log("result",result);
       
       
        // closure + callback
        
        // Callback 함수로 Map 만들기
        const arr = [
            { "id": "111", "name": "티모", age: 555, "addr": "대구" },
            { "id": "222", "name": "렝가", age: 333, "addr": "인천" },
            { "id": "333", "name": "워윅", age: 222, "addr": "부산" },
            { "id": "444", "name": "문도박사", age: 111, "addr": "울산" },
            { "id": "555", "name": "이즈리얼", age: 99, "addr": "창원" }
        ]
        
        // 콜백함수로 만든 유사 map + closure
        function customMap(array) {
            // state(클로저 대상)     
            let newArray = [];
            // inner Function
            function map(func){
                for (let i= 0; i<array.length; i++){
                    // console.log(array[i]);
                    const newItem= func(array[i])
                    console.log(newItem);
                    newArray.push(newItem);
                }
                return newArray;
            }
            return {"map":map}
        }

        // 콜백함수 실행
        const closureFunc = customMap(); // map 함수 리턴
        customMap(arr);
        console.log(customMap(arr).map((item)=>{return{"id":item.id,"addr":item.addr}}));
        

        // const r2 = customMap(arr,(item)=>{return{"id":item.id,"addr":item.addr}})
        // console.log("r2", r2);

    </script>
	```
