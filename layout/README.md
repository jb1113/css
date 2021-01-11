# 레이아웃

- display

    모든 요소는 기본적으로 가지고 있는 display 값이 있습니다.
    그리고 그 값에 따라 블록 레벨, 인라인 레벨 등 렌더링 박스의 유형이 결정됩니다.
    display 속성을 통해 해당 요소의 렌더링 박스의 유형을 변경할 수 있으며, 심지어 렌더링 여부도 결정할 수 있습니다.

    ### display 속성(default=? [요소마다 다름])

    요소의 렌더링 박스 유형을 결정하는 속성입니다.

    ```css
    display: value;
    ```

    - none : 요소가 렌더링 되지 않음
    - block : 블록 레벨 요소처럼 렌더링
    - inline : 인라인 레벨 요소처럼 렌더링
    - inline-block : 인라인 요소처럼 렌더링(배치) 되지만 블록 레벨의 성질을 가짐
    * height나 width 등과 같은 박스 모델 속성을 적용할 수 있음

    이외에도 list-item, flex, inline-flext, table, table-cell 등 다양한 속성값 존재

    ```html
    <!DOCTYPE html>
    <html lang="ko">
    	<head>
    		<meta charset="UTF-8">
    		<title>display</title>
    	</head>
    	<body>
    		<div>
    			<div style="display: none;">box1</div>
    		</div>
    		<div>
    			<div style="display: inline;">box2</div>
    		</div>
    		<div>
    			<div style="display: block;">box3</div>
    		</div>
    		<div>
    			<div style="display: inline-block;">box4</div>
    		</div>
    	</body>
    </html>
    ```

    ### inline과 inline-block의 차이

    inline-block의 경우 inline처럼 자기 콘텐츠 크기만큼 영역을 차지합니다.
    inline-block은 inline 레벨 요소처럼 화면에 나타나지만 block의 성질을 갖고있다고 이해하면 됩니다.

    ```html
    <div>
    	<div style="display: inline;">box</div>
    </div>

    <div>
    	<div style="display: inline-block;">box</div>
    </div>
    ```

    display: inline;과 display: inline-block;의 box model을 비교했을때 inline의 경우에는 auto, auto로 되어있고 inline-block의 경우에는 해당 내용의 width height 값이 선언되어 있습니다.

    이는 block처럼 rendering 값을 갖는다는 뜻입니다.
    display가 어떤 값을 갖는지에 따라서 box model의 속성들을 적용할 수 있는지 없는지의 유무가 정해집니다.

    ### inline 레벨 요소 사이의 공백과 개행

    ```html
    .inline {
    	font-size: 30px;
    	background: pink;
    }

    .inlineblock {
    	font-size: 30px;
    	background: skyblue;
    }

    ...
    <div>
    	<div style="display: inline;" class="inline">box</div>
    	<div style="display: inline;" class="inline">box</div>
    	<div style="display: inline;" class="inline">box</div>
    </div>

    <div>
    	<div style="display: inline;" class="inline">box</div><div style="display: inline;" class="inline">box</div>
    	<div style="display: inline;" class="inline">box</div>
    </div>

    <div>
    	<div style="display: inline;" class="inline">box</div> <div style="display: inline;" class="inline">box</div> <div style="display: inline;" class="inline">box</div>
    </div>

    <div>
    	<div style="display: inline-block;" class="inlineblock">box</div>
    	<div style="display: inline-block;" class="inlineblock">box</div>
    	<div style="display: inline-block;" class="inlineblock">box</div>
    </div>

    <div>
    	<div style="display: inline-block;" class="inlineblock">box</div><div style="display: inline-block;" class="inlineblock">box</div>
    	<div style="display: inline-block;" class="inlineblock">box</div>
    </div>

    <div>
    	<div style="display: inline-block;" class="inlineblock">box</div> <div style="display: inline-block;" class="inlineblock">box</div> <div style="display: inline-block;" class="inlineblock">box</div>
    </div>
    ```

    inline 요소의 경우 공백과 개행에 대해서 하나의 여백으로 받아들입니다.
    공백도 하나의 inline box를 갖습니다.
    따라서 inline과 inline-block의 경우 태그 사이의 공백이나 개행이 있을 경우 약 4px의 여백을 가집니다.

    ### display와 box model의 관계

    display 속성의 값에 따라 box model의 속성들의 적용 유무를 확인할 수 있습니다.

    ```css
    display       width  height  margin  padding  border
    block           O      O       O        O       O
    inline          X      X      좌/우    좌/우(*)  좌/우(*)
    inline-block    O      O       O        O       O
    ```

    **inline 요소의 padding/border 속성이 좌/우(*)만 적용이 되는 이유**

    실제로 inline 요소의 padding/border는 좌/우 뿐만아니라 상/하에도 적용이 됩니다.

    **parent는 `<div>`, child는 `<span>`**

    [https://www.boostcourse.org/viewer/image?src=https%3A%2F%2Fcphinf.pstatic.net%2Fmooc%2F20180925_192%2F15378194530768HSiV_PNG%2F111.png](https://www.boostcourse.org/viewer/image?src=https%3A%2F%2Fcphinf.pstatic.net%2Fmooc%2F20180925_192%2F15378194530768HSiV_PNG%2F111.png)

    하지만 상/하 padding/border는 line-box에는 영향을 주지 못하기 때문에 위와 같이 부모 요소의 박스에 반영되지 않습니다.

    **parent는 `<div>`, child는 `<span>`**

    [https://www.boostcourse.org/viewer/image?src=https%3A%2F%2Fcphinf.pstatic.net%2Fmooc%2F20180925_34%2F1537819494133zgf3i_PNG%2F1111.png](https://www.boostcourse.org/viewer/image?src=https%3A%2F%2Fcphinf.pstatic.net%2Fmooc%2F20180925_34%2F1537819494133zgf3i_PNG%2F1111.png)

    또한 인접한 다른 line-box에도 반영되지 않습니다.
    즉, 콘텐츠가 겹칠수 있기 때문에 실무에서는 잘 사용하지 않습니다.

    ---

    ### 실습 코드

    ```html
    <!DOCTYPE html>
    <html lang="ko">
    	<head>
    		<meta charset="UTF-8">
    		<title>display</title>
    		<style>
    			.inline {
    				width: 100px; /* box model의 값 변화없이 auto auto */
    				height: 100px; /* box model의 값 변화없이 auto auto */
    				margin: 10px; /* 화면에서 좌, 우만 margin 영역이 확인되나 box model에는 상하좌우 다 선언된 것처럼 보임 */
    				padding: 10px; /* 배경 영역이 커진 것을 확인 가능하고 box model에 상하좌우 다 선언된 것처럼 보임 */
    				border: 10px solid red; /* box model에 상하좌우 다 선언된 것처럼 보임 */
    				background: pink;
    			}

    			.block {
    				width: 100px;
    				height: 100px;
    				margin: 10px;
    				padding: 10px;
    				border: 10px solid blue;
    				background: skyblue;
    			}

    			.inlineblock {
    				width: 100px;
    				height: 100px;
    				margin: 10px;
    				padding: 10px;
    				border: 10px solid green;
    				background: mediumspringgreen;
    			}
    		</style>
    	</head>
    	<body>
    		<div>
    			<div style="display: none;">box</div>
    		</div>
    		<div>
    			<div style="display: inline;" class="inline">box</div>
    		</div>
    		<div>
    			<div style="display: block;" class="block">box</div>
    		</div>
    		<div>
    			<div style="display: inline-block;" class="inlineblock">box</div>
    		</div>
    	</body>
    </html>
    ```

    ```html
    <!DOCTYPE html>
    <html lang="ko">
    	<head>
    		<meta charset="UTF-8">
    		<title>display</title>
    		<style>
    			body > div {
    				padding: 5px;
    				border: 1px dashed #aaa;
    			}

    			.box {
    				padding: 15px;
    				border: 1px solid #aaa;
    				background-color: #eee;
    			}

    			.none .box {
    				display: none;
    			}

    			.inline .box {
    				display: inline;
    			}

    			.block .box {
    				display: block;
    			}

    			.inline-block .box {
    				display: inline-block;
    			}

    			.list-item .box {
    				display: list-item;
    			}
    		</style>
    	</head>
    	<body>
    		<h1>display</h1>
    		<h2>none</h2>
    		<div class="none">
    			<div class="box">box1</div>
    			<div class="box">box2</div>
    			<div class="box">box3</div>
    		</div>
    		<h2>inline</h2>
    		<div class="inline">
    			<div class="box">box1</div>
    			<div class="box">box2</div>
    			<div class="box">box3</div>
    			<div class="box">box4</div>
    			<div class="box">box5</div>
    			<div class="box">box6</div>
    			<div class="box">box7</div>
    			<div class="box">box8</div>
    			<div class="box">box9</div>
    			<div class="box">box10</div>
    		</div>
    		<h2>block</h2>
    		<div class="block">
    			<div class="box">box1</div>
    			<div class="box">box2</div>
    			<div class="box">box3</div>
    		</div>
    		<h2>inline-block</h2>
    		<div class="inline-block">
    			<div class="box">box1</div>
    			<div class="box">box2</div>
    			<div class="box">box3</div>
    		</div>
    		<h2>list-item</h2>
    		<div class="list-item">
    			<div class="box">box1</div>
    			<div class="box">box2</div>
    			<div class="box">box3</div>
    		</div>
    	</body>
    </html>
    ```

    ---

    ### 참고자료

    [display](https://developer.mozilla.org/en-US/docs/Web/CSS/display)

    [CSS display property](https://www.w3schools.com/cssref/pr_class_display.asp)

    [CSS Layout - The display Property](https://www.w3schools.com/css/css_display_visibility.asp)