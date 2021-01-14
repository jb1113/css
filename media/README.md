# 미디어쿼리

- 미디어쿼리

    웹이 급격하게 발전하면서 다양한 미디어 기기들이 웹을 지원하고 있습니다.
    그에 맞춰 대부분의 웹 사이트들이 반응형으로 제작되고 있습니다.
    미디어 쿼리는 반응형 웹 사이트 제작에 반드시 필요한 기술입니다.

    ### 미디어쿼리 소개

    미디어 쿼리(Media Queries)는 각 미디어 매체에 따라 다른 스타일(css style)을 적용할 수 있게 만드는 것입니다.
    미디어 매체는 모니터와 같은 스크린 매체, 프린트, 스크린 리더기와 같은 것들을 이야기 합니다.
    미디어쿼리는 동일한 웹 페이지를 다양한 환경의 사용자들에게 최적화된 경험을 제공할 수 있게 해줍니다.

    미디어쿼리는 CSS2의 미디어 타입(Media Types)을 확장해서 만들어졌습니다.
    미디어타입은 이론적으로는 훌륭했지만, 결과적으로 제대로 활용되지 못했습니다.
    이유는 당시에는 미디어 타입을 제대로 지원하는 기기가 없었기 때문입니다.

    미디어 쿼리가 등장하기 이전에는 제대로 된 반응형 웹 사이트를 제작할 수는 없었습니다.
    하지만 당시에는 사용자들의 환경이 아주 제한적이었기 때문에 제작자 입장에서는 대중적인 미디어 범위에서만 잘 보이도록 사이트를 제작하면 반응형이 아니더라도 충분했습니다.

    하지만 웹이 급격히 발전하면서 대응해야 하는 미디어의 폭이 상당히 늘어났습니다.
    이런 필요성에 따라 W3C는 CSS2의 미디어 타입을 확장하며, CSS3 미디어쿼리를 발표합니다.
    이 미디어 쿼리로 인해 웹 사이트를 제작함에 있어 이전의 정적인 고정 레이아웃 웹 사이트에서 동적으로 반응하는 반응형 웹 사이트로 패러다임이 새롭게 변화하였습니다.

    ---

    ### 참고자료

    [Media types](https://www.w3.org/TR/1998/WD-css2-19980128/media.html)

    [Media Queries](https://www.w3.org/TR/css3-mediaqueries/)

- 미디어 타입 & 미디어 특성

    ### @media(at media)

    미디어 쿼리는 CSS2 Media Types을 확장했기 때문에 선언 방법은 동일합니다.

    ```css
    @media mediaqueries { /* style rules */ }
    ```

    @media로 시작하며, 이 키워드는 이제부터 미디어 쿼리를 시작한다 라는 뜻입니다.
    그 뒤에 미디어 쿼리 구문(위 코드의 mediaqueries)이 나오고 이어서 중괄호({ })를 이용해서 스타일 규칙이 들어갑니다.
    미디어 쿼리 구문은 논리적으로 평가되며 참이면 뒤에 나오는 스타일 규칙이 적용되고, 거짓이면 무시됩니다.
    미디어 쿼리 구문은 미디어 타입(Media types)과 미디어 특성(Media Features)으로 이루어져 있습니다.

    ### 미디어 타입

    - **all**, braille, embossed, handheld, **print**, projection, **screen**, speech, tty, tv

    우리가 알아야 할 타입은 all, print, screen 정도입니다. 그 중에서도 screen이 거의 대부분입니다.
    화면을 출력하는 디스플레이가 있는 미디어들은 전부 screen에 속하기 때문에 현실적으로 고려해야하는 미디어들은 전부 여기에 해당이 됩니다.
    print 타입도 간혹 사용이 됩니다.
    all 타입은 모든 미디어에 적용되는 타입입니다. 미디어를 구분하는 용도가 아니기 때문에 유용하게 사용되지는 않습니다.

    ### 미디어 특성

    - **width**, height, device-width, device-height, **orientation**, aspect-ratio, device-aspect-ratio, color, color-index, monochrome, resolution, scan, grid

    미디어 특성 역시 우리가 알아야 할 특성은 width와 orientation 정도입니다.
    width는 뷰포트의 너비, 즉 브라우저 창의 너비를 말합니다. (스크린의 크기 X)
    orientation은 미디어가 세로모드인지 가로모드인지를 구분합니다.
    미디어 쿼리에서는 이 구분을 width와 height 특성의 값을 비교해서 height가 width보다 같거나 크면 세로모드, 반대인 경우에는 가로모드라고 해석합니다.
    세로모드에서는 portrait, 가로모드에서는 landscape 키워드와 매칭이 됩니다.

    ### 미디어 쿼리 level 4

    지금 설명하는 미디어 타입과 미디어 특성은 CSS3 미디어 쿼리 표준 명세를 기준으로 작성되었습니다.
    현재, 미디어 쿼리 level 4가 CR(유력 후보안) 단계입니다.
    해당 문서에서 미디어 타입 대부분과 미디어 특성 중 일부 속성이 폐기 예정입니다.

    ---

    ### 참고자료

    [Media Queries](https://www.w3.org/TR/css3-mediaqueries/#media1)

    [](https://www.w3.org/TR/mediaqueries-4/#media-types)

    [](https://www.w3.org/TR/mediaqueries-4/#mf-deprecated)

- Syntax

    ### 미디어 쿼리 Syntax

    ```css
    media_query_list
     : S* [media_query [ ',' S* media_query ]* ]?
     ;
    media_query
     : [ONLY | NOT]? S* media_type S* [ AND S* expression ]*
     | expression [ AND S* expression ]*
     ;
    expression
     : '(' S* media_feature S* [ ':' S* expr ]? ')' S*
     ;
    ```

    위 코드는 CSS3 미디어 쿼리 표준 명세에 나와있는 Syntax 부분입니다.
    참고로 Syntax는 전부 이해할 필요는 없지만 일부 기호는 알아두면 좋습니다.

    - [ a ] : a가 나올수도 있고 나오지 않을 수도 있습니다.
    - a | b : a 또는 b 둘 중 하나를 선택합니다.
    "|"는 파이프 라인 기호입니다.
    - a ? : a가 0번 나오거나 1번만 나올 수 있음
    - a * : a가 0번 나오거나 그 이상 계속 나올 수 있음
    - media_type : all, screen, print 등 명세에 정의된 미디어 타입
    - media_feature : width, orientation 등 명세에 정의된 미디어 특성

    위 Syntax를 요약하면

    **media_query_list** :
    여러개의 미디어 쿼리로 이루어진 리스트로 작성 가능하며, 쉼표를 이용해서 구분합니다.

    **media_query** :

    **A 형태**
    미디어 타입에 AND 키워드를 이용해서 미디어 표현식을 붙일 수 있습니다.
    미디어 타입 앞에는 only 또는 not 키워드가 올 수 있습니다.
    미디어 표현식은 생략 가능하기 때문에 미디어 타입 단독으로 사용될 수 있습니다.

    **B 형태**
    미디어 타입 없이 미디어 표현식이 바로 나올 수 있습니다.
    (미디어 타입이 명시되지 않으면 all로 간주합니다.)
    미디어 표현식은 AND 키워드를 이용해서 계속해서 나올 수 있습니다.

    **expression** :

    미디어 표현식은 괄호로 감싸야 하며, 특성 이름과 해당하는 값으로 이루어집니다.
    이름과 값은 : 기호로 연결합니다.
    또, 값 없이 특성 이름만으로도 작성할 수 있습니다.

    ### min-/max- 접두사

    미디어 특성은 이름 앞에 min- 또는 max- 접두사를 붙일 수 있습니다.
    실제로 반응형 사이트를 제작할 때는 보통 접두사를 붙여서 사용합니다.
    접두사를 붙이지 않고 사용하는 경우 대부분 효율적이지 못하기 때문입니다.
    예를 들어, 대부분의 반응형 사이트는 width 특성을 이용하는데, 접두사 없이 width: 00px 이라고 하게 선언하면 정확히 뷰포트의 크기가 00px 에서만 적용되기 때문에, 다양한 기기들을 대응하기 힘듭니다.
    그래서 접두사를 사용하여 범위를 지정하게 되면 훨씬 간결하게 반응형 사이트를 제작할 수 있습니다.

    ### 예제 코드

    위에서 정의한 Syntax를 따라 유효한 미디어 쿼리 예제 코드를 살펴보고 어떻게 해석이 되는지 확인합니다.

    **@media screen { ... }**
    : 미디어 타입이 screen이면 적용됩니다.

    **@media screen and (min-width: 768px) { ... }**
    : 미디어 타입이 screen이고 width가 768px 이상이면 적용됩니다.
    두 개 중 하나라도 만족하지 않으면 거짓이 됩니다.

    **@media (min-width: 768px) and (max-width: 1024px) { ... }**
    : and는 연결된 모든 표현식이 참이면 적용됩니다.
    (and 키워드는 연결된 부분이 모두 참이어야 적용이 됩니다.)

    **@media (color-index) { ... }**
    : 미디어 장치가 color-index를 지원하면 적용됩니다.

    **@media screen and (min-width: 768px), screen and (orientation: portrait), ... { ... }**
    : 미디어 쿼리 리스트로 쉼표로 연결된 미디어 쿼리 중 하나라도 참이면 적용됩니다.
    (and 키워드와 반대라고 생각하면 됩니다.)

    **@media not screen and (min-width: 768px)**
    : not 키워드는 하나의 media_query 전체를 부정합니다.
    * (not screen) and (min-width: 768px) → 잘못된 해석
    * not (screen and (min-width: 768px)) → 올바른 해석

    **@media not screen and (min-width: 768px), print**
    : 첫 번째 미디어 쿼리에만 not 키워드가 적용되며, 두 번째 미디어 쿼리(print)에는 영향이 없습니다.

    ### 미디어 쿼리 선언 방법

    미디어 쿼리를 선언하는 3가지 방법에 대해 알아보겠습니다.
    참고로 @media를 이용한 방법을 가장 많이 사용하며 나머지 2가지 방법은 거의 쓰이지 않습니다.

    **@media screen and (color)**
    : CSS 파일 내부에 또는 `<style>` 태그 내부에 사용 가능합니다.
    대부분의 경우 이렇게 사용합니다.

    `**<link rel="stylesheet" media="screen and (color)" href="example.css">**`
    : <link> 태그의 media 속성에 미디어 쿼리를 선언합니다.
    미디어 쿼리가 참이면 뒤에 CSS 파일 규칙이 적용됩니다.

    **@import url(example.css) screen and (color)**
    : CSS 파일 내부에 또는 `<style>` 태그 내부에 사용 가능합니다.
    @import문 뒤에 미디어 쿼리를 선언하면 됩니다.

    ---

    ### 참고자료

    [Media Queries](https://www.w3.org/TR/css3-mediaqueries/#syntax)

- 실습 코드

    **기본 구조**

    ```html
    <!DOCTYPE html>
    <html lang="ko">
    	<head>
    		<meta charset="UTF-8">
    		<title>Media Queries</title>
    		<style>
    			/* media query here */
    		</style>
    	</head>
    	<body>
    		<p>
    			W3C는 <a href="https://www.w3.org/TR/css3-mediaqueries/">CSS3 미디어쿼리 문서</a>를 
    			2012년 6월에 표준 권고안으로 제정하였습니다.
    		</p>
    		<p>
    			또한, 기존의 미디어쿼리 개선 작업을 진행 중이며, 2017년 9월에
    			<a href="https://www.w3.org/TR/mediaqueries-4/">미디어쿼리 레벨4</a>를 발표했습니다. 
    			이 문서는 현재 유력 표준 권고안입니다.
    		</p>
    	</body>
    </html>
    ```

    ### 디스플레이 크기에 따른 body요소의 background-color 변경

    - 0 ~ 767px이면 (mobile) : crimson
    - 768px ~ 1024px이면 (tablet) : darkblue
    - 1025px ~ 이면 (desktop) : teal

    width 미디어 특성을 이용해서 뷰포트 가로 크기에 따라 배경 색상을 변경

    ```css
    @media screen and (max-width: 767px) {
    	body { background-color: crimson; }
    }

    @media screen and (min-width: 768px) and (max-width: 1024px) {
    	body { background-color: darkblue; }
    }

    @media screen and (min-width: 1025px) {
    	body { background-color: teal; }
    }
    ```

    위 코드의 경우, 3개의 조건을 만족하기 위해 3개의 미디어 쿼리를 작성했습니다.
    위 코드도 의도한 대로 정상적으로 잘 동작하지만, 1개의 조건을 기본 body 요소의 배경 색상으로 지정해놓게 된다면 다른 2개의 미디어 쿼리만 이용해도 가능합니다.

    어떤 조건을 기본으로 정할지는 작성하는 사이트가 모바일 사이트인지, 데스크탑 사이트인지를 먼저 구분해야 합니다.

    모바일 중심의 사이트라면(mobile first) 모바일에 해당하는 조건의 배경 색상을 기본으로 선언하면 되고, 데스크탑 중심의 사이트라면(desktop first) 데스크탑에 해당하는 조건의 배경 색상을 기본으로 선언해 놓으면 됩니다.
    만들어진 미디어 쿼리를 수정해서, mobile first인 경우 또 desk first인 경우대로 작성해 봅니다.

    **mobile first**

    ```css
    /* mobile first */
    body { background-color: crimson; }

    @media screen and (min-width: 768px) and (max-width: 1024px) {
    	body { background-color: darkblue; }
    }

    @media screen and (min-width: 1025px) {
    	body { background-color: teal; }
    }
    ```

    **desktop first**

    ```css
    /* desktop first */
    body { background-color: teal; }

    @media screen and (min-width: 768px) and (max-width: 1024px) {
    	body { background-color: darkblue; }
    }

    @media screen and (max-width: 767px) {
    	body { background-color: crimson; }
    }
    ```

    ### 페이지 인쇄하는 경우의 스타일 추가

    - 앵커 요소의 url 출력
    - 앵커 요소의 밑줄 제거

    미디어 타입 print를 이용하면 인쇄될 경우에 적용되는 스타일을 추가할 수 있습니다.

    ```css
    @media print {
    	a:after {
    		display: inline;
    		content: "("attr(href)")";
    	}
    	a { text-decoration: none; }
    }
    ```

    웹 페이지를 인쇄할 경우에는 앵커 요소가 가리키는 url을 문서에 같이 출력해주는게 내용을 이해하는데 훨씬 좋습니다.
    실제 인쇄를 하지 않더라도 브라우저에서 제공하는 인쇄 미리보기 기능을 이용하면 화면으로 확인이 가능합니다.

    ---

    ### 참고자료

    [Media Queries](https://www.w3.org/TR/css3-mediaqueries/)

    [](https://www.w3.org/TR/mediaqueries-4/)

    [Media Queries](https://mediaqueri.es/)