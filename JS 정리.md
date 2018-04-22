```JavaScript
// ---------------------------------------------
// JavaScript 변수 이름 작성 규칙
// ---------------------------------------------

// JavaScript 변수 이름은 식별자(identifier)입니다.
// 식별자는 문자, 밑줄(_) 혹은 달러 기호($)로 시작해야
// 하는 반면 이후는 숫자(0-9)일 수도 있습니다. 대소문자를
// 구분하기에, 문자는 A부터 Z(대문자)와 a부터 z(소문자)까지
// 모두 포함합니다.

// [변수 이름 작성 오류가 발생하는 예]

// [1] 숫자로 시작하는 경우

// [2] 밑줄(_), 달러 기호($)가 아닌,
//     다른 특수 문자 또는 공백이 사용된 경우







// ---------------------------------------------
// JavaScript 데이터 유형(Types)
// ---------------------------------------------

// 최신 ECMAScript 표준은 7가지 데이터 유형을 정의합니다.

// 6가지 원시 데이터(Primitive Data) 유형
// - null
// - undefined
// - number
// - string
// - boolean
// - symbol (ES6+)

// 그리고 객체(Object) 데이터 유형
// 객체 (일반 객체, 배열 객체, 함수 객체)
// - function object
// - array object
// - object

// 객체 생성이란?
// new 생성자 함수()

// 첫글자는 대문자로!!!

new Function()

new Array()

new Object()


// ---------------------------------------------
// JavaScript 리터럴(Literal)
// ---------------------------------------------

// JavaScript에서 값을 나타내기 위해 리터럴을 사용합니다.
// 이는 말 그대로 스크립트에 부여한 고정값으로, 변수가 아닙니다.

// - number   리터럴
// - string   리터럴
// - boolean  리터럴
// - array    리터럴
// - function 리터럴
// - object   리터럴

// 6가지 - 원시 데이터 유형
// 1가지 - 객체 데이터 유형

// 숫자, 문자, 불리언 객체....

90; // 원시 데이터 값

var n = new Number(90); // 숫자 객체 생성
n.valueOf(); // 90

// 숫자 90을 쓰기위해서 위와 같이 사용한다면 번거롭기 때문에
// 자바스크립트에서 편의를 위해 허용해주는 것이다.

new String('hello world').valueOf();
new Boolean(false).valueOf();

// function
var fn;

// 1번 방법
fn = new Function();

// 2번 방법 - 이걸 권장함
fn = function(){

};

// array

// 1번 방법
var arr = new Array();
arr

// 2번 방법 - 이걸 권장함
var arr = [];
arr

// object

// 1번 방법
var obj  = new Object();

// 2번 방법 - 이걸 권장함
obj = {};


// 여러가지 변수 할당 방법

// 길게 쓰는 방법
var num = 9, str = 'nine', boo = true, fun = function () { }, arr = [], obj = {};

// 싱글 바 패턴
var num = 9,
    str = 'nine',
    boo = true,
    fun = function(){},
    arr = [],
    obj = {};

// 일반적인 작성법
var num = 9;
var str = 'nine';
var boo = true;
var fun = function () { };
var arr = [];
var obj = {};


// ---------------------------------------------
// JavaScript 데이터 유형 변환
// ---------------------------------------------

// JavaScript는 동적 형지정 언어입니다. 이는 변수를
// 선언할 때 데이터 형을 지정할 필요가 없음을 의미합니다.
// 또한 데이터 형이 스크립트 실행 도중 필요에 의해 자동으로
// 변환됨을 뜻합니다.

// 선언된 변수의 값 유형이 변경되더라도 문제가 발생하지 않음.

// 자동으로 값이 변경되는 경우.

// - 숫자 값이 문자로 변경되는 경우
//   = String(숫자) // 권장
//   = 숫자 + ''  // 문자로 자동 형 변환

// - 숫자형 문자 값이 숫자로 변경되는 경우
//   = Number(숫자형 문자)  // 권장
//   = +숫자형 문자   // 숫자로 변형
//   = 숫자형 문자 - 0  // 숫자로 자동 형 변환
//   = 숫자형 문자 * 1  // 숫자로 자동 형 변환
//   = 숫자형 문자 / 1  // 숫자로 자동 형 변환

// - 문자 값을 숫자로 변경해야 하는 경우
//   = window.parseInt(문자,10) // 10은 10진수
//   = window.parseFloat(문자,10)

var img_width = '100px';
img_width
window.parseInt(img_width,10);

var img_width = '100.01px';
img_width
window.parseFloat(img_width, 10);


// - 불리언 값으로 변경되는 경우
//   = Boolean(데이터유형)
//   = !!데이터유형  - 권장

var n = 9, 
    s = '70px',
    f = function(){},
    a = [3,4,6],
    o = {};

0 == false              // true
Boolean(null)           // false
Boolean(undefined)      // false
Boolean('')             // false
Boolean(' ')            // true

0, '', null, undefined  // false

// null, false 는 0으로 자동 형변환된다.
// 하지만 undefinded는 변하지 않으므로 주의하자


// ---------------------------------------------
// 동적 형 지정 언어 사용 시, 고민할 점.
// ---------------------------------------------

// 인터프리터 유형의 언어는 실행 도중에 변수에 예상치 못한
// 타입(type)이 들어와 Type Error 를 뿜는 경우가
// 생길 수 있습니다.

// 이러한 고민에 대한 해결책으로 TypeScript를 사용하기도 합니다.
// 우리 수업의 주제는 아니지만, 정적 형 지정 언어에 대해 살펴볼 때
// JavaScript로 변환되는 TypeScript는 좋은 예입니다.

// https://www.typescriptlang.org/play/

// 동일한 변수 이름 문제
// JavaScript는 동적 형지정 언어이므로 변수의 데이터 유형은 실행 중에 변경될 수 있습니다.
// 그러한 이유로 문서 객체의 ID 속성 값을 통해 문서 객체를 선택해서는 안됩니다.
// 이유는 영상 강의를 통해 확인해보세요.

// Developer 1

// console.log(body);

boy.style.transform = 'scale(0.5)';


// Developer 2

// 실행시 var boy는 최상위로 이동된다.
var boy = '야망이 넘치는 소년의 눈빛';

console.log(boy);


/*

var boy;   // undefined
 
// Developer 1

// console.log(body);

undefined.style.transform = 'scale(0.5)';


// Developer 2

boy = '야망이 넘치는 소년의 눈빛';

console.log(boy);

*/

// 그러므로 id 값을 통해 선택해서는 안된다.!!!!!!!!!!!
```
* DOM API
    - 문서 객체(Document Objects)를 선택하는 방법
    - 요소노드(ELEMENT_NODE) `||` HTMLCollection vs **노드리스트(NodeList)** 
    1. tagName 으로 선택하는 방법

        - 문서에서 tagName 값이 `[    ]`인 요소들을 찾아라.
            ```javascript
            var figures = document.getElementsByTagName('figure');
            console.log(figures);   // HTMLCollection 집합객체(자료를 모아서 보여주는 것)를 가져옴
            ``` 
        - 각각의 값을 보여줌
            ```javascript
            figures.item(0);
            figures[0];
            ```
        - 문제점 : 그것이 무엇인지 모른다.
        - 이 방법으로는 많이 사용되지 않는다.
            ```javascript
            boy_el.style.transform = 'perspective(800px) rotateY(56deg)';

            var boy = '야망이 넘치는 소년의 손짓';
            // console.log(boy);

            // p kbd {} 요소를 JavaScript에서 선택하는 방법
            var paragraphs = document.getElementsByTagName('p');
            var kbds = paragraphs.item(0).getElementsByTagName('kbd');
            kbds[0].style.color = 'blueviolet';
            ```

    2. id 속성 값으로 선택하는 방법
        - 이런 방법으로 id 속성 값으로 대상을 찾았기 때문에 
        - 올바르게 id값으로 찾은 대상을 처리 할 수 있다.
            ```javascript
            var boy_el = document.getElementById('boy');
            // console.log(boy_el);
            ```

    3. class 속성 값으로 선택하는 방법
        ```javascript
        var clouds = document.getElementsByClassName('cloud');
        // console.log(clouds);
        var kbd = document.getElementsByClassName('info')[0].getElementsByTagName('kbd')[0];
        // console.log(kbd);
        ```
    4. CSS 선택자(selector)로 선택하는 방법 <-- **이제 이걸로 사용하자!!! 모던한 방법**
        ```javascript
        var boy = document.querySelector('#boy');           // 단수 ELEMENT_NODE
        var clouds = document.querySelectorAll('.cloud');   // 복수 NodeList []
        ```
