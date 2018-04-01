# CSS3 

* 인라인 > 내부(동일한 것은 마지막라인이 읽힌다) > 외부
* html 순서에 따라 적용이 달라진다.

----------------------------------------------------
## CSS 선택자 (Selectors)

- [요소 선택자 (Element Type Selector)]
    * `figure { ... }`
    * 요소를 선택합니다. 

- [그룹핑 (Grouping)] **(자주 쓰임)**
    * `a, abbr { ... }`

- [전체 선택자 (Universal Selector)]
    * `* { ... }`
    * 모든 태그 다 적용

- [자손 선택자 (Descendent Selector)]
    * `h1 abbr { ... }`

- [자식 선택자 (Child Selector)]
    * `.parent > .child { ... }`

- [클래스 선택자 (Class Selector)]
    * `.class { ... }`
    * 문서에서 복수 지정

- [멀티 클래스 선택자 (Mutil Class Selector)]
    * `.class1.class2 { ... }`

- [아이디 선택자 (ID Selector)]
    * `#id { ... }`
    * 문서에서 id 이름이 한번만 지정할 수 있음 
        * ex) 로고, 하단 정보값

- [속성 선택자 (Attribute Selector)]
    
    * `[id]              { ... }`
    * `[class]           { ... }`
    * `[title]           { ... }`
    * `[shape][title]    { ... }`
    <br><br>
    - `[id="about-css"]  { ... }`
    - `#about-css        { ... }`
    <br><br>
    + `[class="note"]    { ... }`
    + `.note             { ... }`
    <br><br>
    * `[href^="http://"] { ... }`
    * `[src$=".svg"]     { ... }`
    * `[src*="phone"]    { ... }`

- [가상 클래스 (Pseudo Class)]
    * 가상(pseudo) 클래스 선택자는 클래스 선택자는 아니지만 엘리먼트들의 상태에 <br>
    따라서 마치 클래스 선택자처럼 여러 엘리먼트를 선택할 수 있다는 점에서 붙은 이름입니다.
    <br><br>
    - `:link         { ... }`   // 방문한 적이 없는 링크
    - `:visited      { ... }`   // 방문한 적이 있는 링크
    <br><br>
    + `:hover        { ... }`   // 마우스를 롤오버 했을 때
    + `:active       { ... }`   // 마우스를 클릭했을 때
    <br><br>

    * **위의 선택자는 순서대로 지정하는 것이 좋습니다.**
    * 특히 `:visited`의 경우는 보안상의 이유로 아래와 같은 속성만 변경이 가능합니다. 
        - `color`
        - `background-color`
        - `border-color`
        - `outline-color`
        - The color parts of the fill and stroke properties
    <br><br>
    * `:focus        { ... }`   // 커서 깜박이는 곳 적용 
    * `:focus:hover  { ... }`
    * `:focus:active { ... }`
    <br><br>
    + `:first-child  { ... }`
    + `:last-child   { ... }`
    + `:nth-child(n) { ... }`
    <br><br>
    - 앞에서 2n+1번째(홀수) 태그 속성
    
        `h4:nth-child(2n+1){ }`
    
    * 뒤에서 2n번째(짝수) 태그 속성

        `h4:nth-last-child(2n){ }`

    * `:lang(ko)     { ... }`


- [가상 요소 (Pseudo Element)]
    
    * `::first-letter { ... }`  // 첫번째 글자에 적용
    * `::first-line   { ... }`  // 첫 줄에 적용 
    * `::before       { ... }`
    * `::after        { ... }`
    <br><br>
    + `::checked` // 체크시 적용 

- 동위 선택자 
    * `+` - 선택자 A `+` 선택자 B
        - 선택자 A **바로 뒤**에 위치하는 선택자 B를 선택

    * `~` - 선택자 A `~` 선택자 B 
        - 선택자 A 뒤에 위치하는 선택자 B를 선택

    ```css
    // ex) 피규어 부분 코드
    
    figure::before {
        content: 'Figure';
        display: block;
        margin-bottom: 10px;
        border-radius: 4px;
        padding: 0.3em 0.8em;
        background: #222;
        color: #fff;
    }
    ```
----------------------------------------------
## CSS 상속 (Inheritance)

- 상속되는 속성 (글자색, 글자 디자인에 관련된 것)
    * `color`
    * `font-size`
    * `font-family`
    * `letter-spacing`

- 상속되지 않는 속성 (공간에 관련된 것)
    * `outline`
    * `margin`
    * `border`
    * `padding`

-----------------------------------------------

## CSS 캐스케이드 (Cascade)

- cascading:
    * The process of combining several style sheets and resolving conflicts between them.

    * Håkon Wium Lie (CSS 공동 창시자)는 CSS에 관한 PHD 논문에서 "여러 스타일 시트를<br>
     결합하고 이들 사이의 충돌을 해결하는 프로세스"라는 용어로 "Cascade"를 말하고 있습니다.
    
    * https://www.wiumlie.no/2006/phd/

