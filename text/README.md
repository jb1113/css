# 텍스트

- vertical-align

    CSS를 통해서 텍스트를 수직, 수평 정렬 할 수 있습니다.
    그 중 vertical-align 속성을 이용하여 수직 정렬을 할 수 있습니다.
    이때 주의하실 점은 **block 요소를 제외한 inline 또는 inline-block에서만 해당 속성을 사용**할 수 있습니다.
    따라서, display 속성이 변하지 않는 `<div>`, `<p>` 등과 같은 블록 레벨 요소에는 적용되지 않습니다.

    ### vertical-align 속성 (default=baseline)

    요소의 수직 정렬을 지정하는 속성입니다.

    ```css
    vertical-align: keyword|length|percent|initial|inherit;
    ```

    - keyword : baseline(기본값), sub, super, text-top, text-bottom, middle, top, bottom
    - length : 요소를 지정한 길이만큼 올리거나 내림 (음수 가능)
    - % : 요소를 line-height를 기준으로 올리거나 내림 (음수 가능)

    인라인 요소 또는 테이블 셀 상자의 수직정렬을 지정할 때 사용합니다.
    대부분 부모 요소의 상대적으로 정렬됩니다.

    ### vertical-align 속성의 기준

    vertical-align은 기본 값이 baseline 입니다.
    이전에 타이포그래피 구조에서 설명했듯이 baseline은 소문자 x를 기준으로 하단 라인을 의미합니다.

    - sub : 부모 아래 첨자 기준으로 정렬
    - super : 부모 위 첨자 기준으로 정렬
    - text-top : 부모 텍스트의 맨 위 (Ascender 제외)
    - text-bottom : 부모 텍스트의 맨 아래 (Descender 제외)
    - middle : 부모의 중앙에 위치
    - top : 부모의 맨 위에 위치
    - bottom : 부모의 맨 아래 위치

    - length : px 값 사용시 baseline을 기준으로 이동하며 음수 값도 사용 가능합니다.
    - % : line-height를 기준으로 이동하며 음수 값도 사용 가능합니다.

    ---

    ### 실습 코드

    ```html
    <!DOCTYPE html>
    <html lang="ko">
    	<head>
    		<meta charset="UTF-8">
    		<title>vertical-align</title>
    		<style>
    			p {
    				border: 1px dashed #aaa;
    				padding: 10px;
    				line-height: 1;
    				font-size: 16px;
    			}

    			p span {
    				border: 1px solid #aaa;
    				background-color: rgba(0, 255, 255, 0.5);
    			}

    			p span:nth-child(1) {
    				background-color: rgba(255, 255, 0, 0.5);
    			}

    			p span:nth-child(2), p span:nth-child(4) {
    				font-weight: bold;
    				font-size: 20px;
    			}

    			p span:nth-child(3) {
    				background-color: rgba(0, 0, 0, 0.2);
    			}

    			table {
    				width: 100%;
    				border-collapse: collapse;
    			}

    			table td, table th {
    				border: 1px solid #aaa;
    				height: 50px;
    			}
    		</style>
    	</head>
    	<body>
    		<h1>vertical-align</h1>
    		<p><span>vertical-align:</span>
    			<span style="vertical-align: baseline;">baseline;</span>
    			<span>---</span>
    			<span style="vertical-align: baseline;">수직정렬</span></p>
    		<p><span>vertical-align:</span>
    			<span style="vertical-align: sub;">sub;</span>
    			<span>---</span>
    			<span style="vertical-align: sub;">수직정렬</span></p>
    		<p><span>vertical-align:</span>
    			<span style="vertical-align: super;">super;</span>
    			<span>---</span>
    			<span style="vertical-align: super;">수직정렬</span></p>
    		<p><span>vertical-align:</span>
    			<span style="vertical-align: text-top;">text-top;</span>
    			<span>---</span>
    			<span style="vertical-align: text-top;">수직정렬</span></p>
    		<p><span>vertical-align:</span>
    			<span style="vertical-align: text-bottom;">text-bottom;</span>
    			<span>---</span>
    			<span style="vertical-align: text-bottom;">수직정렬</span></p>
    		<p><span>vertical-align:</span>
    			<span style="vertical-align: middle;">middle;</span>
    			<span>---</span>
    			<span style="vertical-align: middle;">수직정렬</span></p>
    		<p><span>vertical-align:</span>
    			<span style="vertical-align: top;">top;</span>
    			<span>---</span>
    			<span style="vertical-align: top;">수직정렬</span></p>
    		<p><span>vertical-align:</span>
    			<span style="vertical-align: bottom;">bottom;</span>
    			<span>---</span>
    			<span style="vertical-align: bottom;">수직정렬</span></p>
    		<p><span>vertical-align:</span>
    			<span style="vertical-align: 4em;">4em;</span>
    			<span>---</span></p>
    		<p><span>vertical-align:</span>
    			<span style="vertical-align: 4px;">4px;</span>
    			<span>---</span></p>
    		<p><span>vertical-align:</span>
    			<span style="vertical-align: 20%;">20%;</span>
    			<span>---</span></p>
    		<p><span>vertical-align:</span>
    			<span style="vertical-align: -10px;">-10px;</span>
    			<span>---</span></p>

    		<table>
    			<caption>table cell vertical-align</caption>
    			<thead>
    				<tr>
    					<th>속성 값</th>
    				</tr>
    			</thead>
    			<tbody>
    				<tr>
    					<td style="vertical-align: baseline;">vertical-align: baseline;</td>
    				</tr>
    				<tr>
    					<td style="vertical-align: top;">vertical-align: top;</td>
    				</tr>
    				<tr>
    					<td style="vertical-align: middle;">vertical-align: middle;(cell 기본값)</td>
    				</tr>
    				<tr>
    					<td style="vertical-align: bottom;">vertical-align: bottom;</td>
    				</tr>
    				<tr>
    					<td>null</td>
    				</tr>
    			</tbody>
    		</table>
    	</body>
    </html>
    ```

    ---

    ### 참고자료

    [vertical-align](https://developer.mozilla.org/en-US/docs/Web/CSS/vertical-align)

    [CSS vertical-align property](https://www.w3schools.com/cssref/pr_pos_vertical-align.asp)

- text-align

    vertical-align이 인라인 요소의 수직 정렬이었다면, text-align은 인라인 요소의 수평 정렬에 사용됩니다.
    이 속성 또한 블록 레벨 요소에는 적용되지 않습니다.

    ### text-align 속성 (default=left, RTL 언어일 경우 right)

    텍스트의 정렬을 지정하는 속성입니다.

    ```css
    text-align: left|right|center|justify|initial|inherit;
    ```

    기본값은 left이지만 경우에 따라 다릅니다.
    문서의 방향이 LTR(Left To Right) 왼쪽에서 오른쪽 방향인 언어일 경우 left가 기본값이고, RTL(Right To Left)로 오른쪽에서 왼쪽 방향인 언어일 경우 right가 기본값이 됩니다.

    - left : 텍스트를 왼쪽으로 정렬
    - right : 텍스트를 오른쪽으로 정렬
    - center : 텍스트를 중앙으로 정렬
    - justify : 텍스트를 라인 양쪽 끝으로 붙여서 정렬 (마지막 라인은 정렬하지 않음)

    ### text-align과 display의 관계

    text-align은 inline-level 요소에만 적용되며, block-level에 적용할 수 없습니다.
    만약, 해당 속성을 **블록 요소에 선언할 경우 블록 요소 안에 있는 인라인 요소들의 정렬을 정의**합니다.

    ```css
    div {
    	text-align: center;
    	width: 100px;
    	height: 100px;
    	background: red;
    }

    ...
    <div>text-align</div>
    ```

    위의 경우 `**<div>` 요소가 전체 화면에서 가운데 정렬이 되는것이 아니라, `<div>` 요소 안에 있는 인라인 레벨인 텍스트에 적용이 되어 텍스트가 가운데 정렬되는 것을 확인**할 수 있습니다.
    만약 `<div>` 요소 자체를 화면 가운데로 정렬하고 싶다면 margin 속성을 이용하여 auto 값을 주어 가운데로 정렬할 수 있습니다.

    때문에 **인라인 레벨 요소들을 정렬**하기 위해서는 **text-align(center) 속성**을 사용하고, **블록 레벨 요소들을 정렬**하기 위해서는 **margin(auto) 속성**을 사용합니다.

    ---

    ### 실습 코드

    ```html
    <!DOCTYPE html>
    <html lang="ko">
    	<head>
    		<meta charset="UTF-8">
    		<title>text-align</title>
    		<style>
    			p {
    				border: 1px solid #ccc;
    				padding: 10px;
    				max-width: 630px;
    			}
    		</style>
    	</head>
    	<body>
    		<h1>text-align</h1>
    		<h2>left</h2>
    		<p style="text-align: left;">Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsam aspernatur vitae sapiente laudantium velit quo unde cupiditate autem, harum eaque natus perferendis ducimus saepe libero, voluptatibus voluptates possimus.</p>
    		<h2>right</h2>
    		<p style="text-align: right;">Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsam aspernatur vitae sapiente laudantium velit quo unde cupiditate autem, harum eaque natus perferendis ducimus saepe libero, voluptatibus voluptates possimus.</p>
    		<h2>center</h2>
    		<p style="text-align: center;">Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsam aspernatur vitae sapiente laudantium velit quo unde cupiditate autem, harum eaque natus perferendis ducimus saepe libero, voluptatibus voluptates possimus.</p>
    		<h2>justify</h2>
    		<p style="text-align: justify;">Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsam aspernatur vitae sapiente laudantium velit quo unde cupiditate autem, harum eaque natus perferendis ducimus saepe libero, voluptatibus voluptates possimus.</p>
    	</body>
    </html>
    ```

    ---

    ### 참고자료

    [text-align](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align)

    [CSS text-align property](https://www.w3schools.com/cssref/pr_text_text-align.asp)

- text-indent

    텍스트의 들여쓰기를 지정하는 속성입니다.

    ### text-indent 속성 (default=0)

    ```css
    text-indent: length|percent|initial|inherit;
    ```

    - length : px, em 등 고정 수치로 지정할 수 있습니다. 음수 가능
    - % : 부모 요소의 width를 기준으로 퍼센트로 지정할 수 있습니다.

    length 값의 경우 문단의 첫 줄에 대한 들여쓰기를 수행합니다.
    음수 값을 사용할 수 있으며, 음수 값 사용시 왼쪽으로 이동합니다.
    percent 값의 경우 텍스트를 포함하는 컨테이너 블록의 width(부모의 width)를 기준으로 변환된 백분율 값으로 들여쓰기 합니다.

    ---

    ### 실습 코드

    ```html
    <!DOCTYPE html>
    <html lang="ko">
    	<head>
    		<meta charset="UTF-8">
    		<title>text-indent</title>
    	</head>
    	<body>
    		<h1>text-indent</h1>
    		<h2>length 1em</h2>
    		<p style="text-indent: 1em;">Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsam aspernatur vitae sapiente laudantium velit quo unde cupiditate autem, harum eaque natus perferendis ducimus saepe libero, voluptatibus voluptates possimus.</p>
    		<h2>length 40px</h2>
    		<p style="text-indent: 40px;">Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsam aspernatur vitae sapiente laudantium velit quo unde cupiditate autem, harum eaque natus perferendis ducimus saepe libero, voluptatibus voluptates possimus.</p>
    		<h2>percentage 15%</h2>
    		<p style="text-indent: 15%;">Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsam aspernatur vitae sapiente laudantium velit quo unde cupiditate autem, harum eaque natus perferendis ducimus saepe libero, voluptatibus voluptates possimus.</p>
    		<h2>length -40px</h2>
    		<p style="text-indent: -40px;">Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsam aspernatur vitae sapiente laudantium velit quo unde cupiditate autem, harum eaque natus perferendis ducimus saepe libero, voluptatibus voluptates possimus.</p>
    	</body>
    </html>
    ```

    ---

    ### 참고자료

    [text-indent](https://developer.mozilla.org/en-US/docs/Web/CSS/text-indent)

    [CSS text-indent property](https://www.w3schools.com/cssref/pr_text_text-indent.asp)

- text-decoration

    `<a>` 태그를 사용하면 기본적으로 텍스트 밑에 밑줄이 그어져서 표시되는 것을 확인할 수 있습니다.
    이러한 이유는 브라우저에 따라 다를 수는 있지만 보통 text-decoration이 `<a>` 태그에 대해서 기본값이 다르게 되어 있기 때문입니다.
    text-decoration 속성은 단순 밑줄을 그어주는 것 뿐만 아니라 다양한 줄의 스타일과 모양, 색상 등을 제어할 수 있습니다.

    ### text-decoration 속성 (default=none currentColor solid)

    텍스트의 장식을 지정하는 속성입니다.
    아래 속성들의 단축 속성으로 기본 값은 차례대로 none currentColor solid 값입니다.

    ```css
    text-decoration: text-decoration-line text-decoration-color text-decoration-style|initial|inherit;
    ```

    text-decoration-line : 텍스트 꾸밈의 종류를 지정하는 속성입니다.

    - none : 텍스트 꾸밈을 생성하지 않음 (기본값)
    - underline : 밑줄로 꾸밈을 설정
    - overline : 윗줄로 꾸밈을 설정
    - line-through : 중간을 지나는 줄로 꾸밈을 설정

    text-decoration-color : 텍스트 꾸밈의 색상을 지정하는 속성입니다.

    - currentColor : 기본값

    색상 값을 사용하여 원하는 색상을 지정할 수 있습니다.
    색상 값 적용 방식과 동일합니다.

    text-decoration-style : 텍스트 꾸밈에 사용되는 선의 스타일을 지정하는 속성입니다.

    - solid :  한줄 (기본값)
    - double : 이중선
    - dotted : 점선
    - dashed : 파선
    - wavy : 물결

    ---

    ### 심화

    text-decoration-color에서 기본값은 currentColor 입니다.
    currentColor은 CSS 내에서 색상 값으로 사용할 수 있는 키워드입니다.
    currentColor이 의미하는 바가 무엇이고 어떻게 사용하는지 알아야 합니다.

    ---

    ### 실습 코드

    ```html
    <!DOCTYPE html>
    <html lang="ko">
    	<head>
    		<meta charset="UTF-8">
    		<title>text-decoration</title>
    	</head>
    	<body>
    		<h2>일반적인 경우</h2>
    		<p style="text-decoration: overline;">text-decoration: overline;</p>
    		<p style="text-decoration: underline;">text-decoration: underline;</p>
    		<p style="text-decoration: line-through;">text-decoration: line-through;</p>

    		<h2>부모 내 자식요소가 float의 경우 상속이 해제됩니다</h2>
    		<a href="#" style="text-decoration: overline;"><span style="float: left;">text-decoration: overline;</span></a>
    		<br>
    		<h2>부모 내 자식요소가 absolute의 경우 상속이 해제됩니다</h2>
    		<a href="#" style="text-decoration: overline;"><span style="position: absolute;">text-decoration: overline;</span></a>
    	</body>
    </html>
    ```

    ---

    ### 참고자료

    [text-decoration](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration)

    [CSS text-decoration property](https://www.w3schools.com/cssref/pr_text_text-decoration.asp)

    [CSS text-decoration-line property](https://www.w3schools.com/cssref/css3_pr_text-decoration-line.asp)

    [CSS text-decoration-color property](https://www.w3schools.com/cssref/css3_pr_text-decoration-color.asp)

    [CSS text-decoration-style property](https://www.w3schools.com/cssref/css3_pr_text-decoration-style.asp)

    [- CSS: Cascading Style Sheets | MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value#currentcolor_keyword)

- 단어 관련 속성

    CSS에는 텍스트에 대한 속성뿐만 아니라 단어에 대해서 어떻게 표현할지 지정할 수 있는 속성들이 있습니다.
    몇가지 예를 들자면 단어의 공백을 어떻게 처리할지, 단어 사이의 간격을 얼마만큼 가질지, 줄 바꿈이 되는 지점은 어디로 둘지 등을 지정할 수 있습니다.

    ### white-space 속성 (default=normal)

    요소 안의 공백을 어떻게 처리할지 지정하는 속성입니다.

    ```css
    white-space: normal|nowrap|pre|pre-line|pre-wrap|initial|inherit;
    ```

    - normal : 공백과 개행을 무시하고, 필요한 경우에 자동 줄바꿈 발생 (기본값)
    - nowrap : 공백과 개행을 무시하고, 자동 줄바꿈이 일어나지 않음
    - pre : 공백과 개행을 표현하고, 자동 줄바꿈이 일어나지 않음
    - pre-line : 공백은 무시하고, 개행만 표현. 필요한 경우에 자동 줄바꿈 발생
    - pre-wrap : 개행은 무시하고, 공백만 표현. 필요한 경우 자동 줄바꿈 발생

    ### letter-spacing 속성 (default=normal)

    글자간의 간격(자간)을 지정하는 속성입니다.

    ```css
    letter-spacing: normal|length|initial|inherit;
    ```

    - normal : 현재 글꼴의 기본 간격 (기본값)
    - length : 지정한 수치만큼 자간을 지정합니다. 음수 가능

    ### word-spacing 속성 (default=normal)

    단어 사이의 간격을 지정하는 속성입니다.

    ```css
    word-spacing: normal|length|initial|inherit;
    ```

    - normal : 현재 글꼴의 단어 간격 (기본값)
    - length : 지정한 수치만큼 단어 사이의 간격을 지정합니다. 음수 가능

    ### word-break 속성 (default=normal)

    단어가 라인 끝에 나올 경우 어떻게 처리할지(중단점)를 지정하는 속성입니다.

    ```css
    word-break: normal|break-all|keep-all|initial|inherit;
    ```

    - normal : 기본 줄바꿈 규칙 (기본값)
    중단점은 공백이나 하이픈(-)이며 한중일(CJK)는 음절이 중단점
    - break-all : 기본 중단점은 음절이며 모든 글자가 요소를 벗어나지 않고 개행
    - keep-all : 기본 중단점은 공백이나 하이픈(-)이며 한중일(CJK)에서는 줄을 바꿀때 단어를 끊지 않음

    ### word-wrap 속성 (default=normal)

    요소를 벗어난 단어의 줄바꿈을 지정하는 속성입니다.

    ```css
    word-wrap: normal|break-word|initial|inherit;
    ```

    - normal : 기본 줄바꿈 규칙대로 중단점에서 개행 (기본값)
    - break-word : 모든 글자가 요소를 벗어나지 않고 강제로 개행

    ---

    ### 심화

    word-break 속성과 word-wrap 속성은 언어의 종류에 따라 다르게 동작합니다.
    언어의 종류는 한중일(CJK)의 아시아권 언어와 그 외의 언어를 말합니다.
    종류에 따라 어떤 차이를 가지고 동작하는지 구분할 줄 알아야 합니다.

    ---

    ### 참고자료

    [white-space](https://developer.mozilla.org/en-US/docs/Web/CSS/white-space)

    [CSS white-space property](https://www.w3schools.com/cssref/pr_text_white-space.asp)

    [letter-spacing](https://developer.mozilla.org/en-US/docs/Web/CSS/letter-spacing)

    [CSS letter-spacing property](https://www.w3schools.com/cssref/pr_text_letter-spacing.asp)

    [word-spacing](https://developer.mozilla.org/en-US/docs/Web/CSS/word-spacing)

    [CSS word-spacing property](https://www.w3schools.com/cssref/pr_text_word-spacing.asp)

    [word-break](https://developer.mozilla.org/en-US/docs/Web/CSS/word-break)

    [CSS word-break property](https://www.w3schools.com/cssref/css3_pr_word-break.asp)

    [overflow-wrap](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-wrap)

    [https://www.w3schools.com/cssref/css3_pr_word-wrap.asp](https://www.w3schools.com/cssref/css3_pr_word-wrap.asp)

    [CSS Text](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Text)