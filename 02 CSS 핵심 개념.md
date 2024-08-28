# CSS 핵심 개념

---

## 1. 핵심 개념 소개

### CSS기본 개념
#### CSS 규칙

    선택자 {
      속성: 속성값;
      속성: 속성값;
    }

인라인 스타일 방식보다는 CSS규칙을 미리 정해두는 방법이 권장됨.

#### CSS 선택자
- 규칙에서 요소를 선택하는데 사용하는 부분.
- 태그 이름 : `<h1>`, `<div>`등의 태그에 스타일을 지정하여 해당 태그를 사용한 모든 요소에 스타일을 적용.

      h3 {
        font-size: 24px;  
      }

- 아이디(id) : 맨 앞에 `#`을 붙여서 `#아이디_이름`과 같은 문법으로 사용. 같은 아이디는 한 페이지에서 한 번만 사용할 수 있음.

  
      <h3>우도</h3>
      <h3 id="hallasan">한라산 국립공원</h3>
      <h3>성산 일출봉</h3>
      <h3>군산 오름</h3>
    
      #hallasan {
        color: #f56513;
      }
  
- 클래스(class) : 아이디는 한 요소에만 사용 가능하므로, 여러 요소에 사용하기 위해 `클래스`가 필요함. 맨 앞에 마침표를 붙여 `.클래스_이름`과 같은 문법으로 사용.

#### 색상 단위

- 색상 이름 : `red`, `green`, `yellow`같은 영어명 색상. 세세한 표현이 어려워 많이 사용하지 않음.
- 색상 코드 : 샵(`#`)으로 시작하는 여섯 글자의 16진수 코드. 빨강, 초록, 파랑의 각 0 ~ 255의 값을 두 글자의 16진수로 바꾸어 나열하여 여섯 글자로 표현함.

      #FFFF00

- RGB : 빨강, 초록, 파랑 값을 우리가 평소에 쓰는 10진수로 써서 색상을 나타냄.

      rgb(255, 255, 0)
  
- RGBA : 빨강, 초록, 파랑, 알파 값을 순서대로 써서 색상을 나타냄. 알파값은 0 ~ 1 사이의 소수 값으로, 1에 가까울수록 불투명해지며 0에 가까울수록 투명해짐.

  
      //반투명한 노란색
      rgba(255, 255, 0, 0.5)
  

#### 절대적 크기 단위

- 픽셀 `px` : 화면을 표시하는 기준이 되는 절대적인 단위.

#### 상대적 크기 단위

- 퍼센트 `%` : 부모 태그의 크기에 상대적으로 지정할 때 사용.

      <div id="parent">
        저는 높이가 320px입니다.
        <div id="child">
          저는 높이가 160px이에요!
        </div>
      </div>

      #parent {
        background-color: #A655ED;
        height: 320px;
      }
      
      #child {
        background-color: #6942D6;
        height: 50%;
      }

- em : `em`은 전통적으로 인쇄술에서 대문자 M의 크기를 나타내는 단위. CSS에선 부모 태그의 `font-size`를 의미함.

      <div id="parent">
        저는 16px입니다.
        <div id="child">
          저는 64px이에요!
        </div>
      </div>

      #parent {
        font-size: 16px;
      }
      
      #child {
        font-size: 4em;
      }

- rem : `rem`은 루트(root)em이라는 의미의 단위. 부모가 아닌 최상위 태그 `<html>`의 font-size를 의미함.

      <html>
        <body>
              저는 18px 입니다.
              <div id="other">
            저는 32px이에요!
              </div>
        </body>
      </html>

      html {
        font-size: 16px;
      }
      
      body {
        font-size: 18px;
      }
      
      #other {
        font-size: 2rem;
      }

#### 코멘트 문법
- CSS를 작성하며 코드에 설명을 적고 싶을 때 사용. `/*`로 시작해 `*/`로 끝나는 코드.
- 실행시 아무런 영향을 주지 않음.

      /*
        마켓 CSS
        v1.5.0
      */
      
      /* 찜하기 버튼 */
      .zzim-button {
        font-size: 24px;
        padding: 8px; /* 임시로 정한 값 */
      }


---

## 2. 자주 쓰는 CSS 속성
- 배경 이미지 `background-image` : `url(...)`이라는 문법으로 배경 이미지 삽입. 배경 이미지는 여러 개 넣을 수 있음.

