##HTML5

- 섹션(Sections) 요소들과 메인(Main) 요소
    1. 루트 섹션(Root Section) 요소
        - `<body>`
        - 문서에서 단 1번만 사용가능
    2. 섹션(Sections) 요소들
        - 섹션 요소는 일반적인 컨테이너 요소가 아니며, **문서 개요에 명시적으로 나열되는 경우에만 섹션 요소가 적합하다**는 규칙이 있다.
        - 일반적인 컨테이너 요소로는 `<div>`, `<span>` 등이 있다.

        - `<article>`
            - 문서, 페이지, 애플리케이션, 사이트 등에 포함된 **독립적인 섹션**을 말한다.
            - 잡지, 신문, 논문, 에세이, 보고서, 블로그, 기타 소설 미디어 일 수 있음.
            - 일반적인 규칙은 article 요소의 내용이 **문서 개요에 명시적으로 나열되는 경우에만 적합하다.** 각 article 요소는 일반적으로 요소의 하위 항목으로 **제목(h1~h6 요소)을 포함시켜 식별해야 한다.**

            - [예시]
            ```html
            <article>
                <h2>기사 제목</h2>
                ...
            </article>
            ```
        - `<section>`
            - section 요소는 문서, 애플리케이션의 **일반적인 섹션**을 말한다.
            - 이 컨텍스트의 섹션은 주제별로 그룹화 된 콘텐츠이다.
            - 웹 사이트의 섹션은 소개(introduction), 뉴스 항목(news item), 연락처 정보(contact information)를 위한 섹션으로 나눌 수 있다.
            - 각 section 요소는 일반적으로 요소의 하위 항목으로 **제목(h1~h6 요소)을 포함시켜 식별해야 한다.**

            - [참고]
                - 콘텐츠가 사이트에 포함된 독립적인 섹션의 성향이 크다면 section 요소 대신 article 요소를 사용하는 것이 좋다.

        - `<aside>`
            - 웹 사이트의 사이드바에 해당되는 부 콘텐츠(메인 콘텐츠와 분리된) 섹션을 말한다. / **주로 광고**
        
        - `<nav>` : 문서를 연결하는 네비게이션 링크 <- 메뉴바 생성 예전엔 `div` 사용

            - 다른 페이지로 이동하는 링크 또는 사이트 내 탐색 링크를 포함하는 섹션 요소이다.

            - ex1) 사이트 헤더 만드는 부분
            ```html
            <header>
            <nav>
            <ul>
            ```
            - ex2)
            ```html
            <section id="">
            <div id="" class="">
            <header>
            ```
            - [참고]
                - 내용을 쉽게 이해할 수 있도록 nav 요소 내부에는 비순차 목록(ul)을 사용한다.
                - 사이트의 모든 링크를 nav에 포함하는 것은 아니며, 주로 사이트를 탐색하는 링크를 포함한다.
                - 사이트 하단에 위치한 링크는 footer 요소로도 충분하다.
    3. 섹션 내부에 사용되는 요소들
        - `<header>`
            - header 요소는 일반적으로 섹션의 제목, 목차, 검색, 로고 등을 포함하는데 사용한다.
            - ex1) 사이트 시작부분에 사용하는 해더라면 사이트 맨 위나 왼쪽에 주로 삽입

            - ex2) 헤더안에 `<form>`사용해서 검색 창 넣거나 `<nav>`사용해서 사이트 메뉴 넣습니다.
        - `<footer>`
            - footer 요소는 일반적으로 섹션의 저자, 링크, 저작권 정보 등을 포함하는데 사용한다.
    4. 메인(Main) 요소
        - `<main>`
            - 문서 또는 애플리케이션 body 요소의 메인 콘텐츠에 해당한다.
            - main 요소는 섹션 요소가 아니며, 보이는 요소가 2개 이상이면 안된다.
            - 사용되지 않는 main 요소는 화면에서 감춤(hidden) 처리해야 한다.
            - article, section, aside, nav 요소는 main 요소를 자식으로 포함할 수 없다.
            - 반대로 main 요소는 섹션 요소들을 포함할 수 있다.
            - main 내부에는 header, footer 요소를 직접적으로 포함하지 않는다.

            - [예시]
            ```html
            <main>...</main>
            <main hidden>...</main>
            <main hidden>...</main>
            ```