* JavaScript 함수(Function)
    - 미리 정의된 함수들
    - 함수 정의(선언)
    - 함수 표현식
    - 함수 호출
    - 함수 전달인자와 매개변수
    - 함수 결과 반환

    1. 미리 정의된(내장된) 함수들(native/built-in) 
        - 함수는 절차(procedure)
        - 일을 하는 데 거쳐야 하는 일정한 차례와 방법
        - 쉽게 말해 "할 일 묶음"
        - 메서드 : 객체가 소유하고있는 함수
        - DOM / BOM(window, screen, navigator, location, history)
        
        * ※ window 전역 객체(global object)는 **생략 가능**.   
            ```Javascript
            window.parseInt()       // parseInt('90.23px',10)
            window.parseFloat()
            window.alert()          // 경고창
            window.confirm()        // 확인창(true,false) - 예전에 많이 쓰던 것
            window.prompt()         // 입력창 / prompt('최저시급은 얼마?');
            ```
        * ※ console 객체는 **생략 불가능**.
            
            ```Javascript
            console.log()    // 로그
            console.info()   // 인포메이션
            console.warn()   // 경고
            console.error()  // 오류
            ```
    2. 사용자 정의 함수
        - [1.1] 함수 정의(선언)

            ```Javascript
            function 함수이름() {
                // Code block
                // 할 일 목록
                // 절차
            }

            function callMe() {
                console.log('안녕하세요');
                console.log('00입니다.');
                console.log('우리가 지금 공부라는 것은');
                console.log('함수입니다.');
                console.log('다른 이름으로는 \'절차\'라고 불어요');
            }
            // callMe() == window.callMe()
            ```

            * 장보기(쇼핑) 함수
                - 장 볼 상품의 목록을 작성한다.
                - 목록에 따라 상품을 검색한다.
                - 상품의 상태를 확인한다.
                - 구매할 수량을 입력한다.
                - 장바구니에 담는다.
                - 장바구니에 담긴 항목을 확인한다.
                - 결재한다.

            ```Javascript
            function shopping() {
                console.log('장 볼 상품의 목록을 작성한다.')
                console.log('목록에 따라 상품을 검색한다.')
                console.log('상품의 상태를 확인한다.')
                console.log('구매할 수량을 입력한다.')
                console.log('장바구니에 담는다.')
                console.log('장바구니에 담긴 항목을 확인한다.')
                console.log('결재한다.')
            }
            // shopping : function shopping()을 가리키는 역할
            ```
            
        - [1.2] 함수 표현식(Function Expression)
            ```Javascript
            var shopping = function () {
                console.log('장 볼 상품의 목록을 작성한다.')
                console.log('목록에 따라 상품을 검색한다.')
                console.log('상품의 상태를 확인한다.')
                console.log('구매할 수량을 입력한다.')
                console.log('장바구니에 담는다.')
                console.log('장바구니에 담긴 항목을 확인한다.')
                console.log('결재한다.')
            }
            ```
        - [2] 함수 호출
            - 선언된 함수 이름 또는 함수 값을 참조하는 변수 이름을 호출()
            - 함수는 재사용을 목표로 함
            ```Javascript
            callMe();
            shopping();
            shopping();
            shopping();
            shopping();
            shopping();
            ```
        - [3] 함수 전달인자(arguments)와 매개변수(parameters)
            ```Javascript
            // Excel sum(n1, n2)
            function sum(n1, n2) {  // 매개변수
                // var n1 = 909;
                // var n2 = -1023;
                // 전달된 두 수의 합을 처리하여 결과를 사용자에게 제공한다.
                // console.log(n1, n2);
                console.log(n1 + n2);

            }

            sum(909, -1023); // 전달인자
            sum(9, 153);
            sum(99, -3);
            sum(10203, -923);

            var r1 = sum(909, -1023);
            var r2 = sum(9, 153);
            var r3 = sum(99, -3);
            var r4 = sum(10203, -923);
            // 결과 : undefined / 이유 : 함수는 전달받은 값을 가지고 합한다고 했지만 결과를 반환하지 않아서
            ```

        - [4] 함수 결과 반환(return)
            ```Javascript
            function sum(n1, n2) {  // 매개변수
                // var n1 = 909;
                // var n2 = -1023;
                // 전달된 두 수의 합을 처리하여 결과를 사용자에게 제공한다.
                // console.log(n1, n2);
                return n1 + n2;
            }

            var sum = function (n1, n2) {  // 매개변수
                // var n1 = 909;
                // var n2 = -1023;
                // 전달된 두 수의 합을 처리하여 결과를 사용자에게 제공한다.
                // console.log(n1, n2);
                return n1 + n2;
            }
            ```

            * 결과 값을 요구할 때
                - return 사용 (get)
            * 결과 값을 요구하지 않을 때
                - return 미사용 (set)

            
            - 재사용을 목적으로 하는 '쓸모있는' 함수 만들기

                - 기본적인 방식
                ```Javascript
                var all_elms = document.querySelectorAll('*');
                var figures  = document.querySelectorAll('figure');
                var clouds   = document.querySelectorAll('.cloud');
                var boy      = document.querySelector('#boy');
                var info     = document.querySelector('.info');
                var kbd      = info.querySelector('kbd');
                ```
                - 함수를 이용한 방식
                ```Javascript
                // list, els, $$
                function list(selector) {
                    return document.querySelectorAll(selector);
                }

                // el, $
                var el = function(selector, context) {  // 선택자, 범위
                    // 조건문 (condition)
                    if(!context) {
                        context = document;
                    }
                    return context.querySelector(selector);
                }

                var all_elms = list('*');
                var figures  = list('figure');
                var clouds   = list('.cloud');
                var boy      = el('#boy');
                var info     = el('.info');
                var kbd      = el('kbd', info);
                var kbds     = list('kbd');
                ```


