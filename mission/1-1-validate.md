1. [Error] Stray start tag `html`.
    - From line 4, column 7; to line 4, column 12
    
    ```html
    o">↩<head><html>↩↩↩
    ```

2. [Warning] The `charset` attribute on the `script` element is obsolete.
    - From line 29, column 5; to line 29, column 131
    
    ```html
    " />↩↩    <script charset="UTF-8" class="daum_roughmap_loader_script" src="https://spi.maps.daum.net/imap/map_js_init/roughmapLoader.js"></script>
    ```

3. [Warning] The `type` attribute is unnecessary for JavaScript resources.
    - From line 32, column 1; to line 32, column 86

    ```html
    <script src="/static/js/kakaobankWeb-lib-1521081376857.min.js" type="text/javascript"></script>
    ```

4. [Warning] The `type` attribute is unnecessary for JavaScript resources.
    - From line 36, column 1; to line 36, column 92

    ```html
    <script src="/static/js/kakaobankWeb-resources-1521081376857.min.js" type="text/javascript"></script>
    ```

5. [Error] Stray end tag `head`.
    - From line 44, column 8; to line 44, column 14

    ```html
    >↩↩</html></head>↩↩<bod
    ```

6. [Error] Stray end tag `head`.
    - From line 44, column 8; to line 44, column 14

    ```html
    >↩↩</html></head>↩↩<bod
    ```

7. [Error] Start tag body seen but an element of the same type was already open.
    - From line 46, column 1; to line 46, column 105

    ```html
    ></head>↩↩<body data-browser="unknown" data-os="unknown" data-browser-major="Unknown" data-browser-minor="Unknown">↩<div 
    ```

8. [Fatal Error] Cannot recover after last error. Any further errors will be ignored.
    - From line 46, column 1; to line 46, column 105

    ```html
    ></head>↩↩<body data-browser="unknown" data-os="unknown" data-browser-major="Unknown" data-browser-minor="Unknown">↩<div 
    ```
* line 4의 `html` 여는 tag와 line 44 `html` 닫는 tag 삭제