- Grouping content
    - `<main>` 요소
    - `<div>` 요소
    - `<blockquote>`: 인용문 넣기 <- `<q>`와 유사
        - ex)`<blockquote [속성]>인용내용</>`
        - [속성] : cite="http://..."
    - `<p>` 요소
    - `<ul>` 요소
    - `<ol>` 요소
    - `<li>` 요소
    - 설명 목록(Description Lists)
        ```
        <dl> 설명 목록(Description Lists)
            <dt> 용어(Definition Term)
            <dd> 설명(Defintion Description)
        ```
        - ex1) **용어에 대한 정의 컨텐츠, QnA 컨텐츠** / 용어 - 설명 그룹(a term-description group)
        ```html
        <dl>

            <dt>Blanco tequila</dt>
            <dd>The purest form of the blue agave spirit...</dd>

            <dt>Reposado tequila</dt>
            <dd>Typically aged in wooden barrels for between two and eleven months...</dd>

        </dl>
        ```
        - ex2) **특정 내용에대한 소개 컨텐츠** / 용어 - 설명 그룹(The order of term-description groups)
        ```html
        <p>Information about the rock band Queen:</p>

        <dl>

            <dt>Members</dt>
            <dd>Brian May</dd>
            <dd>Freddie Mercury</dd>
            <dd>John Deacon</dd>
            <dd>Roger Taylor</dd>

            <dt>Record labels</dt>
            <dd>EMI</dd>
            <dd>Parlophone</dd>
            <dd>Capitol</dd>
            <dd>Hollywood</dd>
            <dd>Island</dd>

        </dl> 
        ```
        - ex3) **명령어 순서를 나열** 
            - 아래는 javascript 조건문을 문장으로 나열
        ```html
        <p>승점(victory points)을 다음과 같이 결정합니다.<br>
        (다음 유형 중 첫 번째로 일치하는 경우만 해당됩니다)</p>

        <dl>

            <dt>금화가 정확히 5개인 경우</dt>
            <dd>승점 5 점 획득</dd>

            <dt>금화가 하나 이상 있고, 은색 동전이 하나 이상 있는 경우</dt>
            <dd>승점 2 점 획득</dd>

            <dt>은색 동전이 하나 이상 있는 경우</dt>
            <dd>승점 1 점 획득</dd>

            <dt>그렇지 않으면</dt>
            <dd>승점을 얻지 못합니다.</dd>

        </dl>
        ```
        - 변경 사항 검토

            - HTML 5.2 표준 문서에서 거론된 예시는 아니지만 `<dt>`, `<dd>` 요소를 하나 이상 감싸는 `<div>` 요소를 `<dl>` 내부에 구성할 수 있습니다. 참고로 `<dl>` 내에 사용 되는 **`<div>` 요소는 하나 이상의 `<dt>`, `<dd>`를 감싸는 용도로만** 사용할 수 있습니다. 그리고 `<div>`와 `<dt>`, `<dd>` 요소는 형제 노드여서는 안됩니다.

        ```html
        <p>승점(victory points)을 다음과 같이 결정합니다.<br>
        (다음 유형 중 첫 번째로 일치하는 경우만 해당됩니다)</p>

        <dl>

            <div>
                <dt>금화가 정확히 5개인 경우</dt>
                <dd>승점 5 점 획득</dd>
            </div>

            <div>
                <dt>금화가 하나 이상 있고, 은색 동전이 하나 이상 있는 경우</dt>
                <dd>승점 2 점 획득</dd>
            </div>

            <div>
                <dt>은색 동전이 하나 이상 있는 경우</dt>
                <dd>승점 1 점 획득</dd>
            </div>

            <div>
                <dt>그렇지 않으면</dt>
                <dd>승점을 얻지 못합니다.</dd>
            </div>

        </dl>
        ```
        - 사용 시, 알아두어야 할 점

            - 다음은 `<dl>`, `<dt>`, `<dd>` 요소를 사용해 구조화 할 때 알아두어야 할 점을 나열한 것입니다.

            - `<dl>` 요소에 `<dt>` 또는 `<dd>` 자식 요소가 포함되지 않으면, 용어 설명 그룹이 아니게 됩니다.

            - `<dl>` 요소에 하나 이상의 공백이 아닌 텍스트 노드 하위 항목이 있거나, `<dt>`, `<dd>` 요소가 아닌 하위 항목이있는 경우 이러한 모든 텍스트 노드와 요소는 물론 해당 하위 항목도 모든 용어 설명 그룹의 일부를 구성할 수 없습니다. (`<dt>`, `<dd>` 요소 포함)

            - `<dl>` 요소가 1개 이상의 `<dt>` 요소를 포함 `<dd>` 요소는 포함하지 않은 경우, 설명 없는 용어 그룹입니다.

            - `<dl>` 요소가 1개 이상의 `<dd>` 요소를 포함 `<dt>` 요소는 포함하지 않은 경우, 용어 없는 설명 그룹입니다.

            - `<dl>` 요소의 첫번째 자식 요소가 `<dd>` 요소일 경우, 첫 번째 그룹은 연관된 용어가 없게 됩니다.

            - `<dl>` 요소의 마지막 자식 요소가 `<dt>` 요소일 경우, 마지막 그룹은 연관된 설명이 없게 됩니다.

    - 이미지파일 캡션 붙이기
        - `<figure>` : 캡션 대상 지정
        - `<figcaption>` : 캡션 설명 붙이기
    - `<hr>` 요소
    - `<address>` 요소
    - `<pre>` 요소 : 입력하는 그대로 화면을 표시