* 조건문 (Condition Statement)
    - 특정 조건이 참(true)인 경우 실행하는 명령의 집합
    - `!!` / `!`
    ```Javascript
    var condition = true;

    if(condition == true) {
        // code block
        console.log('condition is TRUE');
    } else {
        console.log('condition is not TRUE');
    }
    ```
* if ~ else 문
    - 특정 조건이 참인 경우 문장을 실행하기 위해 if 문을 사용합니다.
    - 또한 선택적으로 조건이 거짓인 경우 문장을 실행하기 위해서는
    - else 절을 사용합니다.
    - 거짓(false)으로 판단하는 값
        - `false`
        - `undefined`
        - `null`
        - `0`
        - `NaN`
        - `''`
    ```Javascript
    if (false) {
        console.log('this is true');
    } else {
        console.log('this isn\'t true');
    }

    if (0) {
        console.log('this is true');
    } else {
        console.log('this isn\'t true');
    }

    if (undefined) {
        console.log('this is true');
    } else {
        console.log('this isn\'t true');
    }

    if (null) {
        console.log('this is true');
    } else {
        console.log('this isn\'t true');
    }

    if ('') {
        console.log('this is true');
    } else {
        console.log('this isn\'t true');
    }

    if (' ') {
        console.log('this is true');
    } else {
        console.log('this isn\'t true');
    }

    // el('strong'), el('p')

    el('strong')

    if (el('strong')) {
        console.log('this document has strong element');
    } else {
        console.log('this document has not strong element');
    }

    if (el('p')) {
        console.log('this document has p element');
    } else {
        console.log('this document has not p element');
    }

    function el(selector, context) {  // 선택자, 범위
        // if ( context 값이 거짓이면 ){
        //      context 값을 document로 설정하라
        // }
        if (!context) {
            context = document;
        }
        return context.querySelector(selector);
    }

    // el('p')  // p, undefined
    ```
