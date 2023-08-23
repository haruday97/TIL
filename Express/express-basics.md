# Express-Basics

## Introduction
Express는 NodeJS를 위한 프레임워크이다.  
Express는 요청을 받아들일 서버의 구축을 도와주며 들어오는 요청을 파싱한다.  

## Installation
1. `npm init`을 통해 package.json 생성
2. `npm i express`

## Executing Server
```
const express = require('express');
const app = express();
app.listen(3000, () => console.log('i am on port of 3000'));

```

## Routing
Routing이란 클라이언트의 요청에 어떻게 응답할 것인지 어플리케이션의 endpoint들(URI)을 정의하는것을 말한다.  

### Route methods
```
//GET
app.get('/', (req, res) => res.send('if any request of GET comes to /, i'll be printed!'));

//POST
app.post('*', (req, res) => res.send('if any request of POST comes, i'll be printed!'));
```

### Route paths
URI 엔드포인트로 String이거나 regular expression이 온다.  
```
//request to /dogs
app.get('/dogs', (req, res) => res.send('woof woof'));
```
쿼리스트링은 route path의 영역이 아님을 유의.

### Route parameters
URL에 있는 값을 불러오기 위한 URL Segments이다.  
```
//request to http://localhost:3000/dogs/56
app.get('/dogs/:dogId', (req, res) => res.send('req.params')); 
// { "dogId" : "56" }
```

## Middleware
추후작성

## Nodemon
코드에 변경사항이 있으면 일일이 서버를 재부팅해야하는 번거로움이 있다.  
*Nodemon*은 파일의 변경사항을 감지해 서버의 재부팅을 자동으로 해주는 패키지이다.  
일반적으로 전역설치를 한다.  
`npm install -g nodemon`

## Templating
정적인 HTML을 사용하지 않고 정보와 로직을 포함한 HTML을 사용해 클라이언트에게 보여지는 컨텐츠가 동적으로 응답할 수 있게 하는 기법이다.  
템플레이팅을 통해 개발자의 노가다를 덜어준다.  
대표적인 템플릿 엔진으로 `Jade`,`Pug`,`EJS`툴이 있다.

## RESTful Route
`REST`는 REpresentational State Transfer의 약자로 서버와 클라이언트 간의 통신 방식을 정의한 아키텍처 스타일<sup id ="note_1">[1](#footnote_1)</sup>이다.
`RESTful`은 REST의 원리를 따르는 시스템이다.  

### REST API 설계 기본 규칙
<ol>
    <li>슬래시(/)는 계층 관계를 나타내는데 사용한다.</li>
    <li>URI 마지막 문자로 슬래시(/)를 포함하지 않는다.</li>
    <li>불가피하게 긴 URI경로를 사용한다면 하이픈(-)을 사용해 가독성을 높인다.</li>
    <li>언더바(_)는 URI에 사용하지 않는다.</li>
    <li>소문자를 사용하고 대문자 사용을 지양한다.</li>
    <li>파일 확장자는 URI에 포함하지 않는다.</li>
    <li>복수형을 사용한다.</li>

</ol>

***
<sup><a id="footnote_1">[1](#note_1)</a></sup>서비스의 구조 및 동작원리를 정의한 설계
## References
https://compmath.korea.ac.kr/nodejs/Node_Express.html  
https://hannut91.github.io/blogs/express/06.routing  
https://velog.io/@devp1023/Express.-%ED%85%9C%ED%94%8C%EB%A0%88%EC%9D%B4%ED%8C%85-%EA%B0%9C%EC%9A%94