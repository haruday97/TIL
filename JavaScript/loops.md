# Loops
## for
여타 프로그래밍 언어와 동일하게 작동한다.
```
for (let i = 1; i <= 10; i++){
    console.log(i); // 1...10
}
```

## while
여타 프로그래밍 언어와 동일하게 작동한다.
```
let num = 0;
while (num < 10) {
    console.log(num);
    num++;
}
```
## for...of
JS만의 문법이다.  
인덱스를 생략해서 반복문의 가독성을 향상시켜준다.  
참고로 익스플로러에서 지원되지 않는다.  

```
const subreddits = ['cringe', 'books', 'chickens', 'funny', 'pics', 'soccer'];

// for문
for (let i = 0; i < subreddits.length; i++) {
    console.log(`visit reddit.com/r/${subreddits[i]}`);
}

// for...of문
for (let subreddit of subreddits) {
    console.log(`visit reddit.com/r/${subreddit}`);
}
```

인덱스를 구해 요소에 접근하지 않는 경우에는 for of문이 일반적으로 낫다.  

```
const seatingChart = [
    ['Kristein', 'Erik', 'Namita'],
    ['Yuma', 'Antonio', 'Lionel', 'Thiago'],
    ['Juanito', 'Christiano', 'Marcos']
]

// for문
for (let i = 0; i < seatingChart.length; i++) {
    const row = seatingChart[i];
    for(let j = 0; j < row.length; j++){
        console.log(row[j]);
    }
}

// for of문
for (let row of seatingChart) {
    for (let student of row){
        console.log(student);
    }
}
```

객체 리터럴을 메서드(keys, values, entries)를 통해 배열로 만들어주고 for of를 사용하면 반복문을 사용할 수 있다.  
```
const testScores = {
    "kiana" : 56,
    "atrox" : 78,
    "amumu" : 97,
    "janna" : 68,
    "annie" : 31 
}

let total = 0;
let scores = Object.values(testScores)

for (let score of scores){
    total += score;
}
console.log(total / score.length);

```

***
## References
https://www.udemy.com/course/the-web-developer-bootcamp/    
https://fromnowwon.tistory.com/entry/object-literal