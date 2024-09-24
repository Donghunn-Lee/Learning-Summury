## 2. DOM 조작 및 스타일 다루기

### 1. `window` 객체
- `window` 객체는 브라우저 창을 대변하며, 자바스크립트에서 최상단에 존재하는 전역 객체(Global Object).
- 자바스크립트 코드에서 언제든지 접근할 수 있으며, `window.`는 생략 가능.

### 2. DOM(Document Object Model)
- DOM은 HTML 문서를 객체로 표현한 것으로, 웹 페이지의 구조를 반영하여 각 객체를 **노드(Node)**라고 부름.
- 태그는 **요소 노드(Element Node)**, 문자는 **텍스트 노드(Text Node)**로 구분.

### 3. DOM 트리
- HTML의 계층 구조를 반영한 DOM 트리는 부모, 자식, 형제 간의 관계를 나타냄.
  
### 4. DOM 이동 시 활용 가능한 프로퍼티

| 프로퍼티                     | 유형         | 결과                                     |
|------------------------------|--------------|------------------------------------------|
| `element.children`            | 자식 요소 노드 | 자식 요소 모음(HTMLCollection)            |
| `element.firstElementChild`   | 자식 요소 노드 | 첫 번째 자식 요소                         |
| `element.lastElementChild`    | 자식 요소 노드 | 마지막 자식 요소                         |
| `element.parentElement`       | 부모 요소 노드 | 부모 요소                                 |
| `element.previousElementSibling`| 형제 요소 노드 | 이전 형제 요소                            |
| `element.nextElementSibling`  | 형제 요소 노드 | 다음 형제 요소                           |
| `node.childNodes`             | 자식 노드    | 자식 노드 모음(NodeList)                 |
| `node.firstChild`             | 자식 노드    | 첫 번째 자식 노드                        |
| `node.lastChild`              | 자식 노드    | 마지막 자식 노드                         |
| `node.parentNode`             | 부모 노드    | 부모 노드                                 |
| `node.previousSibling`        | 형제 노드    | 이전 형제 노드                           |
| `node.nextSibling`            | 형제 노드    | 다음 형제 노드                           |

### 5. 주요 요소 노드 프로퍼티

| 프로퍼티              | 내용                                | 참고사항                                     |
|-----------------------|-------------------------------------|----------------------------------------------|
| `element.innerHTML`    | 요소 내부의 HTML 코드 문자열로 리턴 | 요소 내부 HTML 수정에 자주 활용               |
| `element.outerHTML`    | 요소 자체의 전체 HTML 코드 리턴     | 할당 시 요소 자체가 교체되므로 주의           |
| `element.textContent`  | HTML을 제외한 텍스트만 리턴         | HTML 태그도 텍스트로 처리                     |

### 6. 요소 노드 다루기

- 요소 노드 만들기: `document.createElement('태그이름')`
- 요소 노드 꾸미기: `element.textContent`, `element.innerHTML`
- 요소 노드 추가/이동: `element.prepend`, `element.append`, `element.after`, `element.before`
- 요소 노드 삭제: `element.remove()`

### 7. HTML 속성 다루기

- 표준 HTML 속성은 DOM 객체의 프로퍼티로 변환됨. 표준이 아닌 속성은 아래 메소드로 처리 가능:
    - 속성 접근: `element.getAttribute('속성')`
    - 속성 추가/수정: `element.setAttribute('속성', '값')`
    - 속성 제거: `element.removeAttribute('속성')`

### 8. 스타일 다루기

- 스타일 다루는 방법:
    - **`style` 프로퍼티 사용**: `element.style.styleName = 'value';`
    - **클래스 변경**: `element.className`, `element.classList`

### 8-1. `classList`의 유용한 메소드

| 메소드              | 내용                                       | 참고사항                                             |
|---------------------|--------------------------------------------|------------------------------------------------------|
| `classList.add`      | 클래스 추가                                | 여러 값을 전달하여 여러 클래스 추가 가능             |
| `classList.remove`   | 클래스 삭제                                | 여러 값을 전달하여 여러 클래스 삭제 가능             |
| `classList.toggle`   | 클래스 없으면 추가, 있으면 삭제            | 두 번째 파라미터로 추가/삭제 기능 강제 가능           |
