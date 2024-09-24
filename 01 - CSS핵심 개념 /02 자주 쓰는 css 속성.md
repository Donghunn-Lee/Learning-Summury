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
