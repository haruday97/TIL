# React Basics

## React란
리액트(React)는 유저인터페이스를 구축하기 위한 **자바스크립트 라이브러리**이다.

## JavaScript XML
JSX는 자바스크립트를 확장한문법으로, 간단하게 자바스크립트 안에 있는 HTML 코드이다.  
컴포넌트에 여러 요소가 있다면 하나의 부모로 감싸야하며, 표현식을 사용하기 위해서는 중괄호로 감싸주면 된다.  
```
function App(){
	return(
    	<div>
          <h1>Hello {name}</h1>
          <h2>Bye</h2>
        </div>
    )
}
export default App;
```
## Component
리액트는 작은 독립적인 조각들로 나뉘어 개발되는데, 이런 조각들을 컴포넌트 라고한다.  
컴포넌트(Component)는 UI를 이루는 최소 단위이다.  
컴포넌트를 통해 재사용 가능하며 각자의 관심사를 명확하게 갖는 코드를 작성할 수 있다.

## Props
props는 컴포넌트 간에 데이터를 전달 및 상호작용하는데 사용하는 매개변수와 비슷한 개념이다.  
부모 컴포넌트에서 자식 컴포넌트로 데이터를 전달하는데 사용한다.  
props는 __Read Only__ 이어야하며 자식 컴포넌트는 전달받은 프롭스를 사용해 렌더링 및 작업을 수행한다.  


### Declarative Approach
리액트는 컴포넌트를 만들때 소위 선언형 접근법(Declarative Approach)이라는 방식을 사용한다.  
선언형 접근법은 원하는 상태를 선언하는 방법으로, 개발자가 원하는 최종상태를 정의한다.  
리액트는 이를 기반으로 실제 웹 페이지에서 어떤 요소가 추가, 삭제, 수정해야하는지 판단하게 된다. 
이를 통해 개발자는 자바스크립트를 통해 직접 DOM을 조작할 필요가 없어지게 된다.   


***
## References
https://react.vlpt.us/basic/05-props.html  
https://velog.io/@nemo/%EC%84%A0%EC%96%B8%ED%98%95-%EB%AA%85%EB%A0%B9%ED%98%95  
https://ko.legacy.reactjs.org/docs/components-and-props.html