# Control-Statements

## Comparisons
```
> // greater than
< // less than
>= // greater than or equal to
<= // less than or equal to
== // equality
!= // not equal
=== // strict equality
!== // strict non-equality
```
숫자말고도 문자끼리 비교도 가능하다.
```
'A' < 'a' // true
```
문자끼리 비교할 경우 unicode에 값을 치환하여 비교를 한다.  
유니코드상 대문자 A는 41, 소문자 a는 61이므로 위의 식은 참이다.  

### Double Equals & Triple Equals
이중 등호(Double Equals)로 두 값이 같은지 확인할 수 있다. 그러나 타입은 구분하지 않는다.  
두 값이 다른 타입이라면 값을 바꾸거나, 같은 타입으로 강제로 형변환을 한다.  
```
0 == '0' // true
0 == ''; // true
0 == false; // true
null == undefined // true
```
삼중 등호(Triple Equals)는 예상했듯이 타입을 구분하고 값과 타입 모두 비교한다.  
```
0 === '0' // false
0 === ''; // false
0 === false; // false
null === undefined // false
```

## Conditionals
JS에서 사용할수 있는 조건문의 형태는 다음과 같다.  
<ul>
    <li>if문</li>
    <li>if / else문</li>
    <li>if / else if/ else문</li>
    <li>switch문</li>
</ul>

## Truth-y & False-y
JS 프로그래밍을 하다보면 할당한 변수에 값이 없거나 혹은 호출한 함수의 리턴값이 없을때에 대한 처리를 해줘야 할때가 있다.  
Truth-y & False-y(혹은 Truthy와 Falsy)는 이러한 경우들의 예외처리를 하기 위해 활용할 수 있으며
JS의 모든 값은 다음 경우를 제외하면 Truth-y이다.  
<ul>
    <li>false</li>
    <li>0</li>
    <li>빈 문자열</li>
    <li>null</li>
    <li>undefined</li>
    <li>NaN</li>
</ul>

```
if(undefined){
    console.log("truthy");
}else{
    console.log("falsy");
}
// falsy
```

***

## References
https://www.udemy.com/course/the-web-developer-bootcamp/  
