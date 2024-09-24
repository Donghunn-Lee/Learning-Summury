## 6. link & script

### `<link>` 태그
외부에 있는 리소스를 불러올 때 사용하는 태그. 불러오는 목적은 `rel` 속성에, 위치는 `href` 속성에 적음. 주로 `<head>` 태그 안에서 맨 마지막에 사용.

- **CSS 파일을 불러올 때**:
  ```html
  <head>
    ...
    <link rel="stylesheet" href="style.css">
  </head>
  ```

- **사이트 아이콘을 불러올 때**:
  ```html
  <head>
    ...
    <link rel="icon" href="favicon.ico">
  </head>
  ```

### `<script>` 태그
자바스크립트 파일을 불러올 때 사용하는 태그. 파일의 위치는 `src` 속성에 적음. 주로 `<body>` 태그 안에서 맨 마지막에 작성. 종료 태그 `</script>`를 반드시 써야 함.

```html
<body>
  ...
  <script src="like.js"></script>
</body>
```
