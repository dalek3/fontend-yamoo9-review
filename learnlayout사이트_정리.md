출처:http://ko.learnlayout.com/
#레이아웃
## **margin:auto**
- block 레벨 앨리먼트의 **width를 설정 후 margin 좌우 auto로 설정하면 가로 중앙에 오게 할 수있다.** <br>지정한 너비를 차지하고 나머지 공간은 두 마진에 균등하게 나뉘질 것이다.
    ```css
    ex)
    #main {
        width: 600px;
        margin: 0 auto; 
    }
    ```
- 브라우저 창이 엘리먼트 너비보다 좁을 때 유일하게 문제가 발생합니다.
- 브라우저에서는 페이지에 가로 스크롤바를 만들어 이 문제를 해결합니다.

## **max-width**
- 위 상황을 해결하기 위해선 **width 대신 max-width를 사용**하면 브라우저가 작은 창을 처리하는 방식을 개설할 수 있습니다.<br> 이것은 사이트를 **모바일 환경에서도 사용할 수 있게 만들 때 중요**합니다.
    ```css
    ex)
    #main {
        max-width: 600px;
        margin: 0 auto; 
    }
    ```
## **박스 모델**
* 엘리먼트의 너비를 설정할 경우 해당 엘리먼트는 실제로 여러분이 설정한 것보다 크게 나타날 수 있습니다. 
* 이것은 엘리먼트의 테두리와 패딩이 지정된 너비 이상으로 엘리먼트를 늘리기 때문입니다. 
* 다음 예제를 보시면 너비값을 동일하게 설정했는데도 결과적으로 크기가 다릅니다.
    ```css
    ex)
    .simple {
      width: 500px;
      margin: 20px auto;
    }

    .fancy {
      width: 500px;
      margin: 20px auto;
      padding: 50px;
      border-width: 10px;
    }
    ```
* 오랫동안 이 문제의 해법은 너비값을 조절하는 것이었습니다. 
* CSS 코드를 작성하는 사람들은 패딩과 테두리를 빼는 식으로 늘 원하는 것보다 작은 너비값을 지정해왔습니다.
*  다행히도 이제 더는 그렇게 하지 않아도 됩니다.

## **box-sizing**
- 오랜 시간에 걸쳐 사람들은 너비값을 조절하는 해법이 그다지 만족스럽지 않다는 사실을 깨닫고 `box-sizing`이라고 하는 새로운 CSS 프로퍼티를 만들어냈습니다.
- 엘리먼트에 `box-sizing`을 지정하면 해당 엘리먼트의 패딩과 테두리가 더는 너비를 늘리지 않습니다.
- 다음은 이전 페이지와 동일한 예제이지만 두 엘리먼트에 모두 `box-sizing: border-box;`를 지정했습니다.
    ```css
    ex)
    .simple {
        width: 500px;
        margin: 20px auto;
        -webkit-box-sizing: border-box;
            -moz-box-sizing: border-box;
                box-sizing: border-box;
    }

    .fancy {
        width: 500px;
        margin: 20px auto;
        padding: 50px;
        border: solid blue 10px;
        -webkit-box-sizing: border-box;
            -moz-box-sizing: border-box;
                box-sizing: border-box;
    }
    ```
## **position**
- `position` 프로퍼티에는 다양한 값을 설정할 수 있으며, 각 값의 이름은 제대로 지어지지 않아서 기억하기가 불가능합니다.

    - `static`
        ```css
        ex) 
        .static {
            position: static;
        }
        ```
        - `static`은 기본값입니다. `position: static;`이 설정된 엘리먼트는 그다지 특별한 방식으로 위치가 지정된 것이 아닙니다.
        - 정적(static) 엘리먼트는 위치가 지정된 것이 아니라고 표현하며, `static`이 아닌 다른 값으로 지정된 엘리먼트에 대해 위치가 지정됐다고 표현합니다.

    - `relative`
        ```css
        ex)
        .relative1 {
            position: relative;
        }
        .relative2 {
            position: relative;
            top: -20px;
            left: 20px;
            background-color: white;
            width: 500px;
        }
        ```
        - `relative`는 별도의 프로퍼티를 지정하지 않는 이상 `static`과 동일하게 동작합니다.
        - 상대 위치가 지정된 엘리먼트에 `top`이나 `right`, `bottom`, `left`를 지정하면 기본 위치와 다르게 위치가 조정됩니다.
        - 다른 콘텐츠는 해당 엘리먼트에서 남긴 공백에 맞춰 들어가게끔 조정되지 않을 것입니다.

    - `fixed`
        - 고정(fixed) 엘리먼트는 뷰포트(viewport)에 상대적으로 위치가 지정되는데, 이는 페이지가 스크롤되더라도 늘 같은 곳에 위치한다는 뜻입니다. 
        - `relative`와 마찬가지로 `top`이나 `right`, `bottom`, `left` 프로퍼티가 사용됩니다.
        <br><br>
        + 페이지의 우측 하단 구석에 고정된 엘리먼트가 있다는 사실을 눈치채셨을 겁니다.
        + 이 엘리먼트를 눈여겨보세요.

        ```css
        ex)
        .fixed {
            position: fixed;
            bottom: 0;
            right: 0;
            width: 200px;
            background-color: white;
        }
        ```
        - 고정 엘리먼트는 평소대로라면 있었을 법한 공백을 페이지에 남기지 않습니다.

        - 모바일 브라우저의 경우 고정 엘리먼트 지원이 굉장히 불안정합니다.
        - 이와 관련된 사항은 이곳에서 좀 더 자세히 확인하실 수 있습니다.
        - http://bradfrost.com/blog/mobile/fixed-position/

    - `absolute`
        - `absolute`는 가장 다루기 까다로운 위치 지정 값입니다.
        - `absolute`는 뷰포트에 상대적으로 위치가 지정되는 게 아니라 가장 가까운 곳에 위치한 조상 엘리먼트에 상대적으로 위치가 지정된다는 점을 제외하면 `fixed`와 비슷하게 동작합니다.
        - 절대 위치가 지정된 엘리먼트가 기준으로 삼는 조상 엘리먼트가 없으면 문서 본문(document body)을 기준으로 삼고, 페이지 스크롤에 따라 움직입니다.
        - **"`absolute`" 엘리먼트는 `position`이 `static`으로 지정되지 않은 엘리먼트를 가리킨다는 사실을 기억하세요.**

        ```css
        ex)
        .relative {
            position: relative;
            width: 600px;
            height: 400px;
        }
        .absolute {
            position: absolute;
            top: 120px;
            right: 0;
            width: 300px;
            height: 200px;
        }
        ```
