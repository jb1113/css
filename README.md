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

- CSS 문법과 CSS의 적용

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

- 선택자

    ### 선택자(selector)란?

    선택자는 복잡하고 다양한 요소들 사이에서 내가 원하는 요소만을 선택할 수 있도록 해줍니다.
    완성도 있는 디자인을 표현하기 위해서는 반드시 내가 원하는 요소를 선택할 수 있어야 하기 때문에 선택자는 매우 중요합니다.

    ### 요소 선택자

    선택자 중에 가장 기본이 되는 선택자이며, 태그 선택자라고도 합니다.

    ```css
    h1 { color: blue; }
    h2 { color: blue; }
    h3 { color: blue; }
    h4 { color: blue; }
    h5 { color: blue; }
    h6 { color: blue; }
    ```

    요소 선택자는 위 코드처럼 선택자 부분에 태그 이름이 들어갑니다.
    문서 내에 선택자에 해당하는 모든 태그, 요소에 스타일 규칙이 적용됩니다.

    ### 전체 선택자

    ```css
    * { color: red; }
    ```

    *(별표, asterisk) 기호로 문서 내의 모든 요소를 선택할 수 있습니다.
    이렇게 선언하면, 한 번의 선언만으로 문서 내에 모든 요소에 스타일 규칙이 적용됩니다.
    전체 선택자는 매우 편리하지만 성능에 좋지 않으므로 될 수 있으면 사용을 지양합니다.

    ### 그룹화

    선택자는 쉼표를 이용해서 그룹화를 할 수 있습니다.

    ```css
    h1, h2, h3, h4, h5, h6 { color: blue; }
    ```

    위 코드는 요소 선택자의 예제 코드와 동일한 동작을 하는 코드입니다.
    선택자뿐만 아니라 선언들도 그룹화가 가능합니다.

    ```css
    h1 { color: blue; font-size: 2em; background-color: yellow; }
    ```

    그리고 마지막으로 선택자와 선언이 동시에 그룹화도 가능합니다.

    ```css
    h1, h2, h3, h4, h5, h6 { color: blue; font-size: 2em; background-color: yellow; }
    ```

    ---

    ### 실습 코드

    ```html
    <!DOCTYPE html>
    <html lang="ko">
    	<head>
    		<meta charset="UTF-8">
    		<title>css</title>
    		<style>
    			h1 { color: blue; font-size: 2em; background-color: yellow; }
    		</style>
    	</head>
    	<body>
    		<h1>Hello, CSS</h1>
    		<p>The language for styling web pages</p>
    	</body>
    </html>
    ```

    ---

    ### class 선택자

    요소에 구애받지 않고 스타일 규칙을 적용할 수 있는 가장 일반적인 방법은 class 선택자를 활용하는 것입니다.
    class 선택자를 사용하기 위해서는 HTML을 수정해 class 속성을 추가해야 합니다.
    class 속성은 글로벌 속성이므로 어느 태그에서도 사용할 수 있습니다.
    class 속성에 값을 넣게 되면 class 선택자를 이용해서 해당 요소에 스타일 규칙을 적용할 수 있습니다.

    ```html
    <style>
    	.foo { font-size: 30px; }
    </style>

    ...
    <p class="foo"> ... </p>
    ```

    위 코드처럼 `<p>` 태그의 class 속성의 값으로 'foo'라는 값을 넣었다면 CSS에서 그 값('foo')을 선택자로 지정하면 됩니다.
    클래스 선택자를 쓸 때는 맨 앞에 마침표(.)를 찍어주셔야 합니다.
    이렇게 되면 어느 요소든지 class 속성값이 'foo'로 선언된 요소가 있다면 해당 스타일 규칙을 적용받게 됩니다.

    ```html
    <style>
    	.html { color: red; }
    	.css { text-decoration: underline; }
    </style>

    ...
    <dl>
    	<dt class="html">HTML</dt>
    	<dd><span class="html">HTML</span>은 문서의 구조를 나타냅니다.</dd>
    	<dt class="css">CSS</dt>
    	<dd><span class="css">CSS</span>는 문서의 표현을 나타냅니다.</dd>
    </dl>
    ```

    ### 다중 class

    class 속성은 꼭 하나의 값만 가질 수 있는 것은 아닙니다.
    공백으로 구분하여 여러 개의 class 값을 넣을 수 있습니다.

    ```html
    <style>
    	.foo { font-size: 30px; }
    	.bar { color: blue; }
    </style>

    ...
    <p class="foo bar"> ... </p>
    ```

    위의 `<p>` 태그에 class 속성에 'foo'와 'bar' 2개의 값을 공백을 통해 넣었습니다.
    그리고 foo class 선택자에는 폰트의 크기를 30px로, bar class 선택자에는 글자를 파란색으로 적용하는 스타일 규칙이 선언되어 있습니다.
    그렇게 되면 이 `<p>` 태그에는 2개의 규칙이 모두 적용이 됩니다.

    ### id 선택자

    id 선택자는 class 선택자와 비슷합니다.
    아이디 선택자를 쓸 때는 마침표(.) 기호 대신 해시(#) 기호를 씁니다.
    요소에는 class 속성 대신 id 속성만 써주면 됩니다.

    ```html
    <style>
    	#baz { background-color: gray; }
    </style>

    ...
    <p id="baz"> ... </p>
    ```

    이 `<p>` 태그는 id 선택자의 스타일 규칙이 적용됩니다.

    ### class 선택자와의 차이점

    1. . 기호가 아닌 # 기호 사용
    2. 태그의 class 속성이 아닌 id 속성을 참조
    3. 문서 내에 유일한 요소에 사용
    4. 구체성

    가장 큰 차이점은 class와 달리 id는 문서 내에서 유일해야 한다는 점입니다.
    클래스 선택자는 여러 요소에 같은 클래스를 넣고 같은 규칙을 적용할 수 있었습니다.
    그리고 그것이 클래스 선택자의 장점이기도 합니다.
    하지만 id 속성값은 문서 내에 유일하게 사용이 되어야 합니다.
    결국, id 선택자로 규칙을 적용할 수 있는 요소는 단 하나 뿐입니다.
    그리고 마지막으로 구체성의 값이 다릅니다.

    ---

    ### 실습 코드

    ```html
    <!DOCTYPE html>
    <html lang="ko">
    	<head>
    		<meta charset="UTF-8">
    		<title>css</title>
    		<style>
    			.item { background: gray; }
    			.a { color: red; }
    			.b { color: blue; }
    			#special { color: white; }
    		</style>
    	</head>
    	<body>
    		<ul>
    			<li class="item a">first</li>
    			<li class="item b">second</li>
    			<li class="item" id="special">third</li>
    		</ul>
    	</body>
    </html>
    ```

    ---

    ### 선택자의 조합

    선택자는 종류에 상관없이 여러 가지 선택자들을 조합하여 사용할 수 있습니다.
    요소와 클래스를 조합할 수도 있고, 다중 클래스, 아이디와 클래스도 조합이 가능합니다.

    ```css
    /* 요소와 class의 조합 */
    p.bar { ... }

    /* 다중 class */
    .foo.bar { ... }

    /* id와 class의 조합 */
    #foo.bar { ... }
    ```

    첫번째는 요소와 클래스를 조합한 경우입니다.
    이 경우에는 `<p>` 태그이면서 class 속성에 bar가 있어야 적용됩니다.
    두 번째는 다중 클래스의 경우입니다.
    이 경우에는 class 속성에 foo와 bar가 모두 있어야 적용됩니다.
    마지막은 id와 class를 조합한 경우입니다.
    이 경우에는 id가 foo이며 class가 bar인 요소에 적용됩니다.

    ```html
    <style>
    	.html { color: red; }
    	.css { text-decoration: underline; }
    	.html.css { border: 1px solid; }
    </style>

    ...
    <dl>
    	<dt class="html">HTML</dt>
    	<dd><span class="html">HTML</span>은 문서의 구조를 나타냅니다.</dd>
    	<dt class="css">CSS</dt>
    	<dd><span class="css">CSS</span>는 문서의 표현을 나타냅니다.</dd>
    	<dt class="html css">JavaScript</dt>
    	<dd><span class="html css">JavaScript</span>는 문서의 동작을 나타냅니다.</dd>
    </dl>
    ```

    ### 속성 선택자

    **단순 속성으로 선택**

    ```html
    <style>
    	p[class] { color: green; }
    	p[class][id] { text-decoration: underline; }
    </style>

    ...
    <p class="foo">HTML</p>
    <p class="bar">CSS</p>
    <p class="baz" id="title">JavaScript</p>
    ```

    속성 선택자는 대괄호를 이용해서 선언하며 대괄호 안에 속성 이름이 들어갑니다.
    요소에 해당 이름의 속성이 있다면 해당 사항이 적용됩니다.
    위 CSS 코드는 요소 선택자와의 조합으로 이루어진 코드입니다.
    첫번째는 `<p>` 태그 이면서 class 속성이 있는 요소이면 color: green 규칙이 적용됩니다.
    두번째는 `<p>` 태그 이면서 class 속성과 id 속성이 함께 있어야 text-decoration: underline 규칙이 적용됩니다.
    바로 위 HTML 코드에는 3개의 `<p>` 태그가 있습니다.
    그렇다면 이 3개의 `<p>` 태그에는 각자 어떤 스타일이 적용될까요?
    `p[class]` 선택자의 규칙은 class 속성만 존재하면 적용이 되기 때문에 3가지 요소 모두에 적용됩니다.
    `p[class][id]` 선택자의 규칙은 class 속성과 id 속성 모두 있는 요소만 해당하기 때문에 마지막 요소에만 적용됩니다.
    두 규칙 모두 속성의 값은 상관하지 않습니다.

    **정확한 속성값으로 선택**

    정확한 속성값으로 선택은 제목 그대로 속성의 값으로 요소를 선택합니다.
    선택자는 대괄호 안에 속성 이름과 속성값을 다 적으면 됩니다.

    ```css
    p[class="foo"] { color: green; }
    p[id="title"] { text-decoration: underline; }
    ```

    `p[class="foo"]`는 `<p>` 태그 이면서 class 속성의 값이 foo이면 적용되고, `p[id="title"]`는 `<p>` 태그이면서 id 속성의 값이 title이면 적용됩니다.
    위 예제 코드의 3개의 `<p>` 태그 중 첫번째 `<p>` 태그에는 color: green 규칙이 세번째 `<p>` 태그에는 text-decoration: underline 규칙이 적용됩니다.

    **부분 속성값으로 선택**

    부분 속성값으로 선택은 속성 이름과 속성값 사이에 사용되는 기호에 따라 동작이 조금 다릅니다.

    - [class~="foo"] : class 속성의 값이 공백으로 구분한 'foo' 단어가 포함되는 요소 선택
    - [class^="foo"] : class 속성의 값이 'foo'로 시작하는 요소 선택
    - [class$="foo"] : class 속성의 값이 'foo'로 끝나는 요소 선택
    - [class*="foo"] : class 속성의 값이 'foo' 문자가 포함되는 요소 선택

    ```html
    <p class="color hot">red</p>
    <p class="cool color">blue</p>
    <p class="colorful nature">rainbow</p>
    ```

    ```css
    p[class~="color"] { font-style: italic; }
    p[class^="color"] { font-style: italic; }
    p[class$="color"] { font-style: italic; }
    p[class*="color"] { font-style: italic; }
    ```

    위의 코드에서는 모두 class 속성값으로 'color'를 선택합니다.
    요소 순서대로 기호에 따라 규칙이 적용되는 결과는 다음과 같습니다.

    ```css
    p[class~="color"] { font-style: italic; } /* 1, 2번째 요소 */
    p[class^="color"] { font-style: italic; } /* 1, 3번째 요소 */
    p[class$="color"] { font-style: italic; } /* 2번째 요소 */
    p[class*="color"] { font-style: italic; } /* 1, 2, 3번째 요소 */
    ```

    ---

    ### 실습 코드

    ```html
    <!DOCTYPE html>
    <html lang="ko">
    	<head>
    		<meta charset="UTF-8">
    		<title>css</title>
    		<style>
    			p[class~="color"] { font-style: italic; }
    			/* p[class^="color"] { font-style: italic; } */
    			/* p[class$="color"] { font-style: italic; } */
    			/* p[class*="color"] { font-style: italic; } */
    		</style>
    	</head>
    	<body>
    		<p class="color hot">red</p>
    		<p class="cool color">blue</p>
    		<p class="colorful nature">rainbow</p>
    	</body>
    </html>
    ```

    ---

    ### 참고자료

    [Selector (CSS)](https://developer.mozilla.org/en-US/docs/Glossary/CSS_Selector)

    [CSS Selectors Reference](https://www.w3schools.com/cssref/css_selectors.asp)

    [The Difference Between ID and Class | CSS-Tricks](https://css-tricks.com/the-difference-between-id-and-class/)

    [Attribute selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/Attribute_selectors)

    [CSS Attribute Selector](https://www.w3schools.com/css/css_attribute_selectors.asp)