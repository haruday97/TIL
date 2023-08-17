# JavaScript-Basics
## JavaScript란
HTML과 CSS로만 이루어진 사이트는 재미없고 정적일 것이다.   
페이지가 사용자와 상호작용이 가능해진다면 유저의 사용경험은 향상될 것이다.  
자바스크립트는 웹페이지에 생동감을 불어넣어준다.  

`빨간 공룡이 춤춘다` 

위 문장에서 
HTML은 명사(공룡), CSS는 형용사(빨간), JavaScript는 동사(춤춘다)에 해당한다.

## Primitive types
<ul>
    <li>Number</li>
    <li>String</li>
    <li>Boolean</li>
    <li>Null</li>
    <li>Undefined</li>
</ul>

### Number
자바의 경우 정수타입(Integer)과 소수타입(Float, Double)으로 나뉘지만
자바스크립트에서는 정수와 소수를 분리하지 않고 한 가지 타입만 있다.  

#### 연산 우선순위
초등수학에서 배우듯이 연산에는 우선순위가 있다. 서구권에서는 PEMDAS<sup id ="note_1">[1](#footnote_1)</sup>로 외운다.  

#### NaN
Not a Number(NaN)은 숫자가 아닌 값을 나타낸다. (그러나 JS에서는 숫자로 간주된다)
```
0/0 // NaN
1 + NaN // NaN
NaN * NaN // NaN
```
수학에서는 0을 0으로 나누는 것은 무의미 혹은 불가능하기에 정의할 수 없다.  
이는 JS에서도 동일하지만, 대신 JS는 컴파일 에러를 발생시키지않고 실제 값을 반환한다.  
실제 값을 반환한다는 증거는 typeof 연산자를 이용해 알 수 있다.  
```
typeof NaN // "Number"
```

### Boolean
Boolean은 true와 false의 값으로 나뉜다.  
```
let hasJob = false;
```

### String
String은 쌍따옴표로 감싸 브라우저에게 문자열임을 알린다.
작은 따옴표로 감싸는 것도 정상적으로 작동한다.  
중요한건 일관성을 유지하는 것이다.  
혼용을 하면 정상적으로 작동하지 않는다.  
```
let saying = "i told her go away' // x
let saying = 'i told her go away" // x
let saying = "i told her go away" // o
let saying = 'i told her go away' // o
```
그러나 혼용할수 있는 하나의 예외가 있다.
```
let testament = "she said 'i hate you' " // o
let testament = 'she said "i hate you" ' // o
```

#### Methods
우리가 JS를 통해 만드는 모든 문자열은 실질적으로 어떠한 통작을 내포하고 있다.  
특정 문자열을 사용해 수행할수 있는 이런 동작을 메서드라고 부른다.  
포켓몬의 특수기술과 비슷하다. 모든 포켓몬은 고유한 기술을 몇 개씩 갖고있다.  
피카츄의 백만볼트라던가, 꼬부기의 물대포라던가, ...  
이처럼 모든 문자열은 똑같지만 메서드 세트를 갖고있다.
```
"hello".toUpperCase(); // "HELLO"

let msg = "LEAVE ME ALONE";
msg.toLowerCase(); // "leave me alone"

let greeting = "   hey sup?    "
greeting.trim(); // "hey sup?"

greeting.trim().toUpperCase(); // "HEY SUP?"

```

#### Template literal
변수를 활용해 문자열을 접합하려면 다음과 같이 사용할 수 있다.
```
let company = 43;
let companyContacted = 12;

let msg = company + "개의 회사에 이력서를 냈고 " + companyContacted + "개의 회사가 면접을 제의했어요.";
```
그러나 이는 상당히 귀찮다.  템플릿 리터럴은 이런 귀찮음으로부터 우리를 구원해준다.  
```
let msg = `${company}개의 회사에 이력서를 냈고 ${companyContacted}개의 회사가 면접을 제의했어요`
```
유의사항으로 따옴표 대신 백틱을 쓴다.  

### Null & Undefined
둘다 값의 존재 유무를 나타내는 타입이다.  
null은 값이 직접적으로 없다고 명시된 상태이며,  
undefined는 아무것도 하지 않은 상태이다.  


## Variables
<ul>
    <li>let</li>
    변수
    <li>const</li>
    변경 불가 상수
    <li>var</li>
    예전 자바스크립트는 var가 유일한 변수 타입이었다. let과 차이가 거의 없다. 
</ul>




***
<sup><a id="footnote_1">[1](#note_1)</a></sup> 괄호(Parentheses) > 지수(Exponent) > 곱셈 (Multiplication) > 나눗셈 (Division) > 더하기 (Addition) > 빼기 (Subtraction)