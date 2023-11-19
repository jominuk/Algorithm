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

<br/>

## 이어 붙인 수 (forEach, 전개연산자 사)

- 문제 설명
  - 정수가 담긴 리스트 num_list가 주어집니다. num_list의 홀수만 순서대로 이어 붙인 수와 짝수만 순서대로 이어 붙인 수의 합을 return하도록 solution 함수를 완성해주세요.

입출력 예
|num_list|	result|
|-|-|
|[3, 4, 5, 2, 1]	|393|
|[5, 7, 8, 3]	|581|

```jsx
function solution(num) {
    let odd = [];
    let eve = [];
    
    [...num].forEach((e) => {
        if(e % 2 !== 0){
            odd.push(e)
        }else{
            eve.push(e)
        }
    })
    let ood = parseInt([...odd].join(""))
    let eev = parseInt([...eve].join(""))
    
    return ood + eev;
}
```

<br />

## 마지막 두 원소(전개연산자)

- 문제 설명
  - 정수 리스트 num_list가 주어질 때, 마지막 원소가 그전 원소보다 크면 마지막 원소에서 그전 원소를 뺀 값을 마지막 원소가 그전 원소보다 크지 않다면 마지막 원소를 두 배한 값을 추가하여 return하도록 solution 함수를 완성해주세요.

입출력 예
|num_list|	result|
|-|-|
|[2, 1, 6]	|[2, 1, 6, 5]|
|[5, 2, 1, 7, 5]	|[5, 2, 1, 7, 5, 10]|

```jsx
function solution(num_list) {
    var answer = [...num_list];
    let last = num_list[num_list.length-1];
    let last1 = num_list[num_list.length-2];
    
    if(last > last1) {
        answer.push(last - last1)
    }else {
        answer.push(last * 2)
    }
    return answer;
}
```

<br />

## 수 조작하기 1
- 문제 설명
  - 정수 n과 문자열 control이 주어집니다. control은 "w", "a", "s", "d"의 4개의 문자로 이루어져 있으며, control의 앞에서부터 순서대로 문자에 따라 n의 값을 바꿉니다.
"w" : n이 1 커집니다.
"s" : n이 1 작아집니다.
"d" : n이 10 커집니다.
"a" : n이 10 작아집니다.
  - 위 규칙에 따라 n을 바꿨을 때 가장 마지막에 나오는 n의 값을 return 하는 solution 함수를 완성해 주세요.

입출력 예
|n|	control|	result|
|-|-|-|
|0|	"wsdawsdassw"	|-1|

```jsx
function solution(n, control) {
    var answer = 0;
    for(let i=0; i<control.length; i++) {
        if(control[i] === "w"){
            answer = n + 1
        }else if(control[i] === "s"){
            answer = n - 1
        }else if(control[i] === "d"){
            answer = n + 10
        }else{
            answer = n - 10
        }
    }
    return answer;
}

// 위 코드는 잘못된 예제 한번 잘 찾아보고 아래 코드를 확인해볼 것 !


function solution(n, control) {
    var answer = n;
    for(let i=0; i<control.length; i++) {
        if(control[i] === "w"){
            answer += 1
        }else if(control[i] === "s"){
            answer -= 1
        }else if(control[i] === "d"){
            answer += 10
        }else{
            answer -= 10
        }
    }
    return answer;
}
```
https://school.programmers.co.kr/learn/courses/30/lessons/181926


<br/>

## 수 조작하기2( 다시 연습해 )

- 문제 설명
  - 정수 배열 numLog가 주어집니다. 처음에 numLog[0]에서 부터 시작해 "w", "a", "s", "d"로 이루어진 문자열을 입력으로 받아 순서대로 다음과 같은 조작을 했다고 합시다.
"w" : 수에 1을 더한다.
"s" : 수에 1을 뺀다.
"d" : 수에 10을 더한다.
"a" : 수에 10을 뺀다.
  - 그리고 매번 조작을 할 때마다 결괏값을 기록한 정수 배열이 numLog입니다. 즉, numLog[i]는 numLog[0]로부터 총 i번의 조작을 가한 결과가 저장되어 있습니다.
  - 주어진 정수 배열 numLog에 대해 조작을 위해 입력받은 문자열을 return 하는 solution 함수를 완성해 주세요.

입출력 예
|numLog	|result|
|-|-|
|[0, 1, 0, 10, 0, 1, 0, 10, 0, -1, -2, -1]	|"wsdawsdassw"|

```jsx
function solution(numLog) {
    var answer = '';

    for (let i = 1; i < numLog.length; i++) {
        const diff = numLog[i] - numLog[i - 1];

        if (diff === 1) {
            answer += "w";
        } else if (diff === -1) {
            answer += "s";
        } else if (diff === 10) {
            answer += "d";
        } else if (diff === -10) {
            answer += "a";
        }
    }

    return answer;
}
// 풀이과정을 이해 못함
```
https://school.programmers.co.kr/learn/courses/30/lessons/181925

<br/>

## 수열과 구간 쿼리 3(구조분해할당, forEach, 대입연산 )