## **float**
* 레이아웃을 잡는 데 사용하는 또 하나의 CSS 프로퍼티는 바로 `float`입니다.
* `float`은 다음과 같이 이미지 주위를 텍스트로 감싸기 위해 만들어진 것입니다
    ```css
    ex)
    img {
        float: right;
        margin: 0 0 1em 1em;
    }
    ```

## **clear**
* `clear` 프로퍼티는 `float`의 동작 방식을 제어하는 데 중요합니다.
* 아래의 두 예제를 비교해 봅시다.
    ```html
    <div class="box">...</div>
    <section>...</section>
    ```
    ```css
    .box {
        float: left;
        width: 200px;
        height: 100px;
        margin: 1em;
    }
    ```
    - 이 경우 `section` 엘리먼트는 실제로 `div` 다음에 있습니다.
    - 하지만 `div`가 왼쪽으로 떠 있기 때문에 이런 결과가 나타난 것입니다.
    - 즉, `section` 안의 텍스트가 `div` 주위에 떠 있고 `section`이 전체를 감싸고 있습니다.
    - `section`을 실제로 떠 있는 엘리먼트 다음에 나타나게 하려면 어떻게 해야 할까요?
    ```css
    .box {
        float: left;
        width: 200px;
        height: 100px;
        margin: 1em;
    }
    .after-box {
        clear: left;
    }
    ```
    - `clear`를 이용해 이제 이 섹션을 떠 있는 `div` 아래로 옮겼습니다.
    - 여기서는 `left` 값을 지정해 왼쪽에 떠 있는 엘리먼트들을 비웠습니다.
    - 게다가 오른쪽(`right`)과 양쪽(`both`)도 비울 수 있습니다.

## **clearfix hack**
* 다음은 `float`를 사용할 때 때때로 일어날 수 있는 이상하고 바람직하지 않은 경우입니다.
    ```css
    img {
        float: right;
    }
    ```
* `img`가 컨테이너 박스로 삐져나옴
* 이 문제를 해결하는 방법이 하나 있긴 하지만 조금 지저분합니다.
- 이를 clearfix hack이라고 합니다.
    ```css
    /* 예전 방식(비추천) */
    .clearfix {
        overflow: auto;
    }
    /* 새로운 방식(추천) */
    .clearfix::after {
        content: "";
        clear: both;
        display: table;
    }
    ```

## **media queries(미디어 쿼리)**
* "반응형 디자인"은 사이트가 표시되는 브라우저와 디바이스에 "반응하는" 사이트를 만드는 전략입니다.

* 미디어 쿼리는 이렇게 하는 가장 강력한 도구입니다.
* 아래의 퍼센트 너비를 사용하는 레이아웃을 가지고 메뉴를 사이드바에 놓기에는 브라우저 창의 크기가 너무 작을 때 메뉴가 한 칼럼에 표시되도록 만들어 봅시다.
    ```css
    @media screen and (min-width:600px) {
        nav {
            float: left;
            width: 25%;
        }
        section {
            margin-left: 25%;
        }
    }
    @media screen and (max-width:599px) {
        nav li {
            display: inline;
        }
    }
    ```
