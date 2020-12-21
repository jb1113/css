# BOX MODEL

- BOX MODEL

    HTML의 모든 요소는 사각형의 박스 형태로 만들어집니다.
    박스는 총 4가지의 세분된 영역으로 구성되어있으며 영역마다 다양한 스타일을 적용할 수 있습니다.
    이 4가지 영역을 통틀어서 박스 모델(BOX MODEL)이라고 합니다.

    문서를 배치할 때 브라우저의 렌더링 엔진은 표준 CSS 기본 박스 모델에 따라 각 요소를 사각형 상자로 나타냅니다.
    CSS를 이용해 이 상자의 크기, 위치 및 속성(색상, 배경, 테두리 크기 등)을 변경할 수 있습니다.

    ### BOX MODEL의 구성

    [https://www.edwith.org/viewer/image?src=https%3A%2F%2Fcphinf.pstatic.net%2Fmooc%2F20180930_36%2F1538294754143G8s2p_PNG%2F1234.png](https://www.edwith.org/viewer/image?src=https%3A%2F%2Fcphinf.pstatic.net%2Fmooc%2F20180930_36%2F1538294754143G8s2p_PNG%2F1234.png)

    ### Content 영역

    요소의 실제 내용을 포함하는 영역입니다. 따라서 크기는 내용의 너비 및 높이를 나타냅니다.

    ### Padding 영역

    content 영역과 테두리 사이의 여백을 padding이라고 합니다.
    content 영역이 배경, 색 또는 이미지가 있을 때 padding 영역까지 영향을 미칩니다.
    이에 따라 padding을 content의 연장으로 볼 수도 있습니다.

    ### Boarder 영역

    content 영역을 감싸는 테두리 선을 border라고 합니다.

    ### Margin 영역

    border 바깥쪽의 영역을 margin 이라고 합니다.
    border 영역을 다른 요소와 구별하기 위해 쓰이는 빈 영역입니다.
    즉, 주변 요소와의 여백(간격)을 margin을 이용해 지정할 수 있습니다.

    ---

    ### 실습 코드

    ```html
    <!DOCTYPE html>
    <html lang="ko">
    	<head>
    		<meta charset="UTF-8">
    		<title>BOX MODEL</title>
    		<style>
    			div {
    				border: 10px solid #000000;
    				padding: 20px;
    				margin: 30px;
    			}
    		</style>
    	</head>
    	<body>
    		<div>BOX MODEL</div>
    	</body>
    </html>
    ```

    ---

    ### 참고자료

    [Introduction to the CSS basic box model](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Box_Model/Introduction_to_the_CSS_box_model)

    [The box model](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/The_box_model)

    [CSS Box Model](https://www.w3schools.com/css/css_boxmodel.asp)

- border

    border 속성은 요소의 테두리에 관련된 속성을 지정할 때 사용합니다.
    테두리의 굵기, 모양, 색상을 지정할 수 있는 속성들이 있으며, 앞서 배웠던 background 속성처럼 여러 속성을 축약하여 적용할 수도 있습니다.

    ### border 관련 속성

    ### border-width (default=medium)

    선의 굵기를 지정하는 속성입니다.
    border-top-width, border-bottom-width, border-left-width, border-right-width를 이용하여 상, 우, 하, 좌의 선의 굵기를 다르게 표현할 수 있습니다.

    ```css
    border-width: [top][right][bottom][left];
    ```

    속성 값으로 단위와 키워드를 사용할 수 있습니다.

    - 단위 : px, em, rem, ... (%, 정수 단위 사용불가)
    - 키워드 : thin, medium, thick

    ### border-style (default=none)

    선의 모양을 지정하는 속성입니다.
    border-top-style, border-bottom-style, border-left-style, border-right-style을 이용하여 상, 우, 하, 좌의 선의 모양을 다르게 표현할 수 있습니다.

    ```css
    border-style: [top][right][bottom][left];
    ```

    또한, 위처럼 축약하여 공백을 이용해 각 방향에 대한 스타일을 지정할 수도 있습니다.

    - none : border를 표시 하지 않습니다.
    - sollid : border를 실선 모양으로 나타냅니다.
    - double : border를 이중 실선 모양으로 나타냅니다.
    - dotted : border를 점선 모양으로 나타냅니다.

    그 밖에도 dashed, double, groove, ridge, inset, outset 등의 다양한 스타일이 있습니다.

    ### border-color (default=currentColor)

    선의 색상을 지정하는 속성입니다.
    border-top-color, border-bottom-color, border-left-color, border-right-color를 이용하여 상, 우, 하, 좌의 선의 색상을 다르게 표현할 수 있습니다.

    ```css
    border-color: [top][right][bottom][left];
    ```

    또한, 위처럼 축약하여 공백을 이용해 각 방향에 대한 색상을 지정할 수도 있습니다.
    색상을 일반적인 CSS 색상 값 사용 방식과 같습니다.

    ### border 축약

    ```css
    border: [-width][-style][-color];
    ```

    위와 같이 공백으로 구분해 축약하여 사용할 수 있고, 정의되지 않은 속성값에 대해서는 기본값이 적용됩니다.

    ---

    ### 실습 코드

    ```css
    /* 속성 */
    border-width: 1px; /* 두께 <length> | thin | medium | thick */
    border-style: solid; /* 종류 none | hidden | dotted | dashed | solid | double | groove | ridge | inset | outset */
    border-color: #000; /* 색상 */

    /* 축약형 */
    border: 1px solid #000; /* 단축 속성 */
    border-left: 6px solid red; /* 보더 왼쪽 */
    border-width: 6px; /* 보더 두께 */
    border-width: 6px 3px; /* 보더 상하, 좌우 두께 */
    border-width: 6px 3px 4px /* 보더 상, 우(좌), 하 두께 */
    border-width: 6px 3px 4px 1px /* 보더 상, 우, 하, 좌 두께 */
    ```

    ```html
    <!DOCTYPE html>
    <html lang="ko">
    	<head>
    		<meta charset="UTF-8">
    		<title>border</title>
    		<style>
    			div {
    				border-width: 10px;
    				border-style: solid;
    				border-color: #000;
    				
    				/* 축약형 */
    				border: 10px solid #000;
    		</style>
    	</head>
    	<body>
    		<div>border property</div>
    	</body>
    </html>
    ```

    ---

    ### 참고자료

    [- CSS: Cascading Style Sheets | MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value#currentcolor_keyword)

    [border](https://developer.mozilla.org/en-US/docs/Web/CSS/border)

    [CSS Borders](https://www.w3schools.com/css/css_border.asp)

- padding

    padding 영역은 border와 content 사이의 여백을 말합니다.

    ### padding 관련 속성

    padding의 기본값은 0이며, 속성 값으로 길이 단위인 length, 요소의 width에 상대적인 크기인 percent, initial, inherit으로 선언할 수 있습니다. (음수 값은 허용되지 않습니다.)
    요소 각 면에 padding을 지정하는 속성으로 padding-top, padding-right, padding-bottom, padding-left가 있습니다.

    ```css
    padding: length|percent|initial|inherit;
    ```

    ### padding-top

    content 영역의 위쪽 여백을 지정합니다.

    ```css
    padding-top: 0;
    ```

    ### padding-right

    content 영역의 오른쪽 여백을 지정합니다.

    ```css
    padding-right: 10px;
    ```

    ### padding-bottom

    content 영역의 아래쪽 여백을 지정합니다.

    ```css
    padding-bottom: 20%;
    ```

    ### padding-left

    content 영역의 왼쪽 여백을 지정합니다.

    ```css
    padding-left: 30px;
    ```

    padding-top,right,bottom,left를 사용하여 요소 네면 모두에 대해 다른 padding 값을 설정할 수 있습니다.

    ### padding 축약

    ```css
    padding: [-top][-right][-bottom][-left];
    ```

    기본적으로 padding의 4가지 속성을 위와 같이 축약하여 사용할 수 있습니다.
    속성의 순서는 상, 우, 하, 좌 순으로 고정되어 있으며 위쪽을 기준으로 시계방향으로 선언합니다.

    축약형으로 사용할 때 반드시 4개의 속성에 대한 값을 모두 적어야 하는 것은 아니며 속성 값으로 1~4개의 값을 사용할 수 있으며 border에서는 축약형 사용 시 정의되지 않은 속성값에 대해서 기본값이 적용되었지만, padding은 조금 다른 방식으로 동작합니다.
    그 이유로 상하, 좌우 영역의 값이 같은 경우 하나로 합쳐서 적용할 수 있기 때문입니다.

    ```css
    /* 상,우,하,좌 네 면의 값이 모두 다른 경우 */
    padding: 10px 20px 30px 40px;
    /* 좌,우 값이 같고 상,하 값이 다른 경우 */
    padding: 10px 20px 30px; /* 좌,우의 값은 20px */
    /* 상,하 값이 같고 좌,우 값이 같은 경우 */
    padding: 10px 20px; /* 상,하의 값은 10px 좌,우 동일하게 20px */
    /* 상,우,하,좌 값이 모두 같은 경우 */
    padding: 10px; /* 상,우,하,좌의 값은 10px */
    ```

    참고로 CSS에서 0 값에 대해서는 단위를 따로 적지 않습니다.

    ---

    ### 실습 코드

    ```html
    <!DOCTYPE html>
    <html lang="ko">
    	<head>
    		<meta charset="UTF-8">
    		<title>padding</title>
    		<style>
    			div {
    				padding-top: 10px;
    				padding-right: 20px;
    				padding-bottom: 30px;
    				padding-left: 40px;
    				
    				/* 축약형 */
    				border: 10px 20px 30px 40px;
    		</style>
    	</head>
    	<body>
    		<div>padding property</div>
    	</body>
    </html>
    ```

    ---

    ### 참고자료

    [padding](https://developer.mozilla.org/en-US/docs/Web/CSS/padding)

    [CSS Padding](https://www.w3schools.com/css/css_padding.asp)

- margin