# ES6-Syntax
## Default Parameters
기본 매개변수(Default Parameters)는 파라미터가 지정되지 않았을 경우 자동으로 값을 설정하는 구문이다.  
```
function multiply(a, b = 1){
    return a * b;
}
```
기본 매개변수를 첫번째 인자로 받으면 예상하지 못한 값을 출력할 수 있음을 유의한다.  
```
function greet(msg = "Good morning", name){
    console.log(`${msg}, ${name}!`)
}
// greet("carl") -> carl, undefined!

function greet(name, msg = "Good morning"){
    console.log(`${msg}, ${name}!`)
}
// greet("carl") -> Good morning, carl!
```

## Spread
배열과 같은 반복가능한 객체를 전개(spread)구문을 사용해 확장할 수 있다.
### Array
max 메서드를 이용해 인수들의 최대값을 구하는법은 다음과 같다.  
```
Math.max(124,235,166,683,354,564); // 683
```
그러나 배열을 max메서드에 인수로 넣는다면 작동하지 않는다.
```
const nums = [243,548,511,438,896,341,677];
Math.max(nums); // NaN
```
이럴때 전개를 사용한다. 전개는 `...`를 배열 앞에 붙여 사용한다.
```
Math.max(...nums); // 896
```
배열을 복사할 수도 있다.  
```
const cats = ['Scottish Fold', "Rag Doll', 'Munchkin'];
const dogs = ['Beagle', "Bulldog', 'Afghan Hound', 'Dalmatian'];

const catdogs = [...cats, ...dogs];
```
### Object
또한 여러개의 객체를 하나의 객체로 묶을 수 있다.  
```
const cockroach = {
    legs : 6,
    family : 'Blattodea',
    isCute : false
}

const spider = {
    legs : 8,
    family : 'Araneae'
}

const newBug = { ...cockroach, ...spider }
newbug; // legs:8, family:"Araneae", isCute:false
```
중복되는 값이 있을경우 마지막 값이 먼저 있던 값을 덮어씌운다.
## Rest Parameters
나머지 매개변수들을 모아주는 구문이다. 매개변수 앞에 `...` 를 사용한다.
```
function sum(){
    return nums.reduce((total, el) => total + el);
}
```

## Destructuring
분해(Destructuring)는 값을 분해하는 구문으로 이는 배열이나 객체에 적용할 수 있다.
### Array Destructuring
사용하기 위해서는 배열이 정렬되어 있어야한다.  
```
const scores = [96,87,74,72,65,60];
const [first, second, third, ...else] = scores;
```
분해를 하면 변수에 접근이 가능하다.
```
first // 96
second // 87
third // 74
```
### Object Destructuring
배열 구조 분해와 달리 순서를 따르지 않는다.  
객체는 순서가 없기때문이다.  
```
const user1 = {
    firstName: "Thomas",
    lastName: "Edison",
    born: 1847,
    died: 1931
}
const {email, password, fistName, lastName} = user1;
```
분해를 하면 변수에 접근이 가능하다.
```
firstName // Thomas
lastName // Edison
```
다른 이름으로 변수를 할당하기 위해서는 콜론을 붙인다.  
```
const {born : birthYear} = user1
born // undefined
birthYear // 1847
```
아래와 같이 디폴트 값을 넣을 수 있다.  
```
const user2 = {
    firstName: "Elon",
    lastName: "Musk",
    born: 1971
}
const {died: deathYear = 'N/A'} = user2
deathYear // N/A
```
user1의 경우 died 값이 존재하기때문에 디폴트 값이 출력되지 않는다.  
```
const {died: deathYear = 'N/A'} = user1
deathYear // 1847
```
### Parameter Destructuring
함수의 매개변수에 적용한다.
```
function fullName({firstName, lastName}){
    return `${firstName} ${lastName}`
}
```
## For...of
[해당문서](loops.md) 참조

## Arrow Function
화살표 함수는 함수표현식을 축약시킨다.  
```
function multiply(a, b){
    return a * b;
}

const multiply = (a, b) => a * b;
```
위 두개의 함수는 완전히 같은 기능을 수행한다.  
매개변수가 하나일 경우 매개변수의 소괄호를 생략할 수 있다.  
```
function greet(name){
    console.log(`hello ${name}!`);
}

const greet = name => console.log(`hello ${name}!`);
```
## Nullish Coalescing
`??` 왼쪽이 null 혹은 undefined일 경우 오른쪽 항의 값을 반환한다.  
```
console.log(null ?? '으잉');
```
## Optional Chaining
`?.` 왼쪽이 null 혹은 undefined일 경우 undefined를 반환한다.  
중첩된 객체에서 값을 추출할때 주로 쓰인다.  
```
let user = {
    name : 'kim',
    age : 20
}
console.log(user?.age)
```

***
## References
https://www.udemy.com/course/the-web-developer-bootcamp/  
https://velog.io/@shaqok/ES6-ES6-Syntax-%EC%A0%95%EB%A6%AC