```
background-image: url('flowers.png');
```

### 배경의 위치 `background-position`
- 기본값은 `left top`이며, 가운데 정렬을 위해선 `center`를 사용해야함.

```
background-position: top; /* 위 */
background-position: right; /* 오른쪽 */
background-position: bottom; /* 아래 */
background-position: left; /* 왼쪽 */
background-position: left top; /* 왼쪽 위 (지정하지 않았을 때 기본값) */
background-position: center;
```

### 배경의 반복 `background-repeat`
- 기본값은 `repeat`이며, `no-repeat`으로 반복되지 않게 할 수 있음.

```
background-repeat: repeat; /* 반복하기 (지정하지 않았을 때 기본값) */
background-repeat: no-repeat; /* 반복 안 함 */
```

### 배경의 크기 `background-size`
- 배경 이미지의 크기를 지정할 수 있음. 직접 가로와 세로 크기를 지정하거나, 비율을 유지하면서 영역에 꽉 차게(`cover`), 또는 영역 안에서 최대한 크게(`contain`) 설정 가능.

```
background-size: cover; /* 비율을 유지하면서 영역에 꽉 차게 설정. 이미지가 잘릴 수 있음 */
background-size: contain; /* 비율을 유지하면서 영역 안에서 최대한 크게 설정. 이미지가 잘리지 않음 */
background-size: 40px 30px; /* 가로 40px, 세로 30px로 설정 */
```

### 그라디언트 `linear-gradient()`
- 색상이 점차적으로 변하는 효과를 줄 수 있음. 기본적으로 시작 색상과 종료 색상을 사용하며, 각도를 지정하여 그라디언트의 방향을 설정할 수 있습니다. 각도의 단위는 `deg`를 사용.

```
background-image: linear-gradient(#000000, #ffffff); /* 기본 각도 (위에서 아래로)로 설정된 그라디언트 */
background-image: linear-gradient(45deg, rgba(0, 0, 0, 0.8), rgba(0, 0, 0, 0.2)); /* 45도 각도의 그라디언트 */
```

### 그림자 `box-shadow`
- 요소에 그림자를 추가할 수 있음. 그림자의 가로, 세로 위치, 흐린 정도(Blur), 퍼지는 정도(Spread), 그리고 색상을 순서대로 지정.

```
box-shadow: 5px 10px 15px 8px rgba(0, 0, 0, 0.6);
/*
  가로 위치: 5px
  세로 위치: 10px
  흐린 정도(Blur): 15px
  퍼지는 정도(Spread): 8px
  색상: rgba(0, 0, 0, 0.6)
*/
```

### 불투명도 `opacity`
- 요소의 전체 불투명도를 조절. 0에서 1 사이의 소수 값으로 단위 없이 사용.

```
opacity: 0; /* 투명 */
opacity: 0.6; /* 반투명 */
opacity: 1; /* 불투명 */
```

## 3. 박스 모델 (Box Model)

### 박스 모델(Box Model)
HTML/CSS에서 요소는 기본적으로 박스 형태. 박스는 바깥에서부터 차례대로 바깥 여백인 마진, 테두리인 보더, 테두리와 실제 내용 사이의 여백인 패딩, 그리고 실제 내용이 들어가는 콘텐트 박스로 구성됨.

