# 속성

- 정의와 구문

    CSS의 속성은 그 종류가 매우 다양하고 지속해서 업데이트 되고 있습니다.
    기존의 속성 명이 변경되기도 하고 속성이 스펙아웃 되기도 하며 새로운 속성이 추가되기도 합니다.
    이러한 잦은 변화고 인해 CSS 관련 서적이나 강의를 통해서 모든 속성을 파악하는 데는 어려움이 있습니다.

    CSS Reference를 통해 확인 가능한 사항들은 다음과 같습니다.

    ### 정의

    해당 속성이 어떤 변화를 일으키고 어떻게 동작하는지 파악할 수 있습니다.

    - 기본 값
    - 상속 여부
    - 애니메이션 가능 여부
    - 사용 가능한 CSS 버전

    ### 문법

    해당 속성값을 어떤 식으로 나열하여 사용하는지를 파악할 수 있습니다.

    ### 속성 값

    해당 속성이 인식하여 적용할 수 있는 값의 형태나 키워드 등을 파악할 수 있습니다.

    - Initial : 초기값, 즉 속성의 기본값으로 정의 (IE에서 지원하지 않음)
    - Inherit : 부모 요소의 해당 속성 값을 적용 (상속 가능한 요소일 경우)
    즉, 상속이 불가능한 속성일 경우에는 적용 되지 않습니다.

    ### 지원 범위

    해당 속성이 정의에 맞게 동작 가능한 CSS 버전, 브라우저별 버전을 확인할 수 있습니다.

    - 어떤 브라우저의 어떤 버전이냐에 따라 같은 값이어도 다르게 렌더링 될 수 있으므로,
    현재 프로젝트의 사용자 제공 지원 범위를 잘 확인하고 적용해야 합니다.

    ### 예제

    문법과 속성값을 바탕으로 실제로 속성을 동작하는 예제 코드를 확인할 수 있습니다.

    ### 참고 사항

    해당 속성에 대해 특이사항이나 버그에 대해서 확인할 수 있습니다.

    ---

    ### 참고자료

    [W3C](https://www.w3.org/)

    [W3Schools Online Web Tutorials](https://www.w3schools.com/)

    [MDN Web Docs](https://developer.mozilla.org/ko/)

- 단위

    CSS 속성과 값을 사용할 때 값과 함께 많이 사용되는 것 중의 하나가 단위입니다.
    여러 가지의 단위가 있고 각각의 동작 방식이 다르기에 특징을 제대로 알아야 합니다.

    단위는 크게 절대 길이 단위와 상대 길이 단위로 구분되어 집니다.

    ### 절대 길이

    절대 길이는 고정된 크기 단위로, 다른 요소의 크기에 의해 영향을 받지 않습니다.

    - px (1px = 1/96th of 1 inch)

    절대 길이이므로 다른 요소의 영향을 받지 않아 화면에서 고정된 크기를 가지지만 장치의 해상도에 따라 상대적입니다.
    여러 환경에서 디자인을 같게 표현하고 브라우저 호환성에 유리한 구조로 되어 있어서 디자인 의도가 많이 반영된 웹사이트의 경우 픽셀 단위를 사용하는 것을 권장하고 있습니다.

    - pt (1pt - 1/72 of 1 inch)

    컴퓨터가 없던 시절부터 있던 단위입니다.
    인쇄물이나 워드프로세서 프로그램에서 사용된 가장 작은 표준 인쇄 단위입니다.
    웹 화면에 인쇄용 문서를 위한 스타일을 적용할 때 유용하게 사용할 수 있습니다.
    그러나 사용하는 기기의 해상도에 따라 차이가 있어 W3C에서도 pt는 웹개발 시 권장하는 단위가 아닙니다.
    예를 들면, Windows에서는 9pt = 12px, Mac에서는 9pt = 9px로 보이게 됩니다.

    ### 상대 길이

    상대 길이는 다른 요소의 크기나 폰트 크기, 브라우저(viewport) 등의 크기에 따라 상대적으로 값이 변합니다.

    - %
    부모의 값에 대해서 백분율로 환산한 크기를 갖게 됩니다.
    - em
    font-size를 기준으로 값을 환산합니다. 소수점 3자리까지 표현 가능합니다.
    - rem
    root의 font-size를 기준으로 값을 환산합니다.
    - vw
    viewport의 width 값을 기준으로 1%의 값으로 계산됩니다.

    ---

    ### 실습 코드

    ```html
    div { font-size : 16px; }
    .px { font-size : 16px; }
    .pt { font-size : 12pt; }
    .percent { font-size : 100%; }
    .em { font-size : 1em; }

    ...
    <div>
    	<p class="px">단위 16px로 선언된 텍스트</p>
    	<p class="pt">단위 12pt로 선언된 텍스트</p>
    	<p class="percent">단위 100%로 선언된 텍스트</p>
    	<p class="em">단위 1em로 선언된 텍스트</p>
    </div>
    ```

    ---

    ### 참고자료

    [CSS values and units](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Values_and_units)

    [CSS Units](https://www.w3schools.com/cssref/css_units.asp)

- 색상

    폰트의 색상 값을 적용할 때 사용하는 속성은 color 속성입니다.
    color 속성은 값으로 색상 값을 받습니다.
    색상 값은 다양한 형태로 적용할 수 있으며 값의 형태에 따라 선언하는 방식이 조금 다릅니다.
    색상 값 적용 방식은 색상과 관련된 다른 속성에서도 동일하게 적용됩니다.

    ### color 속성

    폰트의 색상 값을 적용할 때 사용하는 속성입니다.

    ```css
    h1 { color : 색상 값; }
    ```

    ### 색상 값 지정 방식

    - 컬러 키워드
    CSS 자체에서 사용 가능한 문자 식별자 입니다.
    red, blue, black 등과 같이 미리 정의 되어있는 키워드를 이용해 색상을 표현할 수 있습니다. (참고. transparent는 투명을 나타내는 키워드)
    - 16 진법 (#RRGGBB)
    6자리의 16진수(0-9, A-F)는 각각 두 자리씩 세 가지 색상(RGB)을 나타냅니다.
    첫 번째 두 자리는 적색(RR), 가운데 두 자리는 녹색(GG), 마지막 두 자리는 청색(BB)을 의미합니다.
    각 자리의 알파벳은 대소문자를 구분하지 않습니다.
    - 16 진법 (#RGB)
    6자리의 16진수에서 각각의 두 자리가 같은 값을 가지면 3자리로 축약하여 사용할 수 있습니다.
    예를 들어, #AA11CC는 #A1C로 축약하여 사용할 수 있습니다.
    - RGB()
    RGB 값은 rgb(R, G, B)의 형태로 각 변수 값(R 적색, G 녹색, B 청색)의 강도를 정의합니다.
    0 ~ 255의 정수로 된 값을 지정할 수 있으며, 0 → 255는 검정 → 흰색으로 값의 변화를 나타냅니다.
    - RGBA()
    RGBA 값은 기존 RGB에서 A값이 추가된 형태입니다.
    rgb(R, G, B, A)의 형태로 각 변수는 (R 적색, G 녹색, B 청색, A 투명도)의 강도를 정의합니다.
    A 값은 0 ~ 1 사이의 값을 지정할 수 있으며, 0.5와 같이 소수점 표기도 가능합니다.
    0 → 1은 투명 → 불투명으로 값의 변화를 나타냅니다.

    ```css
    body { color: black; } /* color names */
    body { color: #000000; } /* Hexadecimal colors */
    body { color: #000; } /* Hexadecimal colors */
    body { color: rgb(0,0,0); } /* (red, green, blue / 0~255) */
    body { color: rgba(0,0,0,1); } /* (red, green, blue, alpha / 0~255, 0~1) */
    /* As HSL values (CSS3) */
    /* As HWB values (CSS4) */
    ```

    ---

    ### 실습 코드

    ```html
    <style>
    	div { height: 50px; width: 100px; }
    <style>

    <body>
    	<h1>Colors can be set using hexadecimal values</h1>

    	<div style="background-color: #ff0000"></div> <!-- Red -->
    	<div style="background-color: #00ff00"></div> <!-- Green -->
    	<div style="background-color: #0000ff"></div> <!-- Blue -->
    	
    	<h1 style="color: #FF0000">Heading</h1> <!-- Red -->
    	<h1 style="color: #00FF00">Heading</h1> <!-- Green -->
    	<h1 style="color: #0000FF">Heading</h1> <!-- Blue -->
    </body>
    ```

    ```html
    <style>
    	div { height: 50px; width: 100px; }
    <style>

    <body>
    	<h1>Colors can be set using RGB values</h1>

    	<div style="background-color: rgb(255,0,0)"></div> <!-- Red -->
    	<div style="background-color: rgb(0,255,0)"></div> <!-- Green -->
    	<div style="background-color: rgb(0,0,255)"></div> <!-- Blue -->
    	
    	<h1 style="color: rgb(255,0,0)">Heading</h1> <!-- Red -->
    	<h1 style="color: rgb(0,255,0)">Heading</h1> <!-- Green -->
    	<h1 style="color: rgb(0,0,255)">Heading</h1> <!-- Blue -->
    </body>
    ```

    ```html
    <style>
    	div { height: 50px; width: 100px; }
    <style>

    <body>
    	<h1>Colors can be set using RGBA values</h1>

    	<div style="background-color: rgba(255,0,0,0)"></div> <!-- transparent -->
    	<div style="background-color: rgba(255,0,0,0.5)"></div>
    	<div style="background-color: rgba(255,0,0,1)"></div> <!-- opacity -->
    	
    	<h1 style="color: rgba(255,0,0,0)">Heading</h1> <!-- transparent -->
    	<h1 style="color: rgba(255,0,0,0.5)">Heading</h1>
    	<h1 style="color: rgba(255,0,0,1)">Heading</h1> <!-- opacity -->
    </body>
    ```

    ---

    ### 참고자료

    [](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value)

    [CSS Colors](https://www.w3schools.com/css/css3_colors.asp)

- 배경

    background 속성은 요소의 배경에 관련된 속성을 지정할 때 사용합니다.
    배경에 관련된 속성에는 색상, 이미지, 반복 여부 등 여러 속성이 존재하고 이 속성들을 한 번에 모아서 사용할 수도 있습니다.

    ### background 관련 속성

    - background-color (default=transparent) : 배경의 색상을 지정하는 속성입니다.
    앞서 배운 색상 값 적용 방식과 같습니다.
    - background-image (default=none) : 배경으로 사용할 이미지의 경로를 지정하는 속성입니다.
    url의 경로는 절대 경로, 상대 경로 모두 사용 가능합니다.
    만약 background-color에 색상이 적용된 상태에서 background-image로 사용된 이미지에 투명한 부분이 있다면, 그 부분에 background-color 색상이 노출됩니다.
    - background-repeat (default=repeat) : 이미지의 반복 여부와 방향을 지정하는 속성입니다.
    기본값이 repeat이기 때문에 따로 설정하지 않으면 x, y축으로 반복되어서 표시됩니다.
    background-repeat의 값으로 사용할 수 있는 것들은 다음과 같습니다.
    - repeat : x, y 축으로 모두 반복합니다.
    - repeat-x : x 축 방향으로만 반복합니다.
    - repeat-y : y 축 방향으로만 반복합니다.
    - no-repeat : 이미지를 반복하지 않습니다.
    - background-position (default=0%) : 요소에서 배경 이미지의 위치를 지정하는 속성입니다. x축, y축으로부터의 위치를 지정할 수 있으며 값의 선언 순서는 x축, y축으로부터의 간격입니다. 만일 한쪽만 지정된다면 나머지는 중앙 값(center)으로 적용됩니다.
    - % : 기준으로부터 % 만큼 떨어진 지점과 이미지의 % 지점이 일치하는 곳에 위치시킵니다.
    - px : 기준으로부터 px 만큼 떨어진 지점과 이미지의 (0,0) 지점이 일치하는 곳에 위치시킵니다.
    - 키워드 : top, left, right, bottom, center 키워드를 사용할 수 있습니다.
    키워드는 선언 순서와 관계없이 top, bottom은 y축 기준으로 하며 left, right는 x축으르 기준으로 합니다.
    - background-attachment (default=scroll) : 화면 스크롤에 따른 배경 이미지의 움직임 여부를 지정하는 속성입니다.
    - scroll : 배경 이미지는 요소 자체를 기준으로 고정되어 있으며 내용과 함께 스크롤 되지 않습니다.
    - local : 배경 이미지는 요소의 내용을 기준으로 고정되어 있으며 내용과 함께 스크롤 됩니다.
    - fixed : 배경 이미지는 뷰포트를 기준으로 고정되어 있으며 스크롤에 영향을 받지 않습니다.
    (뷰포트 : 사용자가 시각적으로 볼 수 있는 웹페이지 영역을 의미합니다. 컴퓨터나 휴대폰과 같은 장치의 display 요소가 표현되는 영역을 말합니다.)

    ### background 축약

    ```css
    background: [-color][-image][-repeat][-attachment][-position];
    ```

    ---

    ### 참고자료

    [Backgrounds and borders](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Backgrounds_and_borders)

    [CSS Backgrounds](https://www.w3schools.com/css/css_background.asp)