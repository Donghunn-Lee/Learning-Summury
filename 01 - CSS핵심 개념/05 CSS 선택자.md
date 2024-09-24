## 5. CSS 선택자 (CSS Selector)

### CSS 선택자(CSS Selector)
CSS 규칙에서 맨 앞에 적어주는 걸 CSS 선택자라고 부름. 선택자를 사용해서 이 규칙을 어떤 요소들에 적용할지 선택할 수 있음.

```css
선택자 {
  선언;
  선언;
  선언;
}
```

### 선택자 목록
콤마(,)로 선택자를 연결하면 여러 선택자에 같은 규칙을 적용할 수 있음.

```css
선택자1,
선택자2 {
  ...
}
```

### 선택자 붙여 쓰기
여러 조건을 동시에 만족하는 요소를 선택하고 싶다면 선택자를 붙여서 쓸 수 있음. 예를 들어, 아래 HTML 코드에 있는 태그를 선택하는 방법:

```html
<h2 id="mongolia" class="large title">몽골 대자연으로 떠나는 여행</h2> 
```

- **예시 1. 아이디 + 클래스**
  ```css
  #mongolia.title
  ```
  
- **예시 2. 클래스 + 클래스**
  ```css
  .large.title
  ```
  
- **예시 3. 태그 + 아이디 + 클래스**
  ```css
  h2#mongolia.large.title
  ```

### 자식 결합자 (Child Combinator)
오른쪽 꺾쇠로 선택자를 이어 줌. 예를 들어, 아래 코드에서 `tesla-y-2025.png` 이미지를 선택하려면 `.article > img`로 선택할 수 있음.

```html
<div class="article">
  <img src="tesla-y-2025.png">
  ...
</div>

.article > img {
  width: 100%;
}
```

### 자손 결합자 (Descendant Combinator)
스페이스(띄어쓰기)로 선택자를 이어 줌. 예를 들어, 아래 코드에서 `tesla-w-2025.png` 이미지를 선택하려면 `.article img`로 선택할 수 있음.

```html
<div class="article">
    <p> 이번에 리뷰해 볼 차량은 테슬라 모델 W 입니다.
      <img src="tesla-w-2025.png">
  </p>
  ...
</div>

.article img {
  width: 100%;
}
```

### 가상 클래스 (Pseudo-class)
가상 클래스는 의사 클래스, 가짜 클래스라고도 부름. 요소의 상태 같은 걸 선택할 때 사용하는 클래스. 정해진 이름 앞에 콜론(:)을 붙여서 사용. 대표적으로 `:hover`(마우스를 올렸을 때), `:active`(클릭한 상태), `:visited`(방문한 적이 있는 링크), `:focus`(포커싱 됐을 때) 등이 있음. 예를 들어, 밑줄이 없는 링크에 마우스를 올렸을 때 밑줄이 생기도록 하려면 `:hover`를 활용하면 됨.

```css
a {
  text-decoration: none;
}

a:hover {
  text-decoration: underline;
}
```