- CSS(Cascading Style Sheets )는 캐스케이드 개념이 중요하다는 것을 약어에서 강조.
    <br>가장 기본적인 수준에서는 규칙 순서가 중요하지만 그보다 더 복잡하다는 것을 말한다.

    1. 중요성 (Importance)
        * `!important` 선언은 다른 모든 선언보다 우선권을 가진다.

    > [NOTE]
    >    * !important가 적용된 속성을 덮어 쓰려면, 다시 !important를 사용해야 하기에<br>
         최대한(절대!!) 사용하지 않도록 노력해야 한다.


    2. 특성 (Specificity)
       * 선택자의 우선권에 대한 척도. 
       * 각 척도를 1, 10, 100, 1000 단위로 생각하면 이해하기 좋다.

    ```
       요소 선택자 < 클래스 선택자 < ID 선택자 < 인라인 스타일
       0,0,0,1       0,0,1,0       0,1,0,0     1,0,0,0
    ```

    > [NOTE]
    > * *, >, +, ~ 등 콤비네이터(Combinators),
    > * :not() 가상 클래스는 특성에 영향을 주지 않는다.
    ```css
    [예시]
        *                         -- 0000
        a                         -- 0001
        .link                     -- 0010
        a[href]                   -- 0011
        li:nth-child(2) a:hover   -- 0022
        .nav:nth-child(2) a:hover -- 0031
        #outer a                  -- 0101
        #outer #inner a           -- 0201
        style="color: tan"        -- 1000
                                  -- !important
    ```
  
    3. 소스 순서
      중요성, 특성이 설정되지 않았거나 동일한 경우
      나중에 나온 소스의 스타일이 우선권을 가진다.
    ```css
      [예시]
        p { color: #930212; }
        p { color: #d5727e; } // 우선권을 가진다.
    ```
    * 참고: https://goo.gl/BAhjiN

------------------------------------------------
##  CSS 타이포그래피 (Typography)

- 폰트(Fonts) 스타일 속성
    * 폰트에 영향을 주는 속성으로 적용되는 모양, 크기, 굵기, 기울임 등.
        * `font-family`
        * `font-size`
        * `font-weight`
        * `font-style`
        * `font-variant`
    
    * `font-size` : 글꼴의 크기를 지정
        * 주요 단위 : `px`, `em`, `rem`
        * `rem` **(권장)**

            - html 태그에 적용된 `font-size`의 영향을 받습니다. 
            - html 태그의 폰트 크기에 따라서 상대적으로 크기가 결정되기 때문에 이해하기 쉽습니다.  

        * `px`

            - 모니터 상의 화소 하나의 크기에 대응되는 단위입니다. 
            - 고정된 값이기 때문에 이해하기 쉽습니다만, 사용자가 글꼴의 크기를 <br>
            조정할 수 없기 때문에 가급적 사용을 하지 않는 것이 좋습니다. 

        * `em`

            - 부모 태그의 영향을 받는 상대적인 크기입니다. 
            - 부모의 크기에 영향을 받기 때문에 파악하기가 어렵습니다. 
            - `rem`이 등장하면서 이 단위 역시 사용이 권장되지 않습니다. 

    * `font-family` : 서체를 지정하는 속성
        ```css
        h1{font-family: "Times New Roman", Times, serif;}
        ```
        - 사용자의 컴퓨터에 폰트가 없으면 Times New Roman을 사용 
        - 이 때 마지막 폰트는 포괄적인 폰트로 지정합니다. 
        - 아래와 같은 것이 있습니다.  
            - serif (장식이 있는 폰트)
            - sans-serif
            - cursive (흘림체)
            - fantasy
            - monospace (고정폭)

    * `font-weight` : 폰트의 두께
        - 대체로 `bold`만 기억하시면 됩니다.
        - `bold`를 사용하면 폰트가 두껍게 표시됩니다.
        - `normal`
        - 정수표현으로도 가능하다.

    * ※ 글자 색상은 color 속성으로 설정.
    ```css
        color keywords: red, gree, blue, pink, black
        
        hex color code: #RRGGBB / 0 ~ 9, a ~ f 
            예) #1868a7
        
        rgb, rgba: RED, GREEN, BLUE, ALPHA 
            예) rgba(127,255,0,0.3)
        
        hsl, hsla: HUE, SATURATION, LIGHTNESS, ALPHA 
            예) hsla(360,60%,70%,1)
    ```  
    * ※ 웹브라우저는 운영체제가 지원하는 기본 폰트(웹 안전 폰트)만 화면에 렌더링 한다. <br>
    (참고: cssfontstack.com)
        * 즉, 사용된 폰트가 사용자 컴퓨터에 없으면 렌더링 X.
    
        ```css
            웹 안전 폰트
            Arial            [sans-serif]  고딕체
            Verdana          [sans-serif]  고딕체
            Courier New      [monospace]   코드체(공간이 동일)
            Georgia          [serif]       명조체
            Times New Roman  [serif]       명조체
            Trebuchet MS     [serif]       명조체
        ```

        * 하지만 웹 안전 폰트만으로 디자인 하는 디자이너는 없다!
        * Helvetica는 디자이너가 애용하는 폰트이지만...
        * Windows는 기본 지원하지 않는다. (Mac OSX는 지원)

    * ※ 비주얼 디자인 과정에서 적용 가능한 웹폰트를 사용해야 한다. 
        <br>폰트 저작권에 주의! (참고: hyundaicard.com)

    * ※ 저작권 걱정 없는 폰트
        * fonts.google.com
        * google.co.kr/search?q=무료+웹폰트

  --------------------------------------------------

 - 텍스트(Text) 레이아웃 속성
    * 텍스트 간격 및 레이아웃 기능에 영향을 주는 속성으로
      <br>행간, 자간, 어간, 정렬, 변형, 꾸밈, 그림자
        + `line-height`
        <br><br>
        - `letter-spacing`
        - `word-spacing`
        <br><br>
        * `text-align`
        * `text-indent`
        * `text-transform`
        * `text-decoration`
        * `text-shadow`
        <br><br>
        - `white-space`
        - `word-break`
        - `word-wrap`

    * `line-height` : 행과 행 사이의 간격을 지정
        - 기본 값은 normal로 수치로는 1.2에 해당합니다.
        -  이 수치를 기준으로 간격을 조정하면 됩니다.
        -  값이 1.2라면 현재 엘리먼트 폰트 크기의 1.2배만큼 간격을 준다는 의미입니다. 
        ```css
        p {line-height: 1.3;}
        ```
    * `text-indent`:-9999px; --> 텍스트를 숨기는 방법
    * `text-decoration` : `overline`, `underline`
    * `text-transform` : 글자변환
        - `uppercase` : 대문자
        - `lowercase` : 소문자
    * `text-align`:정렬
        - `left`
        - `right`
        - `center`
        - `justify`

    * `vertical-align` : 세로정렬

    * `word-break` : 줄 바꿈할때 글자 기준인지 단어 기준인지
        - `break-all` : 글자 기준(반응형 웹사이트 기준)
        - `keep-all` : 단어 기준

