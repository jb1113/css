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