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