-----------------------------------------------------------
## CSS 박스 모델 (Box Model)

- CSS를 사용해 HTML 요소를 레이아웃(배치) 하려면 박스 모델에
    <br>대해 먼저 이해해야 한다.

    * [BLOCK vs INLINE]
      * block level 요소 (Flow Contents)
      * inline 요소 (Phrasing Contents)
    
    * `display` : 공간 + 태그
        - `inline` : 화면의 일부를 차지하는 태그 // 가로로 글나오게
        - `block` : 화면 전체를 사용하는 태그 // li처럼 찍기 

        |[block 요소들]||
        |:---|:--- |
        |* address | * form|
        |* article|  * h1~6|
        |* aside| * header|
        |* audio| * hr|
        |* blockquote| * noscript|
        |* canvas|  * ol, ul|
        |* dd| * output|
        |* div|  * p|
        |* dl| * pre|
        |* fieldset| * section|
        |* figcaption| * table|
        |* figure|  * tfoot|
        |* footer| * video|
    
    * [BOX]
      * `margin-box`   --  외부 공간 박스
      * `border-box`   --  테두리 공간 박스
      * `padding-box`  --  내부 공간 박스
      * `content-box`  --  콘텐츠 공간 박스

    * [margin]
        - 길이 : 고정된 너비를 지정. 음수값 지정 가능
        - 백분율 : 용기 블럭의 너비를 참조
        - `auto` : 자동으로 계산된 값을 지정
        - `inherit` : 부모 엘리멘트의 값을 상속
        <br><br>
        * `margin-top`
        * `margin-right`
        * `margin-bottom`
        * `margin-left`
        * `margin: t r b l`
        * `margin: t r b (l=r)`
        * `margin: t r (b=t) (l=r)`
        * `margin: t (r=t) (b=t) (l=r)`

    * [border]
        * `border-width`
            * `thick` : 5px, `thin` : 1px, `medium` : 3px [default값]
            * 길이 : 테두리의 두께를 지정하는 명시적인 값으로 음수가 될 수 없다.
            * `inherit`

        * `border-style`: 테두리 스타일
            * `none` : 선없음 [default 값]
            * `hidden` : 숨김(= `none`)
            * `dotted` : 점선
            * `dashed` : 긴 점선
            * `solid` : 실선
            * `double` : 이중실선
            
        * `border-color`
            - 색상
            - `transparent`
        
        * `border-radius` : 네 개의 모서리 부분 둥글게 처리

        * 다양한 속성 : 익스에서 미지원
            * `groove`
            * `ridge`
            * `inset`
            * `outset`
        <br><br>
        + `border-(top|right|bottom|left)-width`
        + `border-(top|right|bottom|left)-style`
        + `border-(top|right|bottom|left)-color`
        + `border: width style color`
        + `border-top: width style color`
        + `border-right: width style color`
        + `border-bottom: width style color`
        + `border-left: width style color`
        
    * [padding]
        - `길이` : 고정된 너비를 지정 ('10px', '1em' 등 ).
        <br>음수값은 지정할 수 없다.
        - `백분율` : 용기 블럭의 너비를 참조
        - `auto` : 자동으로 계산된 값을 지정
        - `inherit` : 부모 엘리멘트의 값을 상속
        <br><br>
        * `padding-top`
        * `padding-right`
        * `padding-bottom`
        * `padding-left`
        * `padding: t r b l`
        * `padding: t r b (l=r)`
        * `padding: t r (b=t) (l=r)`
        * `padding: t (r=t) (b=t) (l=r)`

    * [DIMENSION]
      * `width`       --  박스 너비
      * `height`      --  박스 높이
      * `min-width`   --  박스 최소 너비
      * `min-height`  --  박스 최소 높이
      * `max-width`   --  박스 최대 너비
      * `max-height`  --  박스 최대 높이

    * [BOX SIZING]
      * `content-box`
      * `border-box`

      - `content-box` (default):
        <br>`width = content-box`
        <br>`height = content-box`

      - `border-box`:
        <br>`width = content-box + padding-box + border-box`
        <br>`height = content-box + padding-box + border-box`

    * [FLOW]
      * `overflow`  --  박스를 넘쳐난 상태(흐름) 조정
        - `auto`
        - `visible`
        - `hidden`
        - `scroll`

    * `box-shadow` :박스에 그림자 효과  
        - 순서
        - `h-shadow` : 수평그림자
        - `v-shadow` : 수직그림자
        - `blur` : 그림자 흐림
        - `spread` :그림자 번짐
        - `color` : 그림자 속성
        - `inset` : 삽입효과

