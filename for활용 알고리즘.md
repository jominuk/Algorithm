## 문자열 섞기

문제 설명
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

문제 설명
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

문제 설명
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






