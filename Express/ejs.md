# EJS
## Introduction
`EJS`는 `Node.js`와 `Express`에서 많이 사용되는 템플릿 엔진이다.  

## Installing
설치 : `npm i ejs`  
설치후 `set()`메서드를 이용해 사용하려는 템플릿엔진이 `ejs`임을 알린다.
```
//index.js
app.set('view engine', 'ejs');
```
Express는 디폴트값으로 views나 템플릿이 `views`디렉토리에 있다고 가정한다.  
`./views/home.ejs`
```html 
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Home</title>
</head>
<body>
    <h1>The home page</h1>
    <p> 
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsa enim voluptates exercitationem reprehenderit similique est ratione neque dicta quae ducimus molestias facilis quasi sequi nobis officiis inventore laboriosam, odit provident.
        Debitis natus tenetur cum id, corporis exercitationem eius saepe officiis perspiciatis cupiditate fugit eaque ipsum vero molestias! Numquam quis magnam impedit harum totam, at maxime perferendis maiores esse cumque neque!
        Asperiores minus maxime vitae commodi rerum incidunt temporibus praesentium veritatis, ipsam aliquam ullam debitis ipsum, quisquam tempora voluptas tempore a odio cumque alias repudiandae labore est. Quo dolorum quos porro!
        Rem, ratione quae amet cum necessitatibus ullam quis, eum dolores aliquam, aspernatur ipsam. Iste ullam cupiditate cumque itaque facilis mollitia dolor nihil et porro dignissimos, eius quos consequatur eaque odit.
        Tempora, rem asperiores, aspernatur nihil quisquam assumenda et itaque at delectus sint inventore corporis perferendis, temporibus reiciendis impedit similique molestias quia voluptates dolorem quasi enim ab. Est soluta impedit maxime.
    </p>
    <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Expedita nesciunt error inventore perspiciatis maxime, fugiat quibusdam minus? Quod ab officiis assumenda, atque sunt beatae eos amet reprehenderit ad inventore nemo.
        Distinctio, et architecto velit expedita ad nobis molestias laudantium tempora modi porro cupiditate dolorem veritatis aperiam tenetur? Dolorem, reprehenderit voluptatem, optio recusandae atque sunt vero nostrum ab dolorum iste alias.
        Ratione impedit in esse saepe culpa labore blanditiis fugiat id debitis, odit facere. Nisi aliquam doloribus iusto quasi, ipsa nobis fugit hic dicta repudiandae impedit. Temporibus accusantium assumenda quae recusandae!
        Iste eos perspiciatis sunt velit, adipisci fuga aliquam omnis ratione culpa a, dolore reiciendis doloribus totam earum corrupti ipsa voluptatem dolor ea assumenda? Sed nihil quas reprehenderit iste magnam. Ut!
        Voluptatibus non optio dicta maxime, accusamus atque rem perferendis quo eveniet repellendus facere harum nam omnis nemo ex fugit natus itaque? Dolorem tenetur quibusdam quis itaque quaerat sed magni reiciendis.
    </p>

</body>
</html>
```
접속해보면 잘된다.
### Set working directory path
views 폴더의 이름을 바꾸고 싶거나, index.js 가 위치하는 디렉토리 밖에서 서버를 실행시키면 에러가난다.  
이는 `set()` 메서드를 통해 경로를 지정해줌으로 해결할 수있다.
```
const path = require('path');
...
app.set('views', path.join(__dirname, 'temps'));
```
위 코드에서는 `views` 폴더명을 `temps`로 설정했다.

### Data delivering to template
HTML 문서안에 아래와같은 메서드작성을 지양한다. 정상적인 작동은 되나 Html문서의 가독성을 떨어트린다.  
`random.ejs`
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Random EJS</title>
</head>
<body>
    <h1>Your Random number is <%= Math.floor( Math.random() * 10 ) + 1 %></h1>
</body>
</html>
```

대신 아래와 같이 데이터를 전달할 수 있다.  
`index.js`
```
app.get('/rand', (req, res) =>{
    const num =  Math.floor( Math.random() * 10 ) + 1;
    res.render('random', { num : num}); // { num } 으로도 전달 가능
})
```
`random.ejs`
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Random EJS</title>
</head>
<body>
    <h1>Your Random number is <%= num %></h1>
</body>
</html>
```

### Conditional
`<% %>`구문은 템플릿을 통제할 수 있도록 로직을 추가한다. 사용자에게 보여지지 않는다.
```html
<body>
    <h1>Your Random number is <%= num %></h1>
    <% if(num % 2 === 0){ %>
        <h2>That is even number!</h2>
    <% } else { %>
        <h2>That is odd number!</h2>
    <% } %>
</body>
```
### Sub-template
`include()`메서드를 통해 html 요소등을 컴포넌트화 할수있다.  
```html
<%- include('path/file') %>
```

*** 
<sup id ="note_1">[1](#footnote_1)</sup>
<sup><a id="footnote_1">[1](#note_1)</a></sup> contents
## References
![image](../Assets/imagename.png)  