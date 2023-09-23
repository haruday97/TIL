# State

## State란
state는 컴포넌트의 상태나 데이터를 저장, 관리에 사용된다.  
이벤트가 트리거 되면 웹 페이지에서 표시되는 내용을 변경해줘야 할 때가 있다.  
리액트에서는 사이트가 한번 렌더링 되면 출력되는 값이 변경되어도 화면에 자동으로 반영되지 않는다.  
이처럼 변경되는 값을 관리하기 위해 state를 사용하면 리액트에서 해당 컴포넌트를 재렌더링(re-rendering)을 하게되어 변경된 내용을 화면에 반영한다.  
## 사용법
```javascript
import { useState } from 'react'

function Example() {
    const [count, setCount] = useState(0);
    
    const clickHandler = () => {
        setCount(count + 1);
    }
    
    return (
        <div>
            <button onClick={clickHandler} >click here!</button>
            <p>{count} times clicked</p>
        </div>
    )
}
```
useState 리액트 훅<sup id ="note_1">[1](#footnote_1)</sup>을 import한다. 
useState()를 받는 배열을 생성하는데, 이는 두 개의 인자를 받으며 첫번째는 상태값, 두번째는 상태값을 업데이트하는 함수명을 받는다.  
함수명은 관례적으로 카멜케이스 형식으로 상태값앞에 set를 붙인다.  



### SubSection

#### SubSubSection

## React Hook

## Section

## Section

*** 
<sup><a id="footnote_1">[1](#note_1)</a></sup> React 16.8 version에서 새로 도입된 기능, 함수형 컴포넌트에서 다양한 기능을 지원하는 라이브러리. 대표적으로 useState, useEffect, useRef 등이있다.
## References
https://life-with-coding.tistory.com/510  
https://onlyfor-me-blog.tistory.com/463  
https://ko.legacy.reactjs.org/docs/faq-state.html

![image](../Assets/imagename.png)  