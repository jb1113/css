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