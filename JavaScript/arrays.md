# Arrays

## Creating
```
let students = [];
let colors = ['red','blue','green'];
let nums = [12,54,32,42,23];
let stuffs = [true, 68, undefined, null, false, 'cat', [1,2,3]];
```
다른 프로그래밍 언어에서는 기본적으로 배열은 하나의 타입으로만 구성이되는 반면 JS에서는 그렇지않다.  
test
## Accessing

### Push
배열의 마지막에 요소를 추가한다.  
변경된 배열의 길이를 반환한다.
```
let people = ["kim", "lee", "choi"];
people.push("park"); // 4
// -> ["kim", "lee", "choi", "park"]
```

### Pop
배열의 마지막에 요소를 삭제한다.  
삭제된 요소를 반환한다.
```
let people = ["kim", "lee", "choi"];
people.pop(); // "choi"
// -> ["kim", "lee"]
```

### Shift
배열의 시작에 요소를 삭제한다.  
삭제된 요소를 반환한다.
```
let people = ["kim", "lee", "choi"];
people.shift(); // "kim"
// -> ["lee", "choi"]
```

### Unshift
배열의 시작에 요소를 추가한다.  
변경된 배열의 길이를 반환한다.
```
let people = ["kim", "lee", "choi"];
people.unshift("park"); // 4
// -> ["park", "kim", "lee", "choi"]
```

### Splice
배열의 특정 인덱스에 요소를 추가 혹은 삭제한다.  
수정된 배열을 반환한다.
```
let people = ["kim", "lee", "choi"];
people.splice(1,1) 
// -> ["kim", "choi"]
```
***
## References