- 컨테이너 요소들
    - HTML 요소를 묶는 컨테이너 요소들
      - 아무런 의미(Semantic)는 가지지 않는다.
      - 그러하므로 이 요소들은 적절한 시멘틱 요소가 없을 때 사용해야 한다.

    - `<div>` 디비전(Division) 요소
      - 블록(block) 컨테이너

      - [사용 예시]
      ```html
      <article lang="en-US">
        <h2>My use of language and my cats</h2>
        <p>My cat’s behavior hasn’t changed much since her absence, except
        that she plays her new physique to the neighbors regularly, in an
        attempt to get pets.</p>
        <div lang="en-GB">
          <p>My other cat, colored black and white, is a sweetie. He followed
          us to the pool today, walking down the pavement with us. Yesterday
          he apparently visited our neighbours. I wonder if he recognizes that
          their flat is a mirror image of ours.</p>
          <p>Hm, I just noticed that in the last paragraph I used British
          English. But I’m supposed to write in American English. So I
          shouldn’t say "pavement" or "flat" or "color"...</p>
        </div>
        <p>I should say "sidewalk" and "apartment" and "color"!</p>
      </article>
      ```

    - <span> 스팬(Span) 요소 : 줄바꿈 없이 영역 묶기
      - 인라인(inline) 컨테이너
      - 인라인 요소들(a, strong, em, b, i 등)을 감쌀 때 사용된다.
      - 블록 요소들(h1~6, p, blockquote, section 등)을 감쌀 수 없다.

      - [사용 예시]
      ```html
      <h2>
        SIX
        <span>C</span>
        <span>O</span>
        <span>L</span>
        <span>O</span>
        <span>R</span>
        <span>S</span>
      </h2>
      ```

- 텍스트 레벨(Text Level) 요소들
  - `<sup>` 요소
    - 윗첨자
  - `<sub>` 요소
    - 아래첨자
  - `<mark>` 요소
    - 관련 참조 목적의 하이라이트된 글자 요소
  - `<abbr>` 요소
    - 축약 요소
  - `<time>` 요소
    - 기계가 이해할 수 있는 형태로 날짜나 시간을 나타내는 요소
  - `<s>` 요소
    - 더 이상 관련이 없거나 더 이상 정확하지 않은 요소

- 수평선: horizontal rule
- 각주: footnote

- `<a>`
    - [속성]
        - `href = "#"` <- "#"은 널링크(앵커연결됐다는 의미)
        - `target = "_block"` <- 새탭
        - `title = "링크내용설명"`
        - `name = ""` <- **이걸 지정하면 #이름으로 href 접근가능**

