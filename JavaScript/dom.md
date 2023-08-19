# DOM
## introduction
DOM(Document Object Model)은 웹 페이지를 구성하는 JS 객체들의 집합이다.  
HTML 요소로 h1태그가 있다면 이를 모델링하는 JS 객체가 있다.  
h1태그를 가리키는 이 JS객체를 변경하면 페이지에는 변경사항이 반영된다.  
즉 DOM은 JS에서 웹 페이지의 콘텐츠로 접근하는 창이자 통로라고 비유할 수 있다.  
브라우저는 웹 페이지를 띄울 때 HTML과 CSS 정보를 받아들인 후 요소와 스타일을 기반으로 JS객체를 생성한다.  
각 객체는 서로 연결된 트리구조를 띄게되며 최상단의 요소는 Document가 된다.
![dom_tree](../Assets/dom_tree.png)  
## Selecting
하나의 요소, 특정 클래스 혹은 특정 타입의 모든 요소 등을 선택한다.
### getElementById
해당하는 id의 요소를 선택하고 없을시 null을 반환한다.  
```
const name = document.getElementById('name');
```
### getElementsByTagName
웹 페이지내의 해당하는 모든 태그를 선택하고 HTML Collection을 반환한다. 배열이 아님을 유의한다.  
해당하는 값이 없다면 빈 HTML Collection을 반환한다.
```
const imgs = document.getElementsByTagName("img");
```
### getElementsByClassName
웹 페이지내의 해당 클래스를 가진 모든 요소를 선택하고 HTML Collection을 반환한다. 배열이 아님을 유의한다.  
해당하는 값이 없다면 빈 HTML Collection을 반환한다.
```
const animals = document.getElementsByClassName("animal");
```
### querySelector
최근 생겨난 문법으로 위에 언급된 선택법보다 간편하게 선택할 수 있다.  
```
// Finds first h1 element:
document.querySelector('h1');

// Finds all h2 element:
document.querySelectorAll('h2');

// Finds element with ID of red:
document.querySelector('#red');

// Finds first element with class of:
document.querySelector('.big');

// Finds all element with class of:
document.querySelectorAll('.big');

// Finds nth img element:
document.querySelector('img:nth-of-type(2)');
```

## Manipulating

### innerText
사용자에게 보여지는 텍스트를 반환한다.
```
document.querySelector('p').innerText = 'lol';
```
### innerHTML
요소에 포함된 마크업의 모든 텍스트를 반환한다.  
```
document.querySelector('h1').innerHTML = '<i>this is h1</i>';
```
대입연산자를 사용할수도 있다.
```
document.querySelector('h1').innerHTML += '<sup>1</sup>';
```

### textContent
노드 안에 있는 모든 텍스트를 반환한다.
```
document.querySelector('div').textContent = 'lmao';
```
***
## References
https://www.udemy.com/course/the-web-developer-bootcamp/  