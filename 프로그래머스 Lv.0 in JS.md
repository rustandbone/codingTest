### 10/224  

문제:   
두 수의 차  

문제 설명:   
정수 num1과 num2가 주어질 때, num1에서 num2를 뺀 값을 return하도록 solution 함수를 완성해주세요.  

입출력 예  
| num1 | num2 | result |
| :-: | :-: | :-: |
| 2 | 3 | -1  |
| 100|  2 | 98 |  

solution.js:  
```javascript
function solution(num1, num2) { 
     return num1 - num2;
}
```
  
---

문제:  
나머지 구하기  

설명:  
정수 num1, num2가 매개변수로 주어질 때, num1를 num2로 나눈 나머지를 return 하도록 solution 함수를 완성해주세요.  

입출력 예  
| num1 | num2 | result |  
| :-: | :-: | :-: |
| 3 | 2 | 1 | 
| 10 | 5 | 0 |

solution.js:
```javascript
function solution(num1, num2) {
    return num1 % num2;
}
```

---

문제:  
숫자 비교하기  

설명:  
정수 num1과 num2가 매개변수로 주어집니다. 두 수가 같으면 1 다르면 -1을 retrun하도록 solution 함수를 완성해주세요.  

입출력 예  
| num1 | num2 | result |  
| :-: | :-: | :-: |
| 2 | 3 | -1 |  
| 11 | 11 | 1 |  
| 7 | 99 | -1 |  

solution.js:
```javascript
function solution(num1, num2) {
    return num1 === num2 ? 1 : -1;
}
```

---

문제:  
몫 구하기  

문제 설명:  
정수 num1, num2가 매개변수로 주어질 때, num1을 num2로 나눈 몫을 return 하도록 solution 함수를 완성해주세요.  

입출력 예  
| num1 | num2 | result |  
| :-: | :-: | :-: |
| 10 | 5 | 2 |  
| 7 | 2 | 3 | 

solution.js:
```javascript
function solution(num1, num2) {
    return  parseInt(num1 / num2);
}
```

---

문제:  
두 수의 곱  

설명:  
정수 num1, num2가 매개변수 주어집니다. num1과 num2를 곱한 값을 return 하도록 solution 함수를 완성해주세요.  

입출력 예  
| num1 | num2 | result |  
| :-: | :-: | :-: |
| 3 | 4 | 12 |  
| 27 | 19 | 513 |  

solution.js:
```javascript
function solution(num1, num2) {
    return num1 * num2;
}
```

---

문제:  
나이 출력  

설명:  
머쓱이는 40살인 선생님이 몇 년도에 태어났는지 궁금해졌습니다. 나이 age가 주어질 때, 2022년을 기준 출생 연도를 return 하는 solution 함수를 완성해주세요.  

입출력 예  
| age | result |  
| :-: | :-: |
| 40 | 1983 |  
| 23 | 2000 |  

solution.js:
```javascript
function solution(age) {
    return (2022 - age) + 1;
}
```

---

문제:  
두 수의 합  

설명:  
정수 num1과 num2가 주어질 때, num1과 num2의 합을 return하도록 soltuion 함수를 완성해주세요.  

입출력 예  
| num1 | num2 | result | 
| :-: | :-: | :-: |
| 2 | 3 | 5 | 
| 100 | 2 | 102 | 

solution.js:
```javascript
function solution(num1, num2) {
    return num1 + num2;
}
```

---

문제:   
두 수의 나눗셈  

설명:  
정수 num1과 num2가 매개변수로 주어질 때, num1을 num2로 나눈 값에 1,000을 곱한 후 정수 부분을 return 하도록 soltuion 함수를 완성해주세요.  

입출력 예  
| num1 | num2 | result | 
| :-: | :-: | :-: |
| 3 | 2 | 1500 |  
| 7 | 3 | 2333 |  
| 1 | 16 | 62 | 

solution.js: 
```javascript
function solution(num1, num2) {
    return parseInt(num1 / num2 * 1000);
}
```

---

문제:  
각도기  

설명:   
각에서 0도 초과 90도 미만은 예각, 90도는 직각, 90도 초과 180도 미만은 둔각 180도는 평각으로 분류합니다. 각 angle이 매개변수로 주어질 때 예각일 때 1, 직각일 때 2, 둔각일 때 3, 평각일 때 4를 return하도록 solution 함수를 완성해주세요.  

예각 : 0 < angle < 90  
직각 : angle = 90  
둔각 : 90 < angle < 180  
평각 : angle = 180  

입출력 예  
| angle | result |
| :-: | :-: |
| 70 | 1 |
| 91 | 3 |
| 180 | 4 |  

solution.js:
```javascript
function solution(angle) {
    var answer = 0;
    if(angle < 90) answer = 1;
    else if(angle === 90) answer = 2;
    else if(angle < 180) answer = 3;
    else answer = 4;
    return answer;
}
```

---

문제:  
짝수의 합  

설명:  
정수 n이 주어질 때, n이하의 짝수를 모두 더한 값을 return 하도록 solution 함수를 작성해주세요.  

입출력 예  
| n | result |
| :-: | :-: |
| 10 | 30 |  
| 4 | 6 | 

solution.js:
```javascript
function solution(n) {
    var answer = 0;
    for(let i = 1; i <= n; i++) {
        i % 2 === 0 ? answer += i : answer;
    }
    return answer;
}
```
