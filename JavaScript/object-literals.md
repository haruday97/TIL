# Object-Literals
## 객체 리터럴이란
여러가지 변수를 하나의 묶음으로 나타낼 때 객체를 사용한다.  
이러한 객체를 표현할 때 중괄호를 사용하여 key:value의 쌍으로 데이터를 저장할 수 있는데, 이러한 데이터 구조를 객체 리터럴이라고 한다.  
객체에서 만드는 모든 키들은 문자열로 변환되는것에 유의.  
```
const person = {
    firstName: 'Mick',
    lastName: 'Jagger',
    interests: ["fishing", "dancing", "cooking"],
    isSingle: true
}
```
## Accessing
### 대괄호를 이용해 접근하는 방법
```
person["firstName"]; // "Mick"
```
### 온점을 이용해 접근하는 방법
```
person.lastName; // "Jagger"
```

***
## References
https://www.udemy.com/course/the-web-developer-bootcamp/    
https://fromnowwon.tistory.com/entry/object-literal