- 문제 설명
  - 정수 배열 arr와 2차원 정수 배열 queries이 주어집니다. queries의 원소는 각각 하나의 query를 나타내며, [i, j] 꼴입니다.
  - 각 query마다 순서대로 arr[i]의 값과 arr[j]의 값을 서로 바꿉니다.
  - 위 규칙에 따라 queries를 처리한 이후의 arr를 return 하는 solution 함수를 완성해 주세요.

입출력 예
|arr	|queries	|result|
|-|-|-|
|[0, 1, 2, 3, 4]|	[[0, 3],[1, 2],[1, 4]]	|[3, 4, 1, 0, 2]|

```jsx
function solution(arr, queries) {
    var answer = [...arr];
    
    for(let i=0; i<queries.length; i++){
        const [a,b] = queries[i]
        
        let temp = answer[a]
        //for문의 0번째 인덱스인 [0,3]을 시작으로 
        // a인 0을 answer에 0번째 인덱스인 0의 값을 temp에 넣어둔다.
        answer[a] = answer[b]
        // 그리고 0번째 인덱스의 [0,3] 중 3을 answer에 3번째 인덱스인 
        // 3을 answer의 a번째 인덱스였던 0번째 인덱스에 3의 값을 넣는다.
        answer[b] = temp
        // 그리고 answer[b]인 3번째 인덱스자리에 변수를 저장해둔 0의 값을 넣어둔다.
    }
    return answer;
}
// ======================================================================================

function solution(arr, queries) {
    queries.forEach( ([a,b]) => {
        //구조 분해 할당을 활용해서 각각의 요소에 함수를 지정해준다.
        [arr[a],arr[b]] = [arr[b],arr[a]];
        // ' = ' 대입연산자를 통해 a자리와 b자리에 
        // b를 넣고 a를 넣어준다.
    })
    return arr;
}
```

<br/>

## 수열과 구간 쿼리2

- 문제 설명
  - 정수 배열 arr와 2차원 정수 배열 queries이 주어집니다. queries의 원소는 각각 하나의 query를 나타내며, [s, e, k] 꼴입니다.
  - 각 query마다 순서대로 s ≤ i ≤ e인 모든 i에 대해 k보다 크면서 가장 작은 arr[i]를 찾습니다.
  - 각 쿼리의 순서에 맞게 답을 저장한 배열을 반환하는 solution 함수를 완성해 주세요.
  - , 특정 쿼리의 답이 존재하지 않으면 -1을 저장합니다.

입출력 예
|arr	|queries|	result|
|-|-|-|
|[0, 1, 2, 4, 3]|	[[0, 4, 2],[0, 3, 2],[0, 2, 2]]|	[3, 4, -1]|

```jsx
function solution(arr, queries) {
    var answer = [];
    
    for (let i=0; i<queries.length; i++) {
        const [s,e,k] = queries[i]
        const ss = arr.slice(s, e+1)
        const result = ss.filter((e) => e > k).sort((a,b) => a-b)[0]
        
        answer.push(result !== undefined ? result : -1) 
    }
    return answer;
}
```

<br/>

## 수열과 구간 쿼리4 (reduce 활용 )

- 문제 설명
  - 정수 배열 arr와 2차원 정수 배열 queries이 주어집니다. queries의 원소는 각각 하나의 query를 나타내며, [s, e, k] 꼴입니다.
  - 각 query마다 순서대로 s ≤ i ≤ e인 모든 i에 대해 i가 k의 배수이면 arr[i]에 1을 더합니다.
  - 위 규칙에 따라 queries를 처리한 이후의 arr를 return 하는 solution 함수를 완성해 주세요.

입출력 예
|arr|	queries	|result|
|-|-|-|
|[0, 1, 2, 4, 3]|	[[0, 4, 1],[0, 3, 2],[0, 3, 3]]|	[3, 2, 4, 6, 4]|

```jsx
function solution(arr, queries) {    
    for(let i=0; i<queries.length; i++) {
        const [s,e,k] = queries[i];
// 이전 문제들과 다른점이라면 기존에 배열을 자르는게 아닌 조건에 맞는 인덱스 애들만 더해준다.
        for(let j=s; j<=e; j++){
            if(j % k === 0){
                arr[j] += 1
            }
        }
    }
    return arr;
}

// ===========================================
function solution(arr, queries) {
    return queries.reduce((bucket, [s,e,k]) => {
// 2. 초기값으로 사용한 배열은 bucket이라는 이름으로 콜백 함수 내부에서 사용하게 된다.
// 3. 첫번 째 매개변수에는 bucket이며, 현재까지의 결과를 나타낸다.
// 4. 두번 째 매개변수에는 비구조화 할당을 사용해서 순회중인 queires의[s,e,k]의 요소를 나타낸다.
// 5. 이제 for문을 통한 조건식을 만들어 조건에 맞는 값들은 buvket에 +1씩 해준다 즉 ...arr의 복사해둔 배열에 조건에 맞는 인덱스의 값을 +1 해준다.
        for(let i=s; i<=e; i++){
            if(i % k === 0){
                bucket[i] += 1
            }
        }
        return bucket
// 1. reduce함수의 초기값을 전개 연산자를 사용해서 배열을 복사해준다.
    }, [...arr])
}
```