- 멀티미디어 요소 (사용할때만 W3C 문서 및 정리문서 보기)
    - `<img>` 요소
      - HTML 문서에 이미지를 포함(링크)

      - [속성]
        - src    - 이미지 파일 경로 설정
        - alt    - 이미지 대체 텍스트 설정
        - width  - 이미지 너비 설정
        - height - 이미지 높이 설정
        - usemap - 이미지 맵 연결 설정
        - title



    - `<picture>` 요소
      - 0개 이상의 `<source>` 요소와 1개 이상의 `<img>`를 포함하는 컨테이너 요소.
      - 다양한 스크린 환경에 맞는 적합한 이미지를 제공하기 위한 목적으로 사용.
      - `<source>` 요소를 사용할 수 없을 경우, `<img>` 요소가 화면에 표시.

      - [사용 예시]
      ```html
      media 속성:
      <picture>
        <source srcset="bamboo-pen.png" media="(min-width: 600px)">
        <img src="bamboo-pen-narrow.png" alt="Bamboo Pen">
      </picture>

      type 속성:
      <picture>
        <source srcset="bamboo-pen.svg" type="image/svg+xml">
        <img src="bamboo-pen-narrow.png" alt="Bamboo Pen">
      </picture>
      ```

    - `<source>` 요소
      - `<picture>`, `<audio>`, `<video>` 요소의 다중 미디어 리소스를 지정하기 위해 사용.

      - [사용 예시]
      ```html
      <video src="videofile.mp4" poster="posterimage.jpg" controls>
        <source src="videofile.webm" type="video/webm">
        <source src="videofile.ogg" type="video/ogg">
        <source src="videofile.mov" type="video/quicktime">
        HTML5 <code>video</code> 요소를 지원하지 않는 구형 웹 브라우저를 사용 중입니다.
        <a href="http://outdatedbrowser.com/ko">최신형 브라우저로 업데이트</a> 하세요.
      </video>
      ```

    - `<video>` 요소
      - 동영상 콘텐츠를 HTML 문서에 포함하기 위해서 사용.
      - src 속성이나 <source> 요소을 이용해 여러 개의 동영상 소스 중 하나를 표시.

      - [사용 예시]
      ```html
      <video src="videofile.mp4" poster="posterimage.jpg">
        HTML5 <code>video</code> 요소를 지원하지 않는 구형 웹 브라우저를 사용 중입니다.
        <a href="http://outdatedbrowser.com/ko">최신형 브라우저로 업데이트</a> 하세요.
      </video>
      ```
      - [속성]
        - src      - 비디오 파일 경로
        - poster   - 포스터 이미지 경로
        - preload  - 사용자 경험 향상(메타데이터 / 비디오 다운로드)에 관한 설정 [none, metadata, auto]
        - controls - 재생 컨트롤 표시 설정
        - autoplay - 자동 재생 설정
        - loop     - 반복 설정
        - muted    - 음소거 설정


    - `<audio>` 요소
      - 동영상 콘텐츠를 포함하기 위해서 사용.
      - src속성이나 <source> 요소을 이용해 여러개의 동영상 소스를 표시.

      - [사용 예시]
      ```html
      <audio src="audiofile.mp3">
        HTML5 <code>audio</code> 요소를 지원하지 않는 구형 웹 브라우저를 사용 중입니다.
        <a href="http://outdatedbrowser.com/ko">최신형 브라우저로
        업데이트</a>로 업데이트 하세요.
      </audio>
      ```
      - [속성]
        - src      - 오디오 파일 경로
        - volume   - 볼륨 조절(0.0 ~ 1.0)
        - muted    - 음소거 설정
        - poster   - 포스터 이미지 경로
        - preload  - 사용자 경험 향상(메타데이터 / 비디오 다운로드)에 관한 설정 [none, metadata, auto]
        - controls - 재생 컨트롤 표시 설정
        - autoplay - 자동 재생 설정
        - loop     - 반복 설정


    - `<track>` 요소
      - 비디오/오디오 재생 시, 자막을 표시.
      -  default 속성을 설정하지 않을 경우, 자막 사용 안함 됨

      - [사용 예시]
      ```html
      <video src="videofile.mp4" poster="posterimage.jpg">
        <track kind="subtitles" src="videofile.ko.vtt" srclang="ko" label="한국어" default>
        <track kind="subtitles" src="videofile.en.vtt" srclang="en" label="English">
      </video>
      

      <audio src="audiofile.mp3">
        <track kind="subtitles" src="audiofile.ko.vtt" srclang="ko" label="한국어">
        <track kind="subtitles" src="audiofile.en.vtt" srclang="en" label="English">
      </audio>
      ```

    - `<iframe>` 요소
      - 인라인 프레임(Inline Frame)에 다른 HTML 페이지를 포함하여 화면에 표시.
   
      [사용 예시]
      ```html
      <iframe
        width="560"
        height="315"
        src="https://www.youtube.com/embed/0wlXaHmmOVc?rel=0&amp;showinfo=0"
        allow="autoplay; encrypted-media"
        allowfullscreen></iframe>

      <iframe
        src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d12643.636820892792!2d127.01610674058901!3d37.60429582641849!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x357cbc91e5ca4f03%3A0x18820a16e406c8ea!2z7ISc7Jq47Yq567OE7IucIOyEseu2geq1rCDquLjsnYwx64-ZIDUzMC0zNg!5e0!3m2!1sko!2skr!4v1520001155674" width="600"
        height="450"
        style="border: 0"
        allowfullscreen></iframe>
      ```
      - [속성]
        - src             - 프레임 소스 설정
        - width           - 프레임 너비 설정
        - height          - 프레임 높이 설정
        - allowfullscreen - 프레임 전체화면 설정
        - seamless :테두리 없애기


    - `<map>` 요소
      - 이미지 맵(클릭 가능한 링크 영역)을 정의하기 위해 `<area>`와 함께 사용됨.

      [사용 예시]
      ```html
      <img src="products-map.jpg" alt="제품 모음" usemap="#products-map">
      <map name="products-map">
        <area
          shape="circle"
          coords="200,250,25"
          hreflang="en-GB"
          href="another.html"
          alt="Another Page"
          target="_blank">
      </map>
      ```

    - `<area>` 요소
      - 이미지의 핫스팟 지역 정의, 하이퍼링크 설정. `<map>` 내부에서만 사용 가능.

      - [속성]
        - shape    - 핫스팟 모양 설정
        - coords   - 모양의 좌표 값 설정
        - href     - 하이퍼링크 주소 설정
        - target   - 새 창(탭) 열림 설정
        - alt      - 대체 텍스트 설정
        - hreflang - 연결된 페이지의 언어 속성 설정
        - download - canvas 데이터 다운로드 설정


    - `<svg>` 요소
      - 확장가능한 벡터 그래픽(SVG)은 2차원의 벡터 그래픽을 기술하기 위한 XML 마크업 언어.

      - [예시 코드]
      ```html
      <img src="svgfile.svg" alt="SVG File">

      <svg width="150" height="150" viewBox="0 0 150 150">
        <circle r="50" cx="75" cy="75" fill="#333" stroke="#900" stroke-width="4" />
      </svg>
      ```
      
