### 1~20 of 224  

1. [편지](#편지)
2. [배열 뒤집기](#배열-뒤집기)
3. [배열 원소의 길이](#배열-원소의-길이)
4. [삼각형의 완성조건 (1)](#삼각형의-완성조건-1)
5. [모음 제거](#모음-제거)
6. [피자 나눠 먹기 (1)](#피자-나눠-먹기-1)
7. [짝수 홀수 개수](#짝수-홀수-개수)
8. [배열 자르기](#배열-자르기)
9. [양꼬치](#양꼬치)
10. [배열의 평균값](#배열의-평균값)
11. [짝수의 합](#짝수의-합)
12. [각도기](#각도기)
13. [두 수의 나눗셈](#두-수의-나눗셈)
14. [두 수의 합](#두-수의-합)
15. [나이 출력](#나이-출력)
16. [두 수의 곱](#두-수의-곱)
17. [몫 구하기](#몫-구하기)
18. [숫자 비교하기](#숫자-비교하기)
19. [나머지 구하기](#나머지-구하기)
20. [두 수의 차](#두-수의-차)

---

문제 :  


설명 :  


입출력 예  
|   |   |   |
| :-: | :-: | :-: |
|   |   |   |
|   |   |   |

solution.js:
```javascript

```

---

문제 :  
#### 편지  

설명 :  
머쓱이는 할머니께 생신 축하 편지를 쓰려고 합니다. 할머니가 보시기 편하도록 글자 한 자 한 자를 가로 2cm 크기로 적으려고 하며, 편지를 가로로만 적을 때, 축하 문구 message를 적기 위해 필요한 편지지의 최소 가로길이를 return 하도록 solution 함수를 완성해주세요.

입출력 예  
| message | result |
| :-: | :-: |
| "happy birthday!" | 30 |
| "I love you~" | 22 |

solution.js:
```javascript
function solution(message) {
    return message.length * 2;
}
```

---

문제 :  
#### 배열 뒤집기  

설명 :  
정수가 들어 있는 배열 num_list가 매개변수로 주어집니다. num_list의 원소의 순서를 거꾸로 뒤집은 배열을 return하도록 solution 함수를 완성해주세요.

입출력 예  
| num_list | result |
| :-: | :-: | 
| [1, 2, 3, 4, 5] | [5, 4, 3, 2, 1] |
| [1, 1, 1, 1, 1, 2] | [2, 1, 1, 1, 1, 1] |
| [1, 0, 1, 1, 1, 3, 5] | [5, 3, 1, 1, 1, 0, 1] |

solution.js:
```javascript
function solution(num_list) {
    return num_list.reverse();
}
```

---

문제 :  
#### 배열 원소의 길이  

설명 :  
문자열 배열 strlist가 매개변수로 주어집니다. strlist 각 원소의 길이를 담은 배열을 retrun하도록 solution 함수를 완성해주세요.

입출력 예  
| strlist | result | 
| :-: | :-: |
| ["We", "are", "the", "world!"] | [2, 3, 3, 6] |
| ["I", "Love", "Programmers."] | [1, 4, 12] | 

solution.js:
```javascript
function solution(strlist) {
    return strlist.map((str) => str.length);
}
```

---

문제 :  
#### 삼각형의 완성조건 (1)  

설명 :  
선분 세 개로 삼각형을 만들기 위해서는 다음과 같은 조건을 만족해야 합니다.  
- 가장 긴 변의 길이는 다른 두 변의 길이의 합보다 작아야 합니다.  

삼각형의 세 변의 길이가 담긴 배열 sides이 매개변수로 주어집니다. 세 변으로 삼각형을 만들 수 있다면 1, 만들 수 없다면 2를 return하도록 solution 함수를 완성해주세요.

입출력 예  
| sides | result |
| :-: | :-: | 
| [1, 2, 3] | 2 |
| [3, 6, 2] | 2 |
| [199, 72, 222] | 1 |

solution.js:
```javascript
function solution(sides) {
    sides.sort((a,b) => a - b);
    return sides[0] + sides[1] > sides[2] ? 1 : 2;
}
```

---

문제 :  
#### 모음 제거  

설명 :  
영어에선 a, e, i, o, u 다섯 가지 알파벳을 모음으로 분류합니다. 문자열 my_string이 매개변수로 주어질 때 모음을 제거한 문자열을 return하도록 solution 함수를 완성해주세요.

입출력 예  
| my_string | result |
| :-: | :-: |
| "bus" | "bs" |
| "nice to meet you" | "nc t mt y" |

solution.js:
```javascript
function solution(my_string) {
    var answer = '';
    let vowel = 'aeiou'
    my_string.split('').filter((str) => {
        if(!vowel.includes(str)) answer += str;
    });
    return answer;
}
```

---

문제 :  
#### 피자 나눠 먹기 (1)  

설명 :  
머쓱이네 피자가게는 피자를 일곱 조각으로 잘라 줍니다. 피자를 나눠먹을 사람의 수 n이 주어질 때, 모든 사람이 피자를 한 조각 이상 먹기 위해 필요한 피자의 수를 return 하는 solution 함수를 완성해보세요.

입출력 예  
| n | result |
| :-: | :-: | 
| 7 | 1 |
| 1 | 1 |
| 15 | 3 |

solution.js:
```javascript
function solution(n) {
    return Math.ceil(n/7);
}
```

---

문제 :  
#### 짝수 홀수 개수  

설명 :  
정수가 담긴 리스트 num_list가 주어질 때, num_list의 원소 중 짝수와 홀수의 개수를 담은 배열을 return 하도록 solution 함수를 완성해보세요.

입출력 예  
| num_list | result | 
| :-: | :-: |
| [1, 2, 3, 4, 5] | [2, 3] |
| [1, 3, 5, 7] | [0, 4] |

solution.js:
```javascript
function solution(num_list) {
    var answer = [0,0];
    num_list.map((a) => {
        if(a%2 === 0) answer[0]++;
        else answer[1]++;
    })
    return answer;
}
```

---

문제 :  
#### 배열 자르기  

설명 :  
정수 배열 numbers와 정수 num1, num2가 매개변수로 주어질 때, numbers의 num1번 째 인덱스부터 num2번째 인덱스까지 자른 정수 배열을 return 하도록 solution 함수를 완성해보세요.

입출력 예  
| numbers | num1 | num2 | result |
| :-: | :-: | :-: | :-: |
|[1, 2, 3, 4, 5] | 1 | 3 | [2, 3, 4] |
| [1, 3, 5] | 1 | 2 | [3, 5] |

solution.js:
```javascript
function solution(numbers, num1, num2) {
    return numbers.slice(num1, num2 + 1);
}
```

---

문제 :  
#### 양꼬치

설명 :  
머쓱이네 양꼬치 가게는 10인분을 먹으면 음료수 하나를 서비스로 줍니다. 양꼬치는 1인분에 12,000원, 음료수는 2,000원입니다. 정수 n과 k가 매개변수로 주어졌을 때, 양꼬치 n인분과 음료수 k개를 먹었다면 총얼마를 지불해야 하는지 return 하도록 solution 함수를 완성해보세요.

입출력 예  
| n | k | result |
| :-: | :-: | :-: |
| 10	| 3 | 124,000 |
| 64	| 6 | 768,000 |

solution.js:
```javascript
function solution(n, k) {
    return (n * 12000) + (k * 2000) - (parseInt(n/10) * 2000);
}
```

---

문제 :  
#### 배열의 평균값

설명 :  
정수 배열 numbers가 매개변수로 주어집니다. numbers의 원소의 평균값을 return하도록 solution 함수를 완성해주세요.

입출력 예  
| numbers | result |
| :-: | :-: |
| [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]	| 5.5 |
| [89, 90, 91, 92, 93, 94, 95, 96, 97, 98, 99] | 94.0 |

solution.js:
```javascript
function solution(numbers) {
    return (numbers.reduce((acc, cur) => (acc + cur), 0)) / numbers.length;
}
```

---

문제:  
#### 짝수의 합  

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

---

문제:  
#### 각도기  

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
#### 두 수의 나눗셈  

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
#### 두 수의 합  

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
#### 나이 출력  

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
#### 두 수의 곱  

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
#### 몫 구하기  

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
#### 숫자 비교하기  

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
#### 나머지 구하기  

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
#### 두 수의 차  

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
