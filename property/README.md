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

- padding
- margin
- width
- height