- Form 태그
  - `<form>`
    - 폼은 텍스트필드, 버튼, 체크박스와 같은 폼 컨트롤을 포함하는 웹 페이지의 컴포넌트를 말함.
    - 사용자와 인터랙션을 수행한 결과(예: 검색)를 서버로 보낼 수 있다.

    - [사용 예시]
      ```html     
        <form action="https://formspree.io/your@email.com" method="POST">
          ...
        </form>
      ```

  - `<input>`
    - 사용자의 데이터를 입력 받을 수 있는 폼 컨트롤을 말함.
    - 다양한 유형(Type) 설정이 가능하며, 유형에 맞는 역할을 수행한다.

      - [속성]
        - name
        - placeholder
        - value
        - readonly
        - required
        - disabled
        - minlength
        - maxlength
        - list

      - [유형]
        - text
        - password
        - checkbox
        - radio
        - file
        - submit
        - button
        - image
        - reset
        - hidden
        - search
        - url
        - tel
        - email
        - date
        - month
        - week
        - time
        - datetime-local
        - number
        - range
        - color


      - [사용 예시]
      ```html
        <input type="text">
        <input type="submit" value="전송">
        <input type="button" value="버튼">
        <input type="image" src="https://goo.gl/Ng66oQ" alt="체크인" width="20" height="20">
        <input type="reset" value="초기화">
        <input type="hidden" name="using-ajax" value="true">
        <input type="number" name="" id="" min="100" step="10" max="1000" value="150">
        <input type="range" name="" id="" min="10" step="5" max="25" value="15">
        <input type="color" name="" id="" value="#F7CC60">
      ```

  - `<label>`
    - 컨트롤에 레이블(이름)을 붙이고자 할 경우 사용.

    - [사용 예시]

      1. 
      ```html
      <label>이름 <input type="text" placeholder="이두연"></label>
      ```
      2. 
      ```html
      <label for="u_pass">비밀번호</label>
      <input id="u_pass" name="u_pass" type="password" maxlength="8" placeholder="비밀번호 8자리를 입력해주세요">
      ```

  - `<button>`
    - 버튼 폼 컨트롤로 사용자의 인터랙션을 받아 액션을 트리깅(방아쇠) 처리함.

    - [type]
      - submit (초기 값)
      - button
      - reset

      - [사용 예시]
      ```html  
        <button type="submit">전송</button>
        <button type="button">버튼</button>
        <button type="reset">초기화</button>
      ```
  - `<select>`
    - 드롭 다운 메뉴(옵션을 선택 할 수 있는) 컨트롤을 말함.
    - 내부에 `<option>` 요소를 포함하여 사용자에게 선택할 수 있도록 한다.
    - `<option>`을 묶어 그룹으로 만들고자 한다면 `<optgroup>` 요소를 사용하고,
    - label 속성을 사용해 그룹 이름을 설정한다.

      - [속성]
        - name
        - multiple
        - disabled
        - required
        - size

      - [사용 예시]
      ```html
        <label for="user_hobby">취미</label>
        <select name="user_hobby" id="user_hobby">
          ...
        </select>
      ```
  - `<option>`
    - `<select>`, `<datalist>`, `<optgroup>` 내부에 포함 가능한 컨트롤로 항목을 만드는데 사용됨.

    - [속성]
      - value
      - selected
      - label
      - disabled

    - [사용 예시]
    ```html
      <label for="user_hobby">취미</label>
      <select name="user_hobby" id="user_hobby" required>
        <option value="0">없음</option>
        <option value="1" selected>축구</option>
        <option value="2" label="basketball" disabled>농구</option>
        <option value="3">독서</option>
        <option value="3">영화관람</option>
      </select>
    ```
  - `<optgroup>`
    - `<option>` 컨트를을 그룹지을 때 사용됨.

    - [속성]
      - disabled
      - label

    - [사용 예시]
    ```html
      <p>
        <label for="user_hobby">취미</label>
        <select name="user_hobby" id="user_hobby" required>
          <option value="0">없음</option>
          <optgroup label="구기종목">
            <option value="1" selected>축구</option>
            <option value="2" label="basketball" disabled>농구</option>
          </optgroup>
          <optgroup label="문화생활" disabled>
            <option value="3">독서</option>
            <option value="3">영화관람</option>
          </optgroup>
        </select>
      </p>
    ```

  - `<textarea>`
    - 멀티라인 일반 텍스트 편집 컨트롤을 말한다.

    - [속성]
      - name
      - placeholder
      - rows
      - cols
      - readonly
      - required
      - disabled
      - minlength
      - maxlength

    - [사용 예시]
    ```html
      <div>
        <label for="user_comments">코멘트</label>
        <p>
          <textarea name="user_comments" id="user_comments" cols="24" rows="5">남기고 싶은 말을 작성해주세요.</textarea>
        </p>
      </div>
    ```

  - `<fieldset>`
    - 하나 이상의 폼 컨트롤을 그룹화 하는데 사용됨.

    - [속성]
      - name
      - disabled

    - [사용 예시]
    ```html
      <fieldset name="user_acount">
        ...
      </fieldset>
    ```
  - `<legend>`
    - `<fieldset>` 컨트롤의 레이블(이름)을 설정하는 컨트롤.

    - [사용 예시]
    ```html
      <fieldset name="user_acount">
        <legend>사용자 계정</legend>
      </fieldset>
    ```

  - `<output>`
    - 계산된 결과를 출력하는 컨트롤.

    - [속성]
      - name
      - for

    - [사용 예시]
    ```html
      <form oninput="result_sum.value = parseInt(n1.value + n2.value, 10)">
        <p>
          <input type="number" name="n1" value="4"> +
          <input type="number" name="n2" value="10"> =
          <output name="result_sum">14</output>
        </p>
      </form>
    ```

  - `<datalist>`
    - 데이터 목록 요소 컨테이너 컨트롤.
    - 내부에 `<option>` 요소를 사용해 항목을 만든다.

      - [사용 예시]
      ```html
        <label>이동할 웹주소 <input list="url_ex" type="url" name="user_url" id="user_url"></label>
        <datalist id="url_ex">
          <option value="http://naver.com">naver</option>
          <option value="http://nate.com">nate</option>
          <option value="http://google.com">google</option>
          <option value="http://goo.gl">google short url</option>
        </datalist>
      ```
   - `<progress>`
    - 작업의 완료 진행 상황을 표시하는데 사용되는 컨트롤.

    - [속성]
      - value
      - max

    - [사용 예시]
    ```html
      <progress value="10" max="100">10%</progress>
    ```

  - `<meter>`
    - 알려진 범위 내에서의 스칼라 측정 또는 분포 비율을 나타내는 컨트롤. (게이지(gauge)라고도 불림)
    - 디스크 사용 현황, 쿼리 결과의 관련성, 특정 후보에 대한 투표율 등이 해당됨.

    [속성]
      - value
      - min
      - max
      - low
      - high
      - optimum

    - [사용 예시]
    ```html
    <meter value="20" min="5" max="40">20</meter>
    ```