### `border` 속성
주로 굵기, 테두리 종류, 색상 순서로 사용. 예를 들어, 아래 코드는 2px 굵기의 실선으로 옅은 회색(#ededed)을 사용하는 코드.

```
border: 2px solid #ededed;
```

### `border-radius` 속성
박스 모델의 모서리를 둥글게 만들 때 사용. `border` 속성 없이도 사용할 수 있음. 아래 코드는 16px만큼 둥글게 하는 코드.

```
border-radius: 16px;
```

#### 팁 1. 타원 만들기
아래 코드는 50%만큼 둥글게 하는 코드. 이렇게 하면 타원 형태가 됨.

```
border-radius: 50%;
```

#### 팁 2. 알약 만들기
아래 코드는 9999px만큼 둥글게 하는 코드. 이렇게 아주 큰 값을 지정하면 알약 형태가 됨.

```
border-radius: 9999px;
```

### `box-sizing` 속성
기본적으로 요소에 크기를 지정하면 그 크기는 박스 모델에서 콘텐트 영역에 대한 크기. 예를 들어서 아래 #box 요소의 실제 너비는 100 + 30 + 30 = 160이 됨.

```css
#box {
  margin: 20px;
  padding: 30px;
  width: 100px;
}
```

좀 더 직관적으로 크기를 지정하고 싶다면, `box-sizing` 속성을 바꿔주면 됨. 기본 값인 `content-box` 대신에 `border-box`를 사용하면 됨.

```css
#box {
  margin: 20px;
  padding: 30px;
  width: 100px;
  box-sizing: border-box;
}
```

이렇게 하면 테두리까지 모두 합친 영역의 크기가 100px이 됨.

### `overflow` 속성
박스의 크기를 지정했을 때 가끔 안에 있는 내용이 많아서 삐져나올 때가 있음. 이런 걸 오버플로우라고 하는데, 이때 박스에 스크롤이 되도록 하거나 삐져나온 내용을 감출 수 있음.

#### 예시 1. 넘치는 것 감추기

```css
overflow: hidden;
```

```html
<div class="card">
    애플 수박은 생긴 건 수박이지만 사과처럼 작고 껍질이 얇은 과일이다. 대한민국 경북 문경에서 박인규씨가 처음으로 재배하기 시작했고 전국적으로 퍼지기 시작했다. 무게는 1kg 정도로 한 손으로 들어 올릴 수 있다. 먹기는 수박보다 편하지만 맛은 일반 수박에 비해 못한 편이라고 한다. 일반 수박에 비해서 덜 아삭하고 마치 멜론같은 식감이 난다.
</div>
```

#### 예시 2. 넘치면 스크롤 하게 만들기

```css
overflow: auto;
```

```html
<div class="card">
    애플 수박은 생긴 건 수박이지만 사과처럼 작고 껍질이 얇은 과일이다. 대한민국 경북 문경에서 박인규씨가 처음으로 재배하기 시작했고 전국적으로 퍼지기 시작했다. 무게는 1kg 정도로 한 손으로 들어 올릴 수 있다. 먹기는 수박보다 편하지만 맛은 일반 수박에 비해 못한 편이라고 한다. 일반 수박에 비해서 덜 아삭하고 마치 멜론같은 식감이 난다.
</div>
```

#### 예시 3. 항상 스크롤 하게 만들기

```css
overflow: scroll;
```

```html
<div class="card">
    애플 수박은 생긴 건 수박이지만 사과처럼 작고 껍질이 얇은 과일이다. 대한민국 경북 문경에서 박인규씨가 처음으로 재배하기 시작했고 전국적으로 퍼지기 시작했다. 무게는 1kg 정도로 한 손으로 들어 올릴 수 있다. 먹기는 수박보다 편하지만 맛은 일반 수박에 비해 못한 편이라고 한다. 일반 수박에 비해서 덜 아삭하고 마치 멜론같은 식감이 난다.
</div>
```

### 마진 상쇄 (Margin Collapsing)
일반적으로 세로 마진은 서로 겹쳐서 화면에 나타남. 서로 이웃한 태그에서는 세로로 마진을 겹쳐서 적용하고, 부모 자식 관계인 태그에서도 세로로 마진을 겹쳐서 적용함. 이때 부모에 `padding`이나 `border`가 있으면 경계가 있다고 생각하고 세로 마진을 겹치지 않음.

#### 예시 1. 서로 이웃한 태그
`#a`와 `#b`의 마진을 겹치면 둘 사이의 마진은 30px이 됨.

```html
<div id="a">a</div>
<div id="b">b</div>
```

```css
#a {
  margin: 30px;
}

#b {
  margin: 20px;
}
```

#### 예시 2. 부모 자식 태그
`#b`와 `#c`는 부모 자식 관계. `#b`에는 따로 경계가 없으니까 둘의 마진을 겹쳐서 위쪽 마진은 40px이 됨. 이 마진 값을 이웃한 `#a`와 겹치면, `#a`와 `#b` 사이의 마진은 40px이 됨.

```html
<div id="a">
  a
</div>
<div id="b">
  <div id="c">
    c
  </div>
  b
</div>
```

```css
#a {
  margin: 30px;
}

#b {
  margin: 20px;
}

#c {
  margin: 40px;
}
```
