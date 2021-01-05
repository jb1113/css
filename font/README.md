# 폰트, 텍스트

- typography

    HTML이 처음 등장했을 때는 이미지를 표현하는 기능도 없는 문자만 존재하는 미디어였습니다.
    그러므로 HTML에서 서체와 관련된 부분은 가장 밀접한 분야이면서 동시에 속성의 빈도수도 가장 많습니다.
    폰트 속성, 텍스트 속성, 간견 관련 속성 등 다양한 서체 관련 속성이 있습니다.
    그러므로 폰트의 기본이 되는 타이포그래피의 구조에 대해 알아보겠습니다.

    ### 타이포그래피의 구조

    [https://www.boostcourse.org/viewer/image?src=https%3A%2F%2Fcphinf.pstatic.net%2Fmooc%2F20180930_2%2F1538299310812y3Shi_PNG%2F11123.png](https://www.boostcourse.org/viewer/image?src=https%3A%2F%2Fcphinf.pstatic.net%2Fmooc%2F20180930_2%2F1538299310812y3Shi_PNG%2F11123.png)

    폰트를 이해하기 위해서는 타이포그래피의구조를 먼저 이해해야 합니다.
    모든 폰트는 em 박스를 가지고 있고 위 그림과 같은 구조로 이루어져 있습니다.

    - em : 폰트의 전체 높이를 의미합니다.
    - ex (x-height) : 해당 폰트의 영문 소문자 x의 높이를 의미합니다.
    - Baseline : 영문 소문자 x를 기준으로 하단의 라인을 의미합니다.
    - Ascender : 영문 소문자 x의 상단 라인 위로 넘어가는 영역을 의미합니다. (예를 들면 b, d, h, l 등)
    - Descender : 소문자에서 Baseline 아래로 쳐지는 영역을 의미합니다. 서체에 따라 Descender의 길이가 다릅니다. (예를 들면 g, j, p, q, y 등)

    타이포그래피 구조에는 위의 5가지 외에도 세부적으로 다양한 용어가 존재합니다.

    ---

    ### 참고자료

    [Typography - CSS Reference](https://cssreference.io/typography/)

    [What Is Typography? A Deep Dive Into All Terms And Rules](https://www.shillingtoneducation.com/blog/what-is-typography/)

- font-family

    글꼴을 지정하는 속성입니다.
    font-family는 상속되기 때문에 기본적으로 대표 폰트를 선언하고, 특정 폰트가 필요한 부분에서 재정의해서 사용합니다.

    ```css
    font-family: family-name|generic-family(|initial|inheric);
    ```

    - family-name : 사용할 폰트의 이름을 나타내며 `,`로 구분하여 여러 개 선언할 수 있습니다. 먼저 선언된 순서대로 우선순위가 결정됩니다. 이름 중간에 공백이 있거나, 한글일 경우 홑따옴표(')로 묶어서 선언합니다.
    - generic-family : family-name으로 지정된 글꼴을 사용할 수 없을 경우를 대비해, 브라우저가 대체할 수 있는 폰트가 필요한 경우 선택할 수 있게 해줍니다.
    font-family 속성의 맨 마지막에 선언해야 하며, 키워드이기 때문에 따옴표 등의 인용부호로 묶지 않는 것이 원칙입니다.

    예를 들면 아래와 같이 선언하여 사용할 수 있습니다.

    ```css
    /* 맨 마지막 선언은 generic-family */
    font-family: Helvetica, Dotum, '돋움', Apple SD Gothic Neo, sans-serif;
    ```

    가장 먼저 Helvetica를 사용하고 이를 사용할 수 없을때 Dotum을 사용하는 방식으로 우선순위에 따라 차례대로 적용 됩니다.
    만약 "abc 가나다 123" 이라는 글자가 있다면 "abc"와 "123"은 Helvetica로 표현되고, "가나다"는 Dotum으로 표현됩니다.
    "가나다"가 Dotum으로 표현된 이유는 Helvetica는 한글을 지원하지 않기 때문입니다.

    추가로 돋움체를 영문으로 한번, 한글로 한번 선언하였는데 이는 한글을 지원하지 않는 디바이스일 경우 해당 한글 폰트를 불러올 수 없으므로 영문명으로도 선언해주어야 하기 때문입니다.

    **마지막에는 반드시 generic-family를 선언해 주어야 합니다.**
    그 이유는 선언된 모든 서체를 사용할 수 있다는 보장이 없기 때문입니다.
    이때 generic-family를 선언해주면, 시스템 폰트 내에서 사용자가 의도한 스타일과 유사한 서체로 적용되기 때문입니다.
    또한, 자식 요소에서 font-family를 재선언하면 부모에 generic-family가 이미 선언되어 있더라도 재선언 해주어야 합니다.

    Generic-Family에는 대표적인 서체로 seif, sans-serif가 있습니다.
    serif는 삐침이라는 뜻이고, sans는 프랑스어로 '~이 없이'라는 의미가 있습니다.
    serif는 글자 획에 삐침이 있는 폰트로 대표적으로 명조체가 있으며, sans-serif는 획에 삐침이 없는 폰트로 대표적으로 돋움체가 있습니다.

    ---

    ### 심화

    디바이스마다 지원하는 폰트의 종류가 다르고, 같은 폰트여도 폰트명이 다를 수 있습니다. 디바이스별 대표 폰트들과 지원 범위를 확인하여야 합니다.

    ---

    ### 참고자료

    [font-family](https://developer.mozilla.org/ko/docs/Web/CSS/font-family)

    [CSS font-family property](https://www.w3schools.com/cssref/pr_font_font-family.asp)

    [CSS Fonts](https://www.w3schools.com/css/css_font.asp)

- line-height

    장문의 글에서는 가독성을 위해서 글 사이의 간격을 띄우기도 합니다.
    이를 행간을 조정한다고 하는데요.
    line-height 속성을 이용해 이 행간을 조정할 수 있습니다.
    정확하게는 line-height는 줄의 높이를 의미하는 것이고, 이를 이용해서 행간을 조정할 수 있는 것입니다.

    [https://www.boostcourse.org/viewer/image?src=https%3A%2F%2Fcphinf.pstatic.net%2Fmooc%2F20180925_292%2F1537812871995OXjoa_PNG%2F1234.png](https://www.boostcourse.org/viewer/image?src=https%3A%2F%2Fcphinf.pstatic.net%2Fmooc%2F20180925_292%2F1537812871995OXjoa_PNG%2F1234.png)

    행간을 제어할 때 사용하는 속성이라해서 줄 간격으로 생각해 오해할 수 있습니다.
    줄 바꿈이 되었을 때 윗 줄의 텍스트 하단과 아랫줄의 텍스트 상단까지의 간격이라고 생각할 수도 있지만, line-height 속성으로 제어되는 부분을 line-box라고도 하며 이는 타이포그래피 구조에서 배웠던 [em 박스] + [상, 하단의 여백]까지를 의미합니다.

    ### line-height 속성 (default=normal)

    line-height는 텍스트 라인의 높이를 의미하는 것으로 주로 행간을 제어할 때 사용합니다.

    ```css
    line-height: normal|number|length|initial|inherit;
    ```

    - normal : 기본값으로 브라우저의 기본 속성을 따릅니다. 폰트에 따라 브라우저에 따라 다르지만 보통 1.2 정도로 할당되어 있습니다.
    - number : font-size를 기준으로 설정한 숫자만큼 배율로 적용합니다.
    - length : px, em 등 고정 수치로 할당할 수 있습니다.
    - % : font-size를 기준으로 설정한 퍼센트만큼 배율로 적용합니다.

    ### number, %의 차이점

    주의해야 할 것은 line-height의 값으로 number를 선언할 때와 %를 선언할 때의 차이점입니다.
    두 값 모두 font-size를 기준으로 동작하기 때문에 1이나 100%를 같은 것이라고 생각하고 오해할 수 있습니다. 하지만 두 값은 큰 차이가 있습니다.
    바로 line-height의 값이 자식 요소로 상속되었을 때의 계산 방식입니다.

    - number : 부모 요소의 숫자 값이 그대로 상속됩니다. 즉, 자식 요소에서도 또 한 번 자식 요소의 font-size를 기준으로 계산된 값을 가집니다.
    - % : 부모 요소에서 % 값이 그대로 상속되는 것이 아니고, %에 의해 이미 계산된 px 값이 상속됩니다.

    ```css
    body { font-size: 20px; line-height: 2; } /* line-height = 40px; */
    body { font-size: 20px; line-height: 200%; } /* line-height = 40px; */
    ```

    두 경우 모두 `<body>`에 똑같이 line-height: 40px이 적용됩니다.
    하지만 자식 요소로 `<p>`가 있을 경우에는 달라집니다.

    ```css
    body { font-size: 20px; line-height: 2; } /* line-height = 40px; */
    p { font-size: 10px; } /* line-height: 20px; */

    body { font-size: 20px; line-height: 200%; } /* line-height = 40px; */
    p { font-size: 10px; } /* line-height: 40px; */
    ```

    이처럼 number의 경우 계산된 값이 아닌 숫자 값을 상속한다는 사실 때문에 숫자 값을 사용하면 부모 엘리먼트에서 계산된 값 대신 비율을 그대로 상속받을수 있으므로, 가능하면 단위가 없는 값을 사용하는 것이 좋습니다.

    ---

    ### 심화

    [visual formatting model](https://developer.mozilla.org/en-US/docs/Web/CSS/Visual_formatting_model)은 document를 처리하고, 시각적으로 표시하는 CSS의 기본 개념입니다.
    line-box가 어떤 식으로 생성되고 요소의 특성에 따라 어떻게 다른지를 잘 알고 있다면, line-height를 이해하는데 뿐만아니라 다른 속성들을 이해하는데도 많은 도움이 됩니다.

    ---

    ### 실습 코드

    ```html
    <!DOCTYPE html>
    <html lang="ko">
    	<head>
    		<meta charset="UTF-8">
    		<title>line-height</title>
    		<style>
    			.parent {
    				width: 200px;
    				font-size: 10px;

    				/* line-height: normal; */
    				/* line-height: 20px; */
    				line-height: 2;
    				/* line-height: 200% */
    			}

    			.child {
    				font-size: 20px;
    			}
    		</style>
    	</head>
    	<body>
    		<div class="parent">
    			<div class="child">
    				Lorem ipsum dolor sit amet consectetur adipisicing elit.
    				Ipsam aspernatur vitae sapiente laudantium velit quo unde cupiditate autem, 
    				harum eaque natus perferendis ducimus saepe libero, voluptatibus voluptates possimus.
    				Adipisci, delectus.
    			</div>
    		</div>
    	</body>
    </html>
    ```

    ---

    ### 참고자료

    [line-height](https://developer.mozilla.org/en-US/docs/Web/CSS/line-height)

    [CSS line-height property](https://www.w3schools.com/cssref/pr_dim_line-height.asp)

    [CSS에 대한 깊은 이해: 폰트 매트릭스, line-height와 vertical-align | WIT블로그](https://wit.nts-corp.com/2017/09/25/4903)

- font-size

    글꼴의 크기를 지정하는 속성입니다.
    텍스트를 많이 사용하는 HTML 문서에서 font-size 속성은 가독성이나 명확한 구문을 표현하기 위해서 반드시 필요한 속성입니다.
    글꼴의 크기를 지정하는 font-size 속성에는 다양한 값들이 있습니다.

    ### font-size 속성 (default=medium)

    ```css
    font-size: keyword|length|initial|inherit;
    ```

    - keyword : medium(기본값), xx-small, x-small, small, large, x-large, xx-large, smaller, larger가 있으며 브라우저마다 사이즈가 다릅니다.
    - length : px, em 등 고정 수치로 지정할 수 있습니다.
    - % : 부모 요소의 font-size 기준의 퍼센트로 지정합니다.

    다르게 분류할 경우 아래와 같습니다.

    ```css
    /* <absolute-size> values - 브라우저마다 사이즈가 다르게 정의되어 있으며, 부모 상속 없음 */
    font-size: xx-small;
    font-size: x-small;
    font-size: small;
    font-size: medium; /* 기본 사이즈 */
    font-size: large;
    font-size: x-large;
    font-size: xx-large;

    /* <relative-size> values */
    font-size: smaller; /* 부모 사이즈의 약 0.8배 */
    font-size: larger; /* 부모 사이즈의 약 1.2배 */

    /* <length> values */
    font-size: 16px;
    font-size: 0.8em;
    font-size: 1.2rem;

    /* <percentage> values */
    font-size: 80%;

    /* <viewport-units> values */
    font-size: 1vw; /* 1% of viewport width */
    font-size: 1vh; /* 1% of viewport height */

    /* global values */
    font-size: initial; /* 태그가 갖고 있는 고유 폰트 크기 속성 */
    font-size: inherit; /* 부모 상속을 받을 수 있는 폰트 크기 속성 */
    ```

    - absolute size (keyword) : 기본 값인 medium에 대한 상대적인 크기로 브라우저마다 사이즈가 다르게 정의되어 있습니다.
    - relative size (keyword) : 부모 요소의 font-size 크기에 대해 상대적입니다. smaller는 0.8배, larger는 1.2배 입니다.
    - length (px, em, rem) : 단위를 이용하여 고정된 크기를 지정할 수 있습니다.
    em : 부모 요소의 font-size에 em 값을 곱한 크기
    rem : root의 font-size에 rem 값을 곱한 크기
    - percent (%) : 부모 요소의 font-size를 기준으로 백분율 계산된 값을 지정할 수 있습니다.
    - viewport units (vw, vh) : 뷰포트를 기준으로 하여, 유동적인 font-size를 지정할 수 있습니다.
    vw : 뷰포트 width의 1%
    vh : 뷰포트 heigh의 1%

    브라우저에서 **font-size의 기본값을 미지정한 경우 font-size의 기본 크기는 16px**을 의미합니다. (= 1em)

    ---

    ### 심화

    font-size에는 em 단위와 % 단위를 사용할 수 있습니다. 둘 다 부모 요소의 font-size를 기준으로 그 값이 곱해지기 때문에 font-size 속성에서는 두 단위의 동작이 같아 보일수 있습니다. 그러나 다른 속성에서 이 단위들이 사용될 때는 그 기준이 명확하게 달라지기 때문에 이 차이에 대해 유념해야 합니다.

    ---

    ### 실습 코드

    ```html
    <!DOCTYPE html>
    <html lang="ko">
    	<head>
    		<meta charset="UTF-8">
    		<title>font-size</title>
    		<style>
    			.parent {
    				font-size: 20px;
    			}

    			.child {
    				font-size: 1em;
    			}
    		</style>
    	</head>
    	<body>
    		<div class="parent">
    			<div class="child">
    				Lorem ipsum dolor sit amet consectetur adipisicing elit.
    				Ipsam aspernatur vitae sapiente laudantium velit quo unde cupiditate autem, 
    				harum eaque natus perferendis ducimus saepe libero, voluptatibus voluptates possimus.
    				Adipisci, delectus.
    			</div>
    		</div>
    	</body>
    </html>
    ```

    ---

    ### 참고자료

    [font-size](https://developer.mozilla.org/en-US/docs/Web/CSS/font-size)

    [CSS font-size property](https://www.w3schools.com/cssref/pr_font_font-size.asp)

- font-weight

    글꼴의 굵기를 지정하는 속성입니다.
    시멘틱 태그 중 heading(h1~h1), strong 태그들을 사용했을때 글씨가 굵게 표현되는 것을 확인 했었는데요.
    분명히 아무런 스타일도 입히지 않았는데 왜 이렇게 표현 되었던 걸까요?
    우리는 흔히 글을 쓸 때 중요한 부분이나 강조하고 싶을 때 폰트를 굵게 표시하곤 합니다.
    브라우저도 위의 태그들이 시멘틱하게, 중요하다고 판단되어 굵게 표시하기 위해 font-weight 속성을 이용하여 굵게 표현했다고 생각하면 됩니다.
    이때 font-weight라는 속성에 의해서 위와 같이 표현되었던 것입니다.
    앞서 사용했던 태그들이 font-weight에 의해 굵게 표현되는 속성을 기본값으로 가지고 있기 때문입니다.

    ### font-weight 속성 (default=normal)

    ```css
    font-weight: normal|bold|bolder|lighter|number|initial|inherit;
    ```

    - normal : 기본값 (400)
    - bold : 굵게 표현 (700)
    - bolder : 부모 요소보다 두껍게 표현
    - lighter : 부모 요소보다 얇게 표현
    - number : 굵기의 수치, 100~900까지 있으며 100단위로 값을 지정 (클수록 더 두껍게 표현)

    수치를 이용한 font-weight는 폰트 자체에서 지원을 해야 표현할 수 있습니다.
    폰트에 따라서 font-weight를 적용해도 굵기에 변화가 없을 수도 있으며, **normal과 bold만 지원하는 폰트일 경우**에는 **100~500까지는 normal, 600~900까지는 bold**로 표현됩니다.

    폰트가 점차 다양해지면서 굵기 자체를 폰트 family-name으로 가지고 있는 경우도 있습니다.
    또한, 디바이스 별로 조금 다르게 표현될 수도 있습니다.

    실무에서는 normal과 bold를 많이 사용하고, 부모 요소에 영향이 있는 bolder와 lighter의 사용은 되도록 지양하는 편입니다.
    물론, 상속 관계에 의해서 바뀌어야 하는 경우라면 당연히 유용하게 사용할 수 있지만 그 외의 경우에는 사용에 있어 신중해야 합니다.

    font-weight와 font-family, font-size는 서로 밀접하게 연관되어 있습니다.

    ```css
    font-weight: normal; /* 400과 같음 */
    font-weight: bold; /* 700과 같음 */
    font-wieght: lighter; /* 부모 요소보다 얇은 폰트 가중치 */
    font-weight: bolder; /* 부모 요소보다 굵은 폰트 가중치 */

    font-weight: 100; /* Thin (Hairline) */
    font-weight: 200; /* Extra Light (Ultra Light) */
    font-weight: 300; /* Light */
    font-weight: 400; /* Normal */
    font-weight: 500; /* Medium */
    font-weight: 600; /* Semi Bold (Demi Bold) */
    font-weight: 700; /* Bold */
    font-weight: 800; /* Extra Bold (Ultra Bold) */
    font-weight: 900; /* Black (Heavy) */
    ```

    ---

    ### 실습 코드

    ```html
    <!DOCTYPE html>
    <html lang="ko">
    	<head>
    		<meta charset="UTF-8">
    		<title>font-weight</title>
    		<link href='//fonts.googleapis.com/css?family=Open+Sans:400,600,700,800,300' rel='stylesheet' type='text/css'>
    		<style>
    			body {
    				padding: 0 20px;
    				font-family: 'Open Sans';
    			}
    			.w100 { font-weight: 100; }
    			.w200 { font-weight: 200; }
    			.w300 { font-weight: 300; }
    			.w400 { font-weight: 400; }
    			.w500 { font-weight: 500; }
    			.w600 { font-weight: 600; }
    			.w700 { font-weight: 700; }
    			.w800 { font-weight: 800; }
    			.w900 { font-weight: 900; }
    		</style>
    	</head>
    	<body>
    		<p class="w100">This is 100 font-weight</p>
    		<p class="w200">This is 200 font-weight</p>
    		<p class="w300">This is 300 font-weight</p>
    		<p class="w400">This is 400 font-weight</p>
    		<p class="w500">This is 500 font-weight</p>
    		<p class="w600">This is 600 font-weight</p>
    		<p class="w700">This is 700 font-weight</p>
    		<p class="w800">This is 800 font-weight</p>
    		<p class="w900">This is 900 font-weight</p>
    	</body>
    </html>
    ```

    ---

    ### 참고자료

    [font-weight](https://developer.mozilla.org/ko/docs/Web/CSS/font-weight)

    [CSS font-weight property](https://www.w3schools.com/cssref/pr_font_weight.asp)

    [Font weight with numeric values](https://codepen.io/impressivewebs/pen/EIncg)

- font-style

    글꼴의 스타일을 지정하는 속성입니다.
    em 태그를 사용했을때, 글꼴이 기울어지는 것을 확인 했었습니다.
    em 태그는 기본적으로 font-style 속성에 italic이라는 값을 가지고 있어 기울임꼴로 표시됩니다.
    이처럼 font-style 속성을 이용하면 글꼴의 기울임 처리를 할 수도 있습니다.
    순서대로 normal, italic, oblique 스타일이 적용된 텍스트 입니다.

    [https://www.boostcourse.org/viewer/image?src=https%3A%2F%2Fcphinf.pstatic.net%2Fmooc%2F20180925_282%2F1537815184289axaTi_PNG%2F12345.png](https://www.boostcourse.org/viewer/image?src=https%3A%2F%2Fcphinf.pstatic.net%2Fmooc%2F20180925_282%2F1537815184289axaTi_PNG%2F12345.png)

    ### font-style 속성 (default=normal)

    ```css
    font-style: normal|italic|oblique|initial|inherit;
    ```

    - normal : font-family 내에 분류된 기본 값
    - italic : italic 스타일로 표현합니다.
    - oblique : oblique 스타일로 표현합니다. (텍스트의 기울기에 대한 각도를 추가로 지정할 수 있습니다.)

    ---

    ### 심화

    대부분 브라우저에서 italic 스타일과 oblique 스타일을 똑같은 형태로 표현하고 있습니다.
    oblique 뒤에 오는 angle의 유효한 값은 -90 ~ 90도이며, 따로 각도를 지정하지 않으면 기본 14도가 사용됩니다.
    양수 값은 글의 끝 부분 쪽으로 기울어지며, 음수 값은 시작 부분 쪽으로 기울어집니다.

    ```css
    /* font-style: oblique <angle> */
    font-style: oblique 45deg;
    ```

    그러나, 아직 초안 단계로 [CSS Fonts Module Level](https://drafts.csswg.org/css-fonts-4/#font-style-prop) 4를 지원하는 브라우저에서만 사용 가능합니다.

    ---

    ### 참고자료

    [font-style](https://developer.mozilla.org/en-US/docs/Web/CSS/font-style)

    [CSS font-style property](https://www.w3schools.com/cssref/pr_font_font-style.asp)

- font-variant

    글꼴의 형태를 변형하는 속성으로 소문자를 작은 대문자로 변환합니다.

    ### font-variant 속성 (default=normal)

    ```css
    font-variant: normal|small-caps|initial|inherit;
    ```

    - normal : 기본값
    - small-caps : 소문자를 작은 대문자로 변환합니다.

    ---

    ### 실습 코드

    ```html
    <!DOCTYPE html>
    <html lang="ko">
    	<head>
    		<meta charset="UTF-8">
    		<title>font-variant</title>
    		<style>
    			p {
    				font-variant: small-caps;
    			}
    		</style>
    	</head>
    	<body>
    		<p>Font-Variant: Small-Caps</p>
    	</body>
    </html>
    ```

    ---

    ### 참고자료

    [font-variant](https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant)

    [CSS font-variant property](https://www.w3schools.com/cssref/pr_font_font-variant.asp)