----------------------------------------------------------
* `list-style` : 목록 항목의 속성(`list-style`, `list-style-position`, `list-style-image`)을 한꺼번에 지정하는 약식속성

- 로고
    - `background` : `url(로고이미지);`
    - `background-repeat` : `no-repeat;`

* `float` : 문단 배치의 명령어 
    - `left`
    - `right` 
    - `none` 

* `clear` : float 속성을 해제한다.
    - `left` : 왼쪽 플로트 해제. 즉 float:left를 해제한다.
    - `right` : 오른쪽 플로트 해제. 즉 float:right를 해제한다.
    - `both` : 왼쪽과 오른쪽 모두 플로트 해제.
    - `none` : float를 해제하지 않는다.

* `cursor` : 마우스 커서의 모양지정

* `position` : 텍스트, 이미지 표 등의 요소를 문서에 배치하는 속성 (위치 설정)
    - `static` : 정적위치 설정 (이동 불가능)
    - `relative` : 상대위치 설정 (이동 가능)
    - `absoulte` : 절대위치 설정 - 자주보는것 / 원하는위치에 메뉴를 움직이게 할 수있음
    - `fixed` : 고정위치 설정 - 메뉴가 고정되있는것
    
* `z-index` :한 요소 위에 다른 요소를 쌓을 때 사용
    - `position`의 속성값이 static 아닌 요소들
    - `auto`
    - 정수 : 값이 클 수록 위에 표시된다. 
    숫자가 크면 클수로 위 (~9999)

### 모션그래픽 ###
* `transition` : 변환
    - 엘리먼트의 크기, 위치, 모양을 변경하는 속성
    ```css
    transition:all 1.5s linear 0.5s;
	```
* `visibility` : 생성된 엘리먼트를 보이게 할지 안보이게 할지를 지정
	- **(최근자주쓰는 것)** 마우스 접근시 보여주는 효과에 사용 
    - `visible` : 엘리먼트를 보이게 지정한다
    - `hidden` : 엘리먼트를 보이지 않게 지정한다. 배치에 영향을 준다.
    - `collapse` : 테이블의 열, 행, 그룹요소들에 지정한 경우 요소를 보이지 않게 하며, 다른 요소에 지정한경우 `hidden`과 같은 의미가 된다. 대부분의 브라우저에서 지원하지 않는다.


* `opacity` : 불투명도 조절 (default:1)
    | 불투명도 : 0.0(완전 투명) ~ 1.0(완전 불투명)
    
출처: 생활코딩 CSS - https://opentutorials.org/course/2418