* 비교 연산자
    - `==`
    - `=== (권장)`
    - `!=`
    - `!== (권장)`
    - `>`
    - `>=`
    - `<`
    - `<=`
    
    ```Javascript
    if (10 == '10') {    // 참
        console.log('10과 문자열 10은 같다.');
    }

    // 자바스크립트가 자동으로 유형을 변경하기 때문에

    if (10 === '10') {    // 거짓
        console.log('10과 문자열 10은 같다.');
    }

    if (10 !== '10') {    // 참
        console.log('10과 문자열 10은 같다.');
    }

    if (0 > 10) {    // 거짓
        console.log('true');
    }

    if (0 < 10) {    // 참
        console.log('true');
    }

    if (10 >= 10) {    // 참
        console.log('true');
    }

    if (10 < 10) {    // 거짓
        console.log('true');
    }

    if (10 > 10) {    // 거짓
        console.log('true');
    }
    if (10 >= 10) {    // 참
        console.log('true');
    }
    ```

    - `ex)` 비교 연산자
        - `A === B`
        - `A !== B`
        - `A > B`
        - `A >= B`
        - `A < B`
        - `A <= B`

* 논리 연산자
    - `AND ⟹ &&`
    - `OR  ⟹ ||`
    - `NOT ⟹ !`

    - 사용자가 어떻게 쓸지 모르기 때문에 모두 방어적으로 대응하기위해 <br>
    내부적으로 생기는 오류를 문제가 생기지 않게 만들어야함.
    ```Javascript
    function els(selector, context) {
        // selector 유형이 문자가 아니거나, selector 공백을 제거한 길이가 0일 경우 결과 값 null 반환
        if (typeof selector !== 'string' || selector.trim().length === 0) { return null; }
        // context 값이 존재하고, 노드 유형이 요소 노드(1)가 아니라면... context 변수에 el() 함수를 통해 문서 객체 참조.
        if (context && context.nodeType !== document.ELEMENT_NODE) { context = el(String(context)); }
        // context 값이 undefined, null 일 경우, context는 document 값을 참조.
        if (!context) { context = document; }
        return context.querySelectorAll(selector);
    }

    function el(selector, context) {
        if (typeof selector !== 'string' || selector.trim().length === 0) { return null; }
        if (context && context.nodeType !== document.ELEMENT_NODE) { context = el(String(context)); }
        if (!context) { context = document; }
        return context.querySelector(selector);
    }


    el()
    el('')
    el(' ')
    el(document)
    el('body', 'html')
    el('figure', '.container')
    els('figure', '.container')
    els('figure', '.wrap')
    els('figure', el('.wrap'))
    ```
