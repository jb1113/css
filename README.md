# CSS 이해하기

- CSS 소개

    **C**ascading **S**tyle **S**heets

    - HTML(마크업 언어)을 꾸며주는 언어
    - HTML이 웹페이지의 **정보**를 표현한다면,
    CSS는 HTML을 보기 좋게 **디자인**하는 역할

    ### CSS와 HTML

    CSS는 간단히 이야기하면, HTML(마크업 언어)를 꾸며주는 표현용 언어입니다.
    HTML이 문서의 정보, 구조를 설계한다면 CSS는 문서를 보기 좋게 디자인합니다.
    CSS는 분명히 HTML과는 독립된 다른 언어지만 마크업 문서 자체가 존재하지 않으면 CSS는 무용지물이나 마찬가지입니다.
    왜냐하면, CSS는 표현을 위한 언어인데 마크업 문서가 없다면 표현할 대상이 없기 때문입니다.
    그래서 CSS는 보통 마크업 언어인 HTML과 같이 묶어서 이야기합니다.

    ### CSS로 표현한 다양한 웹 사이트들

    전 세계에 많은 웹 사이트들이 있습니다.
    그리고 그것들 모두 HTML 태그를 이용해서 만들어졌고, 자주 사용되는 태그의 개수는 10여 개밖에 되지 않습니다.
    결국, 모든 사이트가 비슷한 HTML 태그를 사용해서 만들어졌음에도 불구하고 각각 다양하고 독창적인 디자인으로 표현 가능한 이유가 바로 CSS 덕분입니다.
    CSS는 문서를 디자인하는 강력한 힘을 가졌습니다.

    ---

    ### 참고자료

    [CSS: Cascading Style Sheets](https://developer.mozilla.org/ko/docs/Web/CSS)

    [CSS Zen Garden](http://www.csszengarden.com/)

- CSS 문법

    CSS는 HTML 요소를 꾸며주는 역할을 합니다.
    CSS는 꾸밀 대상이 되는 요소와 그에 대한 스타일 내용으로 이루어져 있습니다.

    ### CSS 구문

    ```css
    h1 { color: gray; font-size: 2em; }
    ```

    - 선택자(selector) : 'h1'
    - 속성(property) : 'color', 'font-size'
    - 값(value) : 'gray', '2em'
    - 선언(declaration) : 'color: gray', 'font-size: 2em'
    - 선언부(declaration block) : '{color: gray; font-size: 2m; }'
    - 규칙(rule set) : 'h1 { color: gray; font-size: 2em; }'

    CSS 파일은 여러 개의 규칙으로 이루어져 있습니다.
    선택자와 선언부 사이, 선언과 선언 사이는 앞뒤로 개행을 해도 상관이 없습니다.
    하지만 속성이름과 속성값 사이에는 개행을 하면 안됩니다.

    [올바른 CSS]

    ```css
    h1
    { color: gray; font-size: 2em; }

    h1 {
    	color: gray;
    	font-size: 2em;
    }
    ```

    [잘못된 CSS]

    ```css
    h1 {
    	color:
    	gray;
    }
    ```

    ### CSS의 속성(Property)과 HTML의 속성(Attribute)

    HTML에도 속성이 있고, CSS에도 속성이 있습니다. 두 가지는 전혀 다른 것입니다.
    HTML의 속성은 영어로 attribute이고, CSS의 속성은 property입니다.
    둘 다 한국어로 번역할 때 '속성'이라고 하므로 잘 구분해야 합니다.

    ### CSS 주석

    CSS의 주석은 아래와 같이 선언합니다.

    ```css
    /* 주석 내용 */

    /*
    	주석은 여러 줄로도
    	작성할 수 있습니다.
    	...
    */
    ```

    ### CSS의 적용

    CSS와 문서를 연결하는 방법은 4가지가 있습니다.

    ### 1. Inline

    Inline은 해당 요소에 직접 스타일 속성을 이용해서 규칙들을 선언하는 방법입니다.
    해당 요소에 직접 입력하기 때문에 선택자는 필요하지 않게 되고, 선언부의 내용만 스타일 속성의 값으로 넣어주면 됩니다.
    Inline 스타일 방식이라고 부릅니다.

    ```html
    <div style="color: gray;">내용</div>
    ```

    Inline 스타일 방식은 코드의 재활용이 되지 않기 때문에 자주 사용하지 않습니다.

    ### 2. Internal

    Internal은 문서에 `<style>` 태그를 활용한 방법입니다.
    `<style>` 태그는 `<head>` 태그 내부에 들어가며 `<style>` 태그 안에 스타일 규칙이 들어갑니다.

    ```html
    <head>
    	<style>
    		div { color: gray; }
    	</style>
    </head>
    ```

    위의 코드로 모든 `<div>` 태그에 같은 스타일을 줄 수 있습니다.
    하지만 이것도 한계가 있습니다.
    많은 페이지가 있는 경우에는 모든 페이지에 저마다의 규칙을 선언해줘야 합니다.
    페이지가 많고 스타일 규칙 내용이 많아지면 결코 쉬운 일이 아닙니다.

    ### 3. External

    External은 외부 스타일 시트 파일을 이용한 방법입니다.
    외부 스타일 시트는 스타일 규칙들을 별도의 외부 파일을 만들어 넣는 방식입니다.
    외부 파일은 확장자가 .css가 되며 css 파일이라고 부릅니다.

    base.css

    ```css
    div { color: gray; }
    ...
    ```

    우선 .css를 확장자로 갖는 CSS 파일을 하나 만들고 스타일 규칙을 선언합니다.
    그다음 `<link>` 태그를 이용해서 CSS 파일을 연결하면 됩니다.

    document.html

    ```html
    <head>
    	<link rel="stylesheet" href="./base.css">
    </head>
    ```

    `<head>` 태그 내부에 `<link>` 태그를 선언한 후 href 속성을 이용하여 CSS 파일의 경로를 적습니다.
    rel 속성은 연결되는 파일이 문서와 어떤 관계인지를 명시하는 속성으로 CSS 파일은 'stylesheet'라고 적어야 합니다.
    외부 스타일 시트 방식으로 스타일을 선언하면 많은 페이지가 있더라도 이 한 줄로 모든 페이지에 같은 스타일을 적용할 수 있습니다.
    또한, 수정이 필요할 때도 CSS 파일을 수정하면 연결된 모든 페이지에 반영할 수 있습니다.
    외부 스타일 시트 방식은 파일 관리가 편하면서도 용량이 작기 때문에 주로 사용되는 방법입니다.

    ### 4. Import

    Import는 스타일 시트 내에서 다른 스타일 시트 파일을 불러오는 방식입니다.

    document.html

    ```html
    <head>
    	<style>
    		@import url("./base.css");
    	</style>
    </head>
    ```

    base.css

    ```css
    @import url("./base.css");
    div { color: gray; }
    ...
    ```

    `<style>` 태그 내부 상단이나 외부 스타일 시트 파일 상단에 선언하는데 성능상 좋지 않아서 거의 쓰이지 않습니다.

    ---

    ### 전체 코드

    ```html
    <!DOCTYPE html>
    <html lang="ko">
    	<head>
    		<meta charset="UTF-8">
    		<title>css</title>
    		<link rel="stylesheet" href="./base.css">
    	</head>
    	<body>
    		<p>Hello, CSS</p>
    		<p>The language for styling web pages</p>
    	</body>
    </html>
    ```

    ---

    ### 참고자료

    [How CSS is structured](https://developer.mozilla.org/en-US/docs/Learn/CSS/First_steps/How_CSS_is_structured)

    [How to add CSS](https://www.w3schools.com/css/css_howto.asp)