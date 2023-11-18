## 문자열 섞기

- 문제 설명
  - 길이가 같은 두 문자열 str1과 str2가 주어집니다.
  - 두 문자열의 각 문자가 앞에서부터 서로 번갈아가면서 한 번씩 등장하는 문자열을 만들어 return 하는 solution 함수를 완성해 주세요.

입출력

|str1	| str2	| result |
|-----|---| ------    |
|"aaaaa"	|"bbbbb"|	"ababababab"|

```javascript
function solution(str1, str2) {
    var answer = '';
    for(let i=0; i<str1.length; i++){
        answer += str1[i]+str2[i]
        // 다음과 같이 작성했을 때 str1의 0번째 인덱스와 str2의 0번째 인덱스가
        // 문자열 연결 연산자를 통해 answer에 넣게 되면 ab이렇게 넣어지게 된다.
        // 이게 str1의 길이만큼 반복하게 된다.
    }
    return answer;
}
```

<br/>

## 문자열 곱하기

- 문제 설명
- 문자열 my_string과 정수 k가 주어질 때, my_string을 k번 반복한 문자열을 return 하는 solution 함수를 작성해 주세요.

입출력 예
|my_string	|k|	result|
|-------    |-|------|
|"string"   |3 |	"stringstringstring"|
|"love"|	10|	"lovelovelovelovelovelovelovelovelovelove"|

```jsx
function solution(my_string, k) {
    var answer = '';
    for (let i=0; i<k; i++){
        answer += my_string
    }
    return answer;
}
// 비록 repeat 메서드를 활용해서 충분히 풀 수 있는 문제이지만 나는 for문을 완전 정복을 위해서...
```

<br/>

## 홀짝에 따라 다른 값 반환하기

- 문제 설명
  - 양의 정수 n이 매개변수로 주어질 때, n이 홀수라면 n 이하의 홀수인 모든 양의 정수의 합을 return 하고 n이 짝수라면 n 이하의 짝수인 모든 양의 정수의 제곱의 합을 return 하는 solution 함수를 작성해 주세요.

입출력 예
|n|	result|
|-|-|
|7|	16|
|10|	220|

```jsx
function solution(n) {
    var answer = 0;
    if(n%2===1){
        for(let i=1; i<=n; i+=2){
            answer += i
        }
    }else {
        for(let i=2; i<=n; i+=2){
            answer += i * i
        }
    }
    return answer;
}
```

<br/>

## 조건 문자열
- 문제 설명
  - 문자열에 따라 다음과 같이 두 수의 크기를 비교하려고 합니다.

두 수가 n과 m이라면
">", "=" : n >= m
"<", "=" : n <= m
">", "!" : n > m
"<", "!" : n < m
두 문자열 ineq와 eq가 주어집니다. ineq는 "<"와 ">"중 하나고, eq는 "="와 "!"중 하나입니다. 그리고 두 정수 n과 m이 주어질 때, n과 m이 ineq와 eq의 조건에 맞으면 1을 아니면 0을 return하도록 solution 함수를 완성해주세요.

입출력 예
|ineq|	eq|	n	|m	|result|
|-|-|-|-|-|
|"<"|	"="|	20|	50|	1|
|">"|	"!"|	41|	78|	0|

```jsx
function solution(ineq, eq, n, m) {
    if (eq === '=' && n === m) return 1
    if (ineq === '<' && n < m) return 1
    if (ineq === '>' && n > m) return 1
    return 0
}
```

<br/>

## 등차수열의 특정한 항만 더하기
- 문제 설명
  - 두 정수 a, d와 길이가 n인 boolean 배열 included가 주어집니다. 첫째항이 a, 공차가 d인 등차수열에서 included[i]가 i + 1항을 의미할 때, 이 등차수열의 1항부터 n항까지 included가 true인 항들만 더한 값을 return 하는 solution 함수를 작성해 주세요.


입출력 예
|a	|d	|included	|result|
|-|-|-|-|
|3	|4|	[true, false, false, true, true]|	37|
|7	|1|	[false, false, false, true, false, false, false]|	10|

```jsx
function solution(a, d, included) {
    var answer = 0;
    for (let i = 0; i < included.length; i++) {
        if (included[i]) {
            answer += a + i * d;
        }
    }
    return answer;
}
```
























