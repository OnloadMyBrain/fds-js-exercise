### 문제 1

두 수를 입력받아 큰 수를 반환하는 함수를 작성하세요.
```js
function larger(x,y){
  return Math.max(x,y);
}
// 또는
const larger = (x,y) => Math.max(x,y);

// if문
function largeIf(x,y){
  if(x > y){
    return x;
  } else {
    return y;
  }
}

// 삼항연산자
function larger2(x,y){
  return x > y ? x : y;
}
```

### 문제 2

세 수를 입력받아 그 곱이 양수이면 `true`, 0 혹은 음수이면 `false`, 둘 다 아니면 에러를 발생시키는 함수를 작성하세요.

에러를 발생시키는 코드는 다음과 같습니다.

```js
function isPositive(x,y,z){
  const result = x * y * z;
  // 만약 곱이 양수이면 true 반환
  if(result > 0){
    return true;
  }else if(result <= 0){
    // 만약 0 혹은 음수이면 false 반환
    return false;
  }else{
    throw new Error('입력값이 잘못 되었습니다.');
  }
}
```

### 문제 3

세 수 `min`, `max`, `input`을 입력받아, 다음과 같이 동작하는 함수를 작성하세요.
- `min`보다 `input`이 작으면, `min`을 반환합니다.
- `max`보다 `input`이 크면, `max`를 반환합니다.
- 아니면 `input`을 반환합니다.

예:
```
limit(3, 7, 5); -> 5
limit(3, 7, 11); -> 7
limit(3, 7, 0); -> 3
```

```js
// if 문
function limit(min,max,input){
  if(min > input){
    return min;
  }else if(max < input){
    return max;
  }else{
    return input;
  }
}

// 삼항연산자 결과값 반환
function limit2(min, max, input) {
  return (
    input < min ? min :
    input > max ? max :
    input
  );
}

// switch 문
function limit(min, max, input) {
 switch(true) {
   case min>input :
     console.log(min);
     break;
   case max<input :
     console.log(max);
     break;
   default :
     return input;
  }
}
```
### 문제 4

어떤 정수가 짝수인지 홀수인지 출력하는 함수를 작성하세요. 이를 이용해서, 1부터 20까지의 수가 각각 짝수인지 홀수인지 출력하는 프로그램을 작성하세요.
```js
// 함수선언
function printEvenOrOdd(x){
  if(x % 2 === 0){
    console.log(x +'은 짝수');
  }else{
    console.log(`${x}은 홀수`);
  }
}
// 반복문 while 문을 이용해서 함수 호출
let i = 0;
while(i < 20){
  printEvenOrOdd(i + 1);
  i++;
}
// 반복문 for를 이용해서 함수 호출
for (let i = 1; i <= 20; i++) {
  printIfEvenOrOdd(i);
}

// 또는 함수안에서 모두 선언
function evenOrOdd(){
  for(let i = 1; i < 21; i++){
    if(i % 2 === 0){
      console.log(i + '은 짝수');
    }else{
      console.log(`${i}은 홀수`);
    }  
  }
}
evenOrOdd();
```

### 문제 5

100 이하의 자연수 중 3과 5의 공배수를 모두 출력하는 프로그램을 작성하세요.
```js
  for(let i=1; i<=100; i++){
    if(i % 3 === 0 && i % 5 === 0){
      console.log(i);
    }
}
```
### 문제 6

자연수를 입력받아, 그 수의 모든 약수를 출력하는 함수를 작성하세요.
```js
function printFactors(n) {
  for (let i = 1; i <= n; i++) {
    if (n % i === 0) {
      console.log(i);
    }
  }
}
```

### 문제 7

2 이상의 자연수를 입력받아, 그 수가 소수인지 아닌지를 판별하는 함수를 작성하세요.

```js
```

### 문제 8

1부터 100까지의 수를 차례대로 출력하되, 자릿수에 3, 6, 9중 하나라도 포함되어 있으면 '짝!'을 대신 출력하는 프로그램을 작성하세요.
```js
for(let i=1; i<=100; i++){
  const str = i.toString();
  if (str.includes('3') || str.includes('6') || str.includes('9')){
    console.log("짝");
  }else{
    console.log(i);
  }
}
```


### 문제 9

양의 정수를 입력받아, 다음과 같은 패턴의 출력을 하는 함수를 작성하세요.

1을 입력받은 경우:
```
*
```

3을 입력받은 경우:
```
*
* *
* * *
```

5를 입력받은 경우:
```
*
* *
* * *
* * * *
* * * * *
```
```js
// 반복문에 repeat을 이용
function stars(n){
  for(let i=0; i<n; i++){
    const str = '* '.repeat(i + 1);
    console.log(str);
  }
}
// 변수 선언 없이 바로 출력
function stars(n) {
  for (let i = 1; i <= n; i++) {
    console.log('* '.repeat(i));
  }
}
// 이중 for문을 이용
function stars(n){
  for(let i=0; i<n; i++){
    let str = '';
    for(let j=0; j<i+1; j++){
      str += '* ';
    }
    console.log(str);
  }
}

```

### 문제 10

양의 정수를 입력받아, 다음과 같은 패턴의 출력을 하는 함수를 작성하세요.

1를 입력받은 경우:
```
*
```

3를 입력받은 경우:
```
  *
 * *
* * *
 * *
  *
```

5를 입력받은 경우:
```
    *
   * *
  * * *
 * * * *
* * * * *
 * * * *
  * * *
   * *
    *
```
```js
function diamond(n){
  for(let i=0; i<n; i++){
    const str = ' '.repeat(n - i -1) + '* '.repeat(i + 1);
    console.log(str);
    
  }
  for(let i=n-1; i>=0; i--){
    const str = ' '.repeat(n - i -1) + '* '.repeat(i + 1);
    console.log(str);
  }
}

// 더 좋은 방법 - 코드 중복 처리
function line(n, i){
  const str = ' '.repeat(n - i -1) + '* '.repeat(i + 1);
  console.log(str);
}

function diamond(n){
  for(let i=0; i<n; i++){
    line(n,i);
  }
  for(let i=n-1; i>=0; i--){
    line(n,i);
  }
}
```

### 문제 11

두 수를 입력받아서, 두 수의 최대공약수를 반환하는 함수를 작성하세요. ([유클리드 호제법](https://ko.wikipedia.org/wiki/%EC%9C%A0%ED%81%B4%EB%A6%AC%EB%93%9C_%ED%98%B8%EC%A0%9C%EB%B2%95)을 참고하세요.)

### 문제 12

세 수를 입력받아 큰 것부터 차례대로 출력하는 함수를 작성하세요.
```js
function sort(x,y,z){
  let larger = x > y ? x : y;
  let smaller1 = x > y ? y : x;
  let max = larger > z ? larger : z;
  let smaller2 = larger > z ? z : larger;
  console.log(max);
  if(smaller1 > smaller2){
    console.log(smaller1);
    console.log(smaller2);
  }else{
    console.log(smaller2);
    console.log(smaller1);
  }
}
// 또는 
function compReverse(a,b){
  return b - a;
}

const arr = [];
function sort(x,y,z){
  arr.push(x,y,z);
  arr.sort(compReverse);
  for(let i=0; i<arr.length; i++){
    console.log(arr[i]);
  }
}
```

### 문제 13

자연수 `n`을 입력받아, `n`번째 피보나치 수를 반환하는 함수를 작성하세요.
