# Sass
## Introduction
SASS는 Css를 보완하는 전처리기이다.  
Css를 사용하다보면 반복작업을 하거나 불편한 요소가 있는데 이를 해소시켜준다.  

## Scss/Sass
SASS에는 Sass와 Scss 둘로 나뉘어 진다.  
가장 큰 차이점으로는 Sass는 중괄호와 세미콜론을 사용하지 않으며 Scss는 중괄호와 세미콜론을 사용한다.

```
// scss
.background {
    background-color : red;
    width: 100%;
}
```
```
// sass, 중괄호 대신 indent를 사용한다.
.background
    background-color : red
    width: 100%
```
이후 아래 설명에서는 Scss 표기법을 따른다.  
## Pros

### 변수로 관리해줄 수 있다

기존 Css에서도 다음과 같은 방법으로 변수를 관리할 수 있다.  
```
:root {
    --main-bg-color: brown;
}

.target {
    background-color: var(--main-bg-color);
}
```
위와 같은 방법으로 변수를 할당해줄수 있으나 다소 번거롭다. SASS는 다음과 같이 간결하게 만들어준다.
```
$main-bg-color: brown;

.target {
    background-color: var(--main-bg-color);
}
```
변수명 앞에 달러기호를 붙여줌으로써 변수를 선언할 수 있으며 재사용을 가능케해준다.  

### 재사용을 할수있게 해준다
색깔만 다른 버튼 3개를 기존의 css로 만들어보면 다음과같다.  
```
.btn-green {
    width : 50px;
    height : 100px;
    padding : 20px;
    color : green;
}

.btn-blue {
    width : 50px;
    height : 100px;
    padding : 20px;
    color : blue;
}

.btn-red {
    width : 50px;
    height : 100px;
    padding : 20px;
    color : red;
}

```
`@extend`를 사용해 다음처럼 상속을 받아 재사용을 할수있게 해준다.  
```
%btn {
    width : 50px;
    height : 100px;
    padding : 20px;    
}

.btn-green {
    @extend %btn;
    color : green;
}

.btn-red {
    @extend %btn;
    color : red;
}

.btn-blue {
    @extend %btn;
    color : blue;
}
```

### 관련있는 클래스를 묶어준다
반복되는 클래스명을과 하위 클래스들을 반복적으로 사용해 css를 해야할 때가 있다.  
SASS는 한번에 이를 작성할 수 있게 도와주는데 이를 `nesting`이라고 한다.
```
.main-bg h2 {
    font-size: 35px;
}
.main-bg button {
    color : red;
}
```
위와 같은 코드를 아래와 같이 작성할 수 있다.  
```
.main-bg {
    h2 {
        font-size: 35px;
    }
    button {
        color : red;
    }
}
```

### 함수를 만들어 재사용할수 있다
`@mixin`는 SASS의 핵심이라고 볼수있으며 프로그래밍 언어에서 함수를 선언하는것과 유사한 기능이다.  
`@mixin`을 통해 선언하고 `@include`를 통해 불러와야한다.  
또한 함수처럼 파라미터를 받아 사용할 수 있다.

```
@mixin fontStyle($param) {
    font-size: $param;
    letter-spacing: -1px;
    text-align: center;
}

.target h2 {
    @include fontStyle(50px);
}
```

### 반복문과 조건문을 사용할 수 있다
`@if`,`@else`,`for`를 사용해 제어할 수 있게하며 사용법은 자바스크립트와 비슷하다.  

### 코드를 모듈화해준다.  
`@use`를 통해 해당 스타일시트에서 선언된 변수 및 믹스인 함수를 불러와서 사용할 수 있다.  
***
## References
https://velog.io/@lize/5.-Sass-%EA%B7%9C%EC%B9%99  
https://developer.mozilla.org/ko/docs/Web/CSS/Using_CSS_custom_properties  
https://www.biew.co.kr/entry/Sass%E3%86%8DSCSS-SASS-%EB%AC%B8%EB%B2%95-3%ED%8E%B8-%EC%A1%B0%EA%B1%B4%EB%AC%B8if-%EB%B0%98%EB%B3%B5%EB%AC%B8for