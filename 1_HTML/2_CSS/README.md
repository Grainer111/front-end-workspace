# CSS (Cascading Style Sheet)

- 웹 페이지의 표현(디자인)을 나타내는 언어
- 특정 요소를 선택해서 원하는 "스타일"을 적용시킬 수 있음

```CSS
선택자(누구한테) {
    속성:(어떤효과) 값(얼만큼);
}
```

### 스타일 적용 방법

### 내부 방식

1. 인라인 방식

```html
<태그 style="속성: 값; 속성: 값;"></태그>
```

2. 내부 스타일

```html
<head>
  <style>
    선택자 {
      속성: 값;
      속성: 값;
    }
  </style>
</head>
```

### 외부 방식

3. 링크 방식

```html
<head>
  <link rel="stylesheet" type="text/css" href="style.css" />
</head>
```

```css
선택자 {
  속성: 값;
  속성: 값;
}
```

## 선택자 우선순위

1. 동일한 선택자를 사용하는 경우

- 나중에 작성한 스타일 적용

2. 다른 방식의 선택자 사용

-|important > 인라인 방식 > 아이디 선택자 > 클래스 선택자 > 태그 선택자 > 태그 선택자 > 전체 선택자

## 크기를 지정하는 단위

- 절대 크기는
  **px** : 모니터의 픽셀 단위로 크기를 계산
- 상대 크기
  -%(퍼센트) : 부모 요소의 크기에 대한 상대적인 비율
- em : 부모 요소에서 지정한 크기를 1em으로 저장한다. 상대적인 16px
  **rem** : 최상위 요소('html')에서 지정한 폰트의 크기를 1rem으로 계산 16px

- 밝기(brightness)는 %로 표시 (0%는 가장 어둡고 100%는 순색)

# Flex (flexble Box, Flexbox)

-css 레이아웃 모델로 화면 크기에 따라 레이아웃의 배치나 크기를 조절할 때 편리하게 사용

````html
<div class="contrainer">
  <div class="item"></div>
  <div class="item"></div>

  ##display: flex; - Flex 컨테이너에 'display: flex;' 적용하면서 시작 ```css
  .container { display:: flex }
</div>
````

### flex-direction

- 배치 방향 설정
- 아이템들이 배치되는 메인축의 방향을 결정하는 속성

```css
.container {
  flex-direction: row/column/row-reverse column;
}
```

- row : 왼쪽부터 순차적으로 배치 (기본값)
- row-reverse : 오른쪽부터 배치
- column : 위에서부터 배치
- column-reverse : 아래에서부터 배치

## flex-wrap

- 아이템 줄바꿈을 어떻게 할지 결정하는 속성

```css
.container {
  flex-wrap: nowrap / wrap / wrap-reverse;
}
```

- nowrap : 기본값, 줄바꿈을 하지 않음
- wrap
- wrap-reverse : 역순으로 배치 후 줄바꿈

````css
.container {
  justify-content: flex start / flex end / center / space-between
  flex flow: flex-direction flex-wrap
}
flex start : 기본값. 아이템들을 시작점으로 정렬
flex end : 아이템들을 끝점으로 정렬
center : 아이템들을 가운데로 정렬
space-between :
- 메인축 방향으로 정렬

## align-items
- 수직축 방향으로 정렬

```css
.container {
  align-items: stretch / flex start / flex end /
}

````

- stretch : 기본값, 아이템들을 끝까지 늘림
- flex start : 아이템들을 위쪽으로 정렬

## flex-flow

- flex-direction과 flex wrap을 한꺼번에 지정할 수 있는 속성

````css
.container {
  flex-flow: flow direction flex wrap;
}

```css
.container {
  align-content: stretch / flex-start / flex-end
}

##flex-basis

-flex 아이템의 기본 크기 설정 (flex-direction이 row일 때는 너비, column일 때는 높이)

##flex-grow
-flex basis의 값보다 크기

##flex-shrink

- flex grow와 쌍을 이루는 속성으로, flex-basis 값보다 작아질 수 있는지를 결정하는 속성


## flex

- flex-grow, flex-shrink, flex-basis를 한번에 쓸 수 있는 속성

```css
.item {
  flex: 1 1 auto;

  /* flex grow: 1; flex-shrink: 1; flex-basis: 1;  flex-basis: auto
} */

## align-self

- 특정 아이템만 정렬을 따로 정렬하고자 할 때 사용하는 속성
- item들의 순서를 바꿀 수 있는 속성

```css
````