* `typeof` : 데이터 유형을 확인할 수 있음
    ```JavaScript
    typeof 9                    // number
    typeof '0'                  // string
    typeof false                // boolean
    typeof function () { }      // function
    typeof object               // undefined
    typeof {}                   // object
    typeof []                   // object
    // 배열은 아래와 같이 써야 확인 가능
    Array.isArray([])           // true
    Array.isArray({})           // false
    typeof null                 // object
    ```
    - typeof 는 JavaScript 데이터 유형이 무엇인지 문자열(소문자)로 변환한다.
    - 단, null 또는 Array(배열)는 올바른 값을 변환하지 못한다. ('object' 문자열 변환)

* `trim()` : 양쪽에 공백이 있는 경우 제거
    ```JavaScript
    '   hi there    '.trimLeft()    // 'hi there    '
    '   hi there    '.trimRight()   // '   hi there'
    '   hi there    '.trim()        // 'hi there'
    '   '.trim().length             // 0 / ''.length
    ' a '.trim().length             // 1 / 'a'.length
    ```

* `document.ELEMENT_NODE`
    ```JavaScript
    document.ELEMENT_NODE                               // ELEMENT_NODE : 상수 / 숫자 1을 반환
    // const : 상수 선언
    const bin = '미스터 빈'
    bin = '소크라테스'      // 에러

    // DOM <- Node Type : ELEMENT / ATTRIBUTE / TEXT / COMMENT / DOCUMENT
    document.body.nodeType                              // 1
    document.body.nodeType === document.ELEMENT_NODE    // true
    document.nodeType === document.ELEMENT_NODE         // false
    document.nodeType === document.DOCUMENT_NODE        // true
    document.DOCUMENT_NODE                              // 9
    document.ELEMENT_NODE                               // 1
    ```