- table
    - `<table>` 요소
      - 테이블 몸체에 해당되며, 행(row)/열(column) 및 셀(cell)을 포함한다.
      - 복잡한 내용을 x, y축에 따라 이해하기 쉽게 데이터를 구조화하는데 테이블을 사용한다.
      - 가장 좋은 테이블 디자인은 최대한 단순하게 표를 구성하는 것이다.
      - 테이블 내 테이블을 중첩해서는 안된다.
      - 테이블을 레이아웃(배치) 목적으로 사용해서는 안된다.
      - border 속성을 사용해 테두리를 그릴 수 있다. (CSS로 대체하는 것이 좋다)

    - `<caption>` 요소
      - 테이블의 제목을 명시적으로 제공하며, 제작자는 표의 내용을 이해할 수 있도록 정보를 제공해야 함.
      - 테이블 내용이 복잡해 설명이 필요하다면 아래 나열된 방법 중 하나를 선택해 기술해야 한다.

      - [설명(summary)을 추가하는 방법]
        1. aria-describedby 속성을 사용해 설명 단락(paragraph)을 연결
        2. `<figure>` 요소에 aria-labelledby 속성을 사용해 제목(caption)을 연결

    - `<tr>` 요소
      - 테이블의 행(row)을 말하며 내부에 셀 제목(header), 셀 내용(data)을 포함한다.

    - `<th>` 요소
      - 테이블 셀 제목(header cell in a table)으로 행(tr) 내부에 포함되어야 한다.

        - [속성]
         - scope: 행(row) 또는 열(col), 행그룹(rowgroup), 열그룹(colgroup)의 제목임을 명시
         - abbr: 제목이 길어 축약(Abbreviation)이 필요할 때 사용
         - colspan: 열(column)을 그룹 지을 때 사용
         - rowspan: 행(row)을 그룹 지을 때 사용

    - `<td>` 요소
      - 테이블 셀 내용(data cell in a table)으로 행(tr) 내부에 포함되어야 한다.

        - [속성]
         - colspan: 열(column)을 그룹 지을 때 사용
         - rowspan: 행(row)을 그룹 지을 때 사용
         - headers: 셀 제목을 하나 이상 연결하여 읽기 용이하도록 구성할 때 사용

    - `<thead>` 요소
      - 테이블 행 블록(row block) 내에 제목 열 그룹(column headers)으로 구성할 경우 사용한다.
      - 선택적(option)으로 사용한다. (필수 아님)

    - `<tbody>` 요소
      - 행 블록 내에 테이블 데이터로 구성할 때 사용한다.
        선택적(option)으로 사용한다. (필수 아님)

    - `<tfoot>` 요소
      - 행 블록 내에 열 요약(column summaries)로 구성할 때 사용한다.
      - 선택적(option)으로 사용한다. (필수 아님)
    
    - `<col>` 요소
      - 테이블 열(column)을 하나 이상 묶고자 할 때 사용한다.
      - 일반적으로 colgroup 요소 내부에 포함시킨다.
      - 선택적(option)으로 사용한다. (필수 아님)

      - [속성]
        - span: 열 묶음 개수 설정

    - `<colgroup>` 요소
      - 테이블 열(column) 그룹을 만들고자 할 때 사용한다.
      - 내부에 col 요소를 포함하거나, 포함하지 않을 수 있다.
      - 선택적(option)으로 사용한다. (필수 아님)

      - [속성]
        - span: colgroup 요소가 col을 포함하지 않을 경우, 열 묶음 개수 설정
