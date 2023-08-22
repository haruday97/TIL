# Node.js-Basics
## Introduction
Node JS는 브라우저 밖에서 실행되는 JavaScript Runtime<sup id ="note_1">[1](#footnote_1)</sup>이다.  
Node.Js를통해 자바스크립트 코드를 브라우저를 열지않고 실행할 수 있다.  
그러나 브라우저를 통해 실행하는것이 아닌만큼 DOM을 사용할 수 없다.  
노드는 자바스크립트에서 가장 인기있는 도구로, 커뮤니티가 강력하다는 이점을 가지고있다.  

## Features
<ol>
    <li>빠르다</li>
    <li>비동기 기반</li>
    <li>단일스레드, 그러나 높은 확장성</li>

</ol>

## What people do with Node?
![what_people_do_with_nodejs](../Assets/what_people_do_with_nodejs.png)

## Module
모듈을 생성하기 위해선 `exports` 전역 객체를 사용하며, 모듈을 불러오기 위해서는 `require()` 메서드를 사용한다.   

### exports
```
const add = (a, b) => a + b;

const multiply = (a, b) => a * b;

const PI = 3.14159265357989;
```
위의 두개의 함수, 하나의 상수를 모듈을 생성하려면 아래와 같은 방법을 사용한다.
#### 모듈에 직접 할당하는 방법
```
module.exports.add = add;
module.exports.multiply = multiply;
module.exports.PI = PI;
```
`module.`을 생략할수있다.

#### 객체 리터럴에 할당하는 방법
```
// math.js
const math = {
    add: add,
    PI: PI,
    multiply: multiply
}
``` 

#### 선언과 동시에 할당하는 방법

```
module.exports.add = (a, b) => a + b;

module.exports.multiply = (a, b) => a * b;

module.exports.PI = 3.14159265357989;
```
`module.`을 생략할수있다.

### require()
모듈을 불러오기 위해서는 `require()`메서드를 사용한다.  
```
// index.js
const math = require("./math");
```
아래와 같이 구조 분해를 해서 불러올수도 있다.  
```
const {PI, add} = require("./math");
```
기존의 모듈이 아니거나 `NPM`에서 인스톨한 모듈이 아닌경우 경로를 명시해야한다.  
같은 디렉토리에 있다고 가정하고 `./`를 명시했다.  

## NPM
Node Package Manager는 노드 패키지를 관리해주는 툴이다.  
패키지는 타인이 작성한 라이브러리로 npm은 그런 노드 패키지를 위한 표준화된 저장소이다.  
안드로이드의 플레이스토어를 생각하면 된다.

## Package.json
현재 프로젝트에 관한 정보와 패키지매니저를 통해 설치한 모듈들의 의존성을 기록, 관리하는 파일이다.
`npm init` 명령어를 이용해 생성한다.  
`-y` 플래그로 질문을 생략할 수 있다.
***
<sup><a id="footnote_1">[1](#note_1)</a></sup> 프로그램을 실행할 수 있는 환경
## References
https://victorydntmd.tistory.com/16  
https://phsun102.tistory.com/28  

