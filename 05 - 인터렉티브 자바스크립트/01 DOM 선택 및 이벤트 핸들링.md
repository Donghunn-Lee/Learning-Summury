## 1. DOM 선택 및 이벤트 핸들링
### 1. 자바스크립트로 태그 선택하기

| 메소드                                  | 의미                             | 결과                                    |
|------------------------------------------|----------------------------------|-----------------------------------------|
| `document.getElementById('id')`          | HTML id 속성으로 태그 선택하기    | id에 해당하는 태그 하나                |
| `document.getElementsByClassName('class')`| HTML class 속성으로 태그 선택하기 | class에 해당하는 태그 모음(HTMLCollection) |
| `document.getElementsByTagName('tag')`   | HTML 태그 이름으로 태그 선택하기  | tag에 해당하는 태그 모음(HTMLCollection) |
| `document.querySelector('css')`          | CSS 선택자로 태그 선택하기        | CSS 선택자에 해당하는 첫 번째 태그 하나 |
| `document.querySelectorAll('css')`       | CSS 선택자로 태그 선택하기        | CSS 선택자에 해당하는 태그 모음(NodeList) |

### 2. 유사 배열이란?
배열과 유사한 객체로 `HTMLCollection`, `NodeList`, `DOMTokenList` 등이 있음.

#### 특징:
- 숫자 형태로 인덱싱이 가능.
- `length` 프로퍼티가 있음.
- 배열의 기본 메소드를 사용할 수 없음.
- `Array.isArray(유사 배열)`의 리턴값은 `false`.

### 3. 이벤트와 이벤트 핸들링, 그리고 이벤트 핸들러

- **이벤트**: 웹 페이지에서 발생하는 대부분의 사건들 (ex: 버튼 클릭, 스크롤, 키보드 입력 등).
- **이벤트 핸들링**: 자바스크립트를 통해 이벤트를 다루는 일.
- **이벤트 핸들러(Event Handler)**: 이벤트가 발생했을 때 실행되는 구체적인 동작을 표현한 코드. 이벤트 리스너(Event Listener)라고도 부름.

### 4. 이벤트 핸들러를 등록하는 2가지 방법

#### 4-1. 자바스크립트로 DOM 객체의 `onclick` 프로퍼티에 등록

```javascript
const btn = document.querySelector('#myBtn');

btn.onclick = function() {
  console.log('Hello Codeit!');
};
```

#### 4-2. HTML 태그의 `onclick` 속성에 바로 등록

```html
<button id="myBtn" onclick="console.log('Hello Codeit!')">클릭!</button>
```
