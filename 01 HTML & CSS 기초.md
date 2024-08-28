# HTML & CSS 기초

---

## 1. 수업 소개

### 웹사이트 제작 개요
- 웹사이트는 HTML(구조)과 CSS(디자인)을 사용해 만듦.
- HTML과 CSS를 사용해 간단한 웹사이트를 제작하고 이를 실제로 인터넷에 런칭하는 과정.

---

## 2. HTML 기초

### 기본 개념
HTML은 웹페이지의 뼈대를 구성. 제목, 본문, 이미지, 링크 등을 통해 웹페이지의 구조를 잡아감.

### <예시 코드>
      
```html
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <title>나의 첫 웹사이트</title>
</head>
<body>
    <h1>안녕하세요!</h1>
    <p>이것은 나의 첫 웹사이트입니다.</p>
    <a href="https://example.com">예시 링크</a>
    <img src="image.jpg" alt="예시 이미지">
</body>
</html>
```

### 실습: 구독 페이지 제작
- **사이트 이름과 제목 설정:** `<title>` 태그를 사용해 페이지의 제목을 설정.
- **한글 인코딩 문제 해결:** `<meta charset="UTF-8">` 태그를 추가해 한글이 깨지지 않도록 설정.
- **본문과 줄바꿈 추가:** `<p>` 태그로 본문을 작성하고, 줄바꿈은 `<br>` 태그를 사용.
- **특수문자 삽입:** HTML에서 `&lt;`, `&gt;`와 같은 엔티티를 사용해 꺾쇠 기호 등을 삽입.
- **링크와 이미지 추가:** `<a>`와 `<img>` 태그를 사용해 링크와 이미지를 삽입.
- **영역 나누기:** `<div>`, `<section>` 등의 태그를 사용해 페이지를 구역별로 나눔.

---

## 3. CSS 기초

### 기본 개념
- CSS는 HTML로 만든 구조를 꾸미는 역할. 색상, 글꼴, 정렬, 여백 등 시각적인 요소들을 제어.
- 기초 단계에서는 내부, 외부 스타일이 아닌 인라인 스타일(Inline Style) 방식을 사용.

### <예시 코드>

```html
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Roboto&display=swap" rel="stylesheet">
    <title>구독 페이지</title>
</head>
<body style="background-color: #f0f0f0; font-family: Roboto, sans-serif; color: #333;">
    <h1 style="color: #ff6347; text-align: center;">구독을 환영합니다!</h1>
    <p style="font-size: 16px; line-height: 1.5;">이 페이지는 구독을 위한 안내 페이지입니다.</p>
</body>
</html>
```

### 실습: 구독 페이지 스타일링
- **색상 및 배경색:** `background-color`와 `color` 속성을 사용해 페이지의 색상을 설정.
- **글꼴 설정:** `font-family` 속성을 사용해 텍스트에 원하는 글꼴을 적용. 글꼴은 Google Fonts에서 `<link>` 태그를 사용해 웹사이트를 방문한 사용자가 받아올 수 있도록 설정.
- **글자 크기와 정렬:** `font-size`와 `text-align` 속성을 통해 텍스트 크기와 정렬을 조정.
- **여백 및 크기 조정:** `padding`, `margin`, `width` 속성을 사용해 콘텐츠의 여백과 크기를 조절.

---

## 4. 마무리

### 페이지 연결 및 소셜 공유 설정
다양한 페이지를 `<a>` 태그로 연결하고, 오픈그래프를 이용해 소셜 미디어에서의 공유 미리보기를 설정.

### <예시 코드>

```html
<meta property="og:title" content="나의 첫 웹사이트">
<meta property="og:description" content="이 웹사이트는 나의 첫 번째 프로젝트입니다.">
<meta property="og:image" content="image.jpg">
<meta property="og:url" content="https://example.com">
```

### 방문자 추적 및 도메인 설정
Google Analytics를 통해 방문자 수를 추적하고, 맞춤 도메인을 설정해 웹사이트를 더욱 전문적으로 만듦.

### <예시 코드>

```html
<script async src="https://www.googletagmanager.com/gtag/js?id=UA-XXXXX-Y"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'UA-XXXXX-Y');
</script>
```

---