* 짜잔! 이제 레이아웃이 모바일 브라우저에서도 멋지게 보입니다.
* `min-width`와 `max-width` 말고도 알아낼 수 있는 것이 굉장히 많습니다.
* 이와 관련된 자세한 사항을 알고 싶다면 MDN 문서를 참고하세요.
* [참고] 메타 뷰포트(meta viewport)를 이용하면 레이아웃을 모바일에서도 훨씬 더 나은 모습으로 보이게 할 수 있습니다.
    * https://dev.opera.com/articles/an-introduction-to-meta-viewport-and-viewport/

## **inline-block**
* 브라우저 너비를 채우고 알맞게 줄바꿈되는 박스 그리드를 만들 수 있는데, 그동안 이러한 박스 그리드를 만드는 방법은 `float`를 이용하는 것이었습니다.
* 하지만 이제 `inline-block`을 이용하면 만들기가 훨씬 더 쉽습니다.
* `inline-block` 엘리먼트는 `inline` 엘리먼트와 비슷하지만 **너비와 높이를 지정할 수 있습니다**.
* 두 접근법의 예제를 모두 살펴봅시다.
    ```css
    /* 힘든 방법(float를 이용) */

    .box {
        float: left;
        width: 200px;
        height: 100px;
        margin: 1em;
    }
    .after-box {
        clear: left;
    }
    ```

    ```css
    /* 쉬운 방법(inline-block을 이용)
        display 프로퍼티에 inline-block 값을 이용하면 똑같은 효과를 낼 수 있습니다. */

    .box2 {
        display: inline-block;
        width: 200px;
        height: 100px;
        margin: 1em;
    }
    ```

## **inline-block 레이아웃**
* 레이아웃을 잡기 위해 `inline-block`을 사용할 수도 있습니다.
* 이때 몇 가지 염두에 둘 점이 있습니다.

* `inline-block` 엘리먼트는 `vertical-align` 프로퍼티의 영향을 받습니다
    * (아마 이 프로퍼티는 `top`으로 설정하고 싶을 겁니다).
* 각 칼럼의 너비를 설정할 필요가 있습니다.
* HTML의 각 칼럼 사이에 공백이 있으면 칼럼 간에 틈이 생깁니다.
    ```css
    nav {
        display: inline-block;
        vertical-align: top;
        width: 25%;
    }
    .column {
        display: inline-block;
        vertical-align: top;
        width: 75%;
    }
    ```
## **칼럼**
* 다중 칼럼 텍스트를 손쉽게 만들 수 있는 CSS 프로퍼티가 새로 생겼습니다. 한번 살펴보시죠.
    ```css
    .three-column {
        padding: 1em;
        -moz-column-count: 3;
        -moz-column-gap: 1em;
        -webkit-column-count: 3;
        -webkit-column-gap: 1em;
        column-count: 3;
        column-gap: 1em;
    }
    ```
* CSS 칼럼은 아주 최근에 생겼기 때문에 접두사를 사용할 필요가 있으며, IE9까지 또는 오페라 미니에서는 동작하지 않습니다.

## **flexbox**
* 새로운 `flexbox` 레이아웃 모드는 우리가 CSS로 레이아웃을 잡는 방법을 재정의할 기세입니다.
* 아쉽게도 `flexbox` 규격이 최근에 상당히 많이 바뀌었기 때문에 각 브라우저마다 다른 식으로 구현돼 있습니다.
* 그럼에도 어떤 것인지 알아두는 차원에서 몇 가지 예제를 공유하고자 합니다.
* 여기서 선보이는 예제는 현재 최신 버전의 표준을 사용하는 일부 브라우저에서만 동작합니다.
<br>
* `flexbox`와 관련된 오래된 자료가 굉장히 많습니다.
* `flexbox`에 관해 좀 더 배우고 싶다면 참고 자료가 최신 내용을 반영하고 있는지 확인하는 방법을 배울 수 있도록 이곳에서 시작하세요.
    * https://css-tricks.com/old-flexbox-and-new-flexbox/
* `flexbox`를 이용해서 할 수 있는 일은 아주 많습니다.
* 영감을 주는 차원에서 몇 가지 예제를 알려주자면 다음과 같습니다.
    ```css
    flexbox를 이용한 간단한 레이아웃
    .container {
        display: -webkit-flex;
        display: flex;
    }
    nav {
        width: 200px;
    }
    .flex-column {
        -webkit-flex: 1;
                flex: 1;
    }
    ```
    ```css
    flexbox를 이용한 멋진 레이아웃
    .container {
        display: -webkit-flex;
        display: flex;
    }
    .initial {
        -webkit-flex: initial;
                flex: initial;
        width: 200px;
        min-width: 100px;
    }
    .none {
        -webkit-flex: none;
                flex: none;
        width: 200px;
    }
    .flex1 {
        -webkit-flex: 1;
                flex: 1;
    }
    .flex2 {
        -webkit-flex: 2;
                flex: 2;
    }
    ```
    ```css
    flexbox를 이용한 중앙 정렬
    .vertical-container {
        height: 300px;
        display: -webkit-flex;
        display:         flex;
        -webkit-align-items: center;
                align-items: center;
        -webkit-justify-content: center;
                justify-content: center;
    }
    ```