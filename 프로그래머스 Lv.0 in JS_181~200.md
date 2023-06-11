### 181~200 of 224  

1.	[문자 개수 세기](#문자-개수-세기)
2.	[리스트 자르기](#리스트-자르기)
3.	[배열 만들기 4](#배열-만들기-4)
4.	[조건 문자열](#조건-문자열)
5.	[두 수의 합](#두-수의-합)
6.	[a와 b 출력하기](#a와-b-출력하기)
7.	[문자열 겹쳐쓰기](#문자열-겹쳐쓰기)
8.	[수열과 구간 쿼리 2](#수열과-구간-쿼리-2)
9.	[왼쪽 오른쪽](#왼쪽-오른쪽)
10.	[무작위로 K개의 수 뽑기](#무작위로-K개의-수-뽑기)
11.	[문자열 여러 번 뒤집기](#문자열-여러-번-뒤집기)
12.	[대소문자 바꿔서 출력하기](#대소문자-바꿔서-출력하기)
13.	[그림 확대](#그림-확대)
14.	[배열 만들기 6](#배열-만들기-6)
15.	[배열 만들기 2](#배열-만들기-2)
16.	[코드 처리하기](#코드-처리하기)
17.	[문자열 출력하기](#문자열-출력하기)
18.	[외계어 사전](#외계어-사전)
19.	[직사각형 넓이 구하기](#직사각형-넓이-구하기)
20.	[종이 자르기](#종이-자르기)

---

문제 :  
#### 

설명 :  


입출력 예  
|  |  |  |
| :-: | :-: | :-: |
|  |  |  |
|  |  |  |

solution.js:
```javascript

```

---

문제 :  
#### 문자 개수 세기

설명 :  
알파벳 대소문자로만 이루어진 문자열 my_string이 주어질 때, my_string에서 'A'의 개수, my_string에서 'B'의 개수,..., my_string에서 'Z'의 개수, my_string에서 'a'의 개수, my_string에서 'b'의 개수,..., my_string에서 'z'의 개수를 순서대로 담은 길이 52의 정수 배열을 return 하는 solution 함수를 작성해 주세요.

입출력 예  
| my_string | result | 
| :-: | :-: |
| "Programmers" | [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 1, 0, 0, 0, 1, 0, 1, 0, 0, 0, 0, 0, 2, 0, 1, 0, 0, 3, 1, 0, 0, 0, 0, 0, 0, 0] |

solution.js:
```javascript
function solution(my_string) {
    var answer = Array.from({length: 52}, () => 0);
    let big = Array(26).fill().map((v, i) => String.fromCharCode(i + 65));
    let small = Array(26).fill().map((v, i) => String.fromCharCode(i + 97));
    let alpha = [...big, ...small];
    for(let str of my_string) {
        for(let [index, arr] of alpha.entries()) {
            if(str === arr) answer[index]++;
        }
    }
    return answer;
}
```

---

문제 :  
#### 리스트 자르기

설명 :  
정수 n과 정수 3개가 담긴 리스트 slicer 그리고 정수 여러 개가 담긴 리스트 num_list가 주어집니다. slicer에 담긴 정수를 차례대로 a, b, c라고 할 때, n에 따라 다음과 같이 num_list를 슬라이싱 하려고 합니다.

- n = 1 : num_list의 0번 인덱스부터 b번 인덱스까지
- n = 2 : num_list의 a번 인덱스부터 마지막 인덱스까지
- n = 3 : num_list의 a번 인덱스부터 b번 인덱스까지
- n = 4 : num_list의 a번 인덱스부터 b번 인덱스까지 c 간격으로

올바르게 슬라이싱한 리스트를 return하도록 solution 함수를 완성해주세요.

입출력 예  
| n | slicer | num_list | result |
| :-: | :-: | :-: | :-: |
| 3 | [1, 5, 2] | [1, 2, 3, 4, 5, 6, 7, 8, 9] | [2, 3, 4, 5, 6] |
| 4 | [1, 5, 2] | [1, 2, 3, 4, 5, 6, 7, 8, 9] | [2, 4, 6] |

solution.js:
```javascript
function solution(n, slicer, num_list) {
    var answer = [];
    if(n == 1) {
        answer = num_list.slice(0, slicer[1]+1);
    } else if(n == 2) {
        answer = num_list.slice(slicer[0]);
    } else if(n == 3) {
        answer = num_list.slice(slicer[0], slicer[1]+1);
    } else {
        for(let i = slicer[0]; i <= slicer[1]; i += slicer[2]) {
            answer.push(num_list[i]);
        }
    }
    return answer;
}
```

---

문제 :  
#### 배열 만들기 4

설명 :  
정수 배열 arr가 주어집니다. arr를 이용해 새로운 배열 stk를 만드려고 합니다.  
변수 i를 만들어 초기값을 0으로 설정한 후 i가 arr의 길이보다 작으면 다음 작업을 반복합니다.  

- 만약 stk가 빈 배열이라면 arr[i]를 stk에 추가하고 i에 1을 더합니다.
- stk에 원소가 있고, stk의 마지막 원소가 arr[i]보다 작으면 arr[i]를 stk의 뒤에 추가하고 i에 1을 더합니다.
- stk에 원소가 있는데 stk의 마지막 원소가 arr[i]보다 크거나 같으면 stk의 마지막 원소를 stk에서 제거합니다.

위 작업을 마친 후 만들어진 stk를 return 하는 solution 함수를 완성해 주세요.

입출력 예  
| arr | result |
| :-: | :-: |
| [1, 4, 2, 5, 3] | [1, 2, 3] |

solution.js:
```javascript
function solution(arr) {
    var stk = [];
    let i = 1;
    stk.push(arr[0]);
    while(i < arr.length) {
        if(stk.length === 0) {
            stk.push(arr[i]);
            i++;
        }
        else if(arr[i] > stk.at(-1)) {
            stk.push(arr[i]);
            i++;
        }
        else {
            stk.pop();
        };
    } 
    return stk;
}
```

---

문제 :  
#### 조건 문자열

설명 :  
문자열에 따라 다음과 같이 두 수의 크기를 비교하려고 합니다.

- 두 수가 n과 m이라면
- ">", "=" : n >= m
- "<", "=" : n <= m
- ">", "!" : n > m
- "<", "!" : n < m

두 문자열 ineq와 eq가 주어집니다. ineq는 "<"와 ">"중 하나고, eq는 "="와 "!"중 하나입니다. 그리고 두 정수 n과 m이 주어질 때, n과 m이 ineq와 eq의 조건에 맞으면 1을 아니면 0을 return하도록 solution 함수를 완성해주세요.

입출력 예  
| ineq | eq | n | m | result |
| :-: | :-: | :-: | :-: | :-: |
| "<" | "=" | 20 | 50 | 1 |
| ">" | "!" | 41 | 78 | 0 |

solution.js:
```javascript
function solution(ineq, eq, n, m) {
    var answer = 0;
    if(eq === '=') {
        if(ineq === ">" && n >= m) answer = 1
        else if(ineq === "<" && n <= m) answer = 1
        else answer = 0
    } else {
        if(ineq === ">" && n > m) answer = 1
        else if(ineq === "<" && n < m) answer = 1
        else answer = 0
    }
    return answer;
}
```

---

문제 :  
#### 두 수의 합

설명 :  
0 이상의 두 정수가 문자열 a, b로 주어질 때, a + b의 값을 문자열로 return 하는 solution 함수를 작성해 주세요.

입출력 예  
| a | b | result |
| :-: | :-: | :-: |
| "582" | "734" | "1316" |
| "18446744073709551615" | "287346502836570928366" | "305793246910280479981" |
| "0" | "0" | "0" |

solution.js:
```javascript
function solution(a, b) {
    return String(BigInt(a) + BigInt(b));
}
```

---

문제 :  
#### a와 b 출력하기

설명 :  
정수 a와 b가 주어집니다. 각 수를 입력받아 입출력 예와 같은 형식으로 출력하는 코드를 작성해 보세요.

입출력 예  
| 입력 | 출력 |
| :-: | :-: |
| 4 5 | a = 4| 
|  | b = 5 |

solution.js:
```javascript
const readline = require('readline');
const rl = readline.createInterface({
    input: process.stdin,
    output: process.stdout
});

let input = [];

rl.on('line', function (line) {
    input = line.split(' ');
}).on('close', function () {
    console.log(`a = ${Number(input[0])}\nb = ${Number(input[1])}`);
});
```

---

문제 :  
#### 문자열 겹쳐쓰기

설명 :  
문자열 my_string, overwrite_string과 정수 s가 주어집니다. 문자열 my_string의 인덱스 s부터 overwrite_string의 길이만큼을 문자열 overwrite_string으로 바꾼 문자열을 return 하는 solution 함수를 작성해 주세요.

입출력 예  
| my_string | overwrite_string | s | result |
| :-: | :-: | :-: | :-: |
| "He11oWor1d" | "lloWorl" | 2 | "HelloWorld" |
| "Program29b8UYP" | "merS123" | 7 | "ProgrammerS123" |

solution.js:
```javascript
function solution(my_string, overwrite_string, s) {
    var answer = '';
    let array = my_string.split('')
    array.splice(s, overwrite_string.length, overwrite_string)
    answer = array.join('')
    return answer;
}
```

---

문제 :  
#### 수열과 구간 쿼리 2

설명 :  
정수 배열 arr와 2차원 정수 배열 queries이 주어집니다. queries의 원소는 각각 하나의 query를 나타내며, [s, e, k] 꼴입니다.  
각 query마다 순서대로 s ≤ i ≤ e인 모든 i에 대해 k보다 크면서 가장 작은 arr[i]를 찾습니다.  
각 쿼리의 순서에 맞게 답을 저장한 배열을 반환하는 solution 함수를 완성해 주세요.  
단, 특정 쿼리의 답이 존재하지 않으면 -1을 저장합니다.

입출력 예  
| arr | queries | result |
| :-: | :-: | :-: |
| [0, 1, 2, 4, 3] | [[0, 4, 2],[0, 3, 2],[0, 2, 2]] | [3, 4, -1] |

solution.js:
```javascript
function solution(arr, queries) {
    var array = [];
    let result =[];
    let answer = [];
    
    for(let i = 0; i < queries.length; i++) {
        array[i] = arr.slice(queries[i][0], queries[i][1]+1);
        result[i] = array[i].sort((a,b) => a - b).filter(a => a > queries[i][2]);
    }
    
    for(let j in result) {
        answer.push(result[j][0]);
        if(answer[j] === undefined) answer[j] = -1;
    }
    
    return answer;
}
```

---

문제 :  
#### 왼쪽 오른쪽

설명 :  
문자열 리스트 str_list에는 "u", "d", "l", "r" 네 개의 문자열이 여러 개 저장되어 있습니다. str_list에서 "l"과 "r" 중 먼저 나오는 문자열이 "l"이라면 해당 문자열을 기준으로 왼쪽에 있는 문자열들을 순서대로 담은 리스트를, 먼저 나오는 문자열이 "r"이라면 해당 문자열을 기준으로 오른쪽에 있는 문자열들을 순서대로 담은 리스트를 return하도록 solution 함수를 완성해주세요. "l"이나 "r"이 없다면 빈 리스트를 return합니다.

입출력 예  
| str_list | result |
| :-: | :-: | 
| ["u", "u", "l", "r"] | ["u", "u"] |
| ["l"] | [] |

solution.js:
```javascript
function solution(str_list) {
    if(!str_list.includes("l") && !str_list.includes("r")) return [];
    
    if(str_list.includes("l") && str_list.includes("r")) {
        if(str_list.indexOf("l") < str_list.indexOf("r")) return str_list.slice(0, str_list.indexOf("l"));
        else return str_list.slice(str_list.indexOf("r") + 1);
    }
    else {
        if(str_list.indexOf("l") > -1) return str_list.slice(0, str_list.indexOf("l"));
        else return str_list.slice(str_list.indexOf("r") + 1);
    }
}
```

---

문제 :  
#### 무작위로 K개의 수 뽑기

설명 :  
랜덤으로 서로 다른 k개의 수를 저장한 배열을 만드려고 합니다. 적절한 방법이 떠오르지 않기 때문에 일정한 범위 내에서 무작위로 수를 뽑은 후, 지금까지 나온적이 없는 수이면 배열 맨 뒤에 추가하는 방식으로 만들기로 합니다.  
이미 어떤 수가 무작위로 주어질지 알고 있다고 가정하고, 실제 만들어질 길이 k의 배열을 예상해봅시다.  
정수 배열 arr가 주어집니다. 문제에서의 무작위의 수는 arr에 저장된 순서대로 주어질 예정이라고 했을 때, 완성될 배열을 return 하는 solution 함수를 완성해 주세요.  
단, 완성될 배열의 길이가 k보다 작으면 나머지 값을 전부 -1로 채워서 return 합니다.

입출력 예  
| arr | k | result |
| :-: | :-: | :-: |
| [0, 1, 1, 2, 2, 3] | 3 | [0, 1, 2] |
| [0, 1, 1, 1, 1] | 4 | [0, 1, -1, -1] |

solution.js:
```javascript
function solution(arr, k) {
    var answer = [];
    for(let a of arr) {
        if(!answer.includes(a)) answer.push(a);
        if(answer.length === k) break; 
    }
    if(answer.length < k) {
        let num = k-answer.length;
        for(let i = 0; i < num; i++) {
            answer.push(-1)            
        }
    }
    return answer;
}
```

---

문제 :  
#### 문자열 여러 번 뒤집기

설명 :  
문자열 my_string과 이차원 정수 배열 queries가 매개변수로 주어집니다. queries의 원소는 [s, e] 형태로, my_string의 인덱스 s부터 인덱스 e까지를 뒤집으라는 의미입니다. my_string에 queries의 명령을 순서대로 처리한 후의 문자열을 return 하는 solution 함수를 작성해 주세요.

입출력 예  
| my_string | queries | result |
| :-: | :-: | :-: |
| "rermgorpsam" | [[2, 3], [0, 7], [5, 9], [6, 10]] | "programmers" |

solution.js:
```javascript
function solution(my_string, queries) {
    var answer = '';
    my_string = my_string.split("")
    for(let q of queries) {
        my_string.splice(q[0], q[1]+1-q[0], my_string.slice(q[0], q[1]+1).reverse());
        my_string = my_string.flat();
    }
    return my_string.join('');
}
```

---

문제 :  
#### 대소문자 바꿔서 출력하기

설명 :  
영어 알파벳으로 이루어진 문자열 str이 주어집니다. 각 알파벳을 대문자는 소문자로 소문자는 대문자로 변환해서 출력하는 코드를 작성해 보세요.

입출력 예  
| 입력 | 출력 |
| :-: | :-: |
| aBcDeFg | AbCdEfG |

solution.js:
```javascript
const readline = require('readline');
const rl = readline.createInterface({
    input: process.stdin,
    output: process.stdout
});

let input = [];

rl.on('line', function (line) {
    input = [line];
}).on('close',function(){
    str = input[0];
    let answer = ''
    for(let s of str) {
        if(s === s.toUpperCase()) answer += s.toLowerCase()
        else answer += s.toUpperCase();
    }
    console.log(answer);
});
```

---

문제 :  
#### 그림 확대

설명 :  
직사각형 형태의 그림 파일이 있고, 이 그림 파일은 1 × 1 크기의 정사각형 크기의 픽셀로 이루어져 있습니다. 이 그림 파일을 나타낸 문자열 배열 picture과 정수 k가 매개변수로 주어질 때, 이 그림 파일을 가로 세로로 k배 늘린 그림 파일을 나타내도록 문자열 배열을 return 하는 solution 함수를 작성해 주세요.

입출력 예  
| picture | k | result |
| :-: | :-: | :-: |
| [".xx...xx.", "x..x.x..x", "x...x...x", ".x.....x.", "..x...x..", "...x.x...", "....x...."] | 2 | ["..xxxx......xxxx..", "..xxxx......xxxx..", "xx....xx..xx....xx", "xx....xx..xx....xx", "xx......xx......xx", "xx......xx......xx", "..xx..........xx..", "..xx..........xx..", "....xx......xx....", "....xx......xx....", "......xx..xx......", "......xx..xx......", "........xx........", "........xx........"]
["x.x", ".x.", "x.x"] | 3 | ["xxx...xxx", "xxx...xxx", "xxx...xxx", "...xxx...", "...xxx...", "...xxx...", "xxx...xxx", "xxx...xxx", "xxx...xxx"] |

solution.js:
```javascript
function solution(picture, k) {
    var answer = [];
    let temp = '';

    for(let p of picture) {
        for(let i = 0; i < p.length; i++) {
            temp += p[i].repeat(k);
        }
        for(let j = 0; j < k; j++) {
            answer.push(temp);
        }
        temp = '';
    }
    
    return answer;
}
```

---

문제 :  
#### 배열 만들기 6

설명 :  
0과 1로만 이루어진 정수 배열 arr가 주어집니다. arr를 이용해 새로운 배열 stk을 만드려고 합니다.  
i의 초기값을 0으로 설정하고 i가 arr의 길이보다 작으면 다음을 반복합니다.  

- 만약 stk이 빈 배열이라면 arr[i]를 stk에 추가하고 i에 1을 더합니다.
- stk에 원소가 있고, stk의 마지막 원소가 arr[i]와 같으면 stk의 마지막 원소를 stk에서 제거하고 i에 1을 더합니다.  
- stk에 원소가 있는데 stk의 마지막 원소가 arr[i]와 다르면 stk의 맨 마지막에 arr[i]를 추가하고 i에 1을 더합니다.

위 작업을 마친 후 만들어진 stk을 return 하는 solution 함수를 완성해 주세요.  
단, 만약 빈 배열을 return 해야한다면 [-1]을 return 합니다.

입출력 예  
| arr | result |
| :-: | :-: | 
| [0, 1, 1, 1, 0] | [0, 1, 0] |
| [0, 1, 0, 1, 0] | [0, 1, 0, 1, 0] |
| [0, 1, 1, 0] | [-1] |

solution.js:
```javascript
function solution(arr) {
    var answer = [];
    for(let i = 0; i < arr.length; i++) {
        if(answer.length === 0) {
            answer.push(arr[i]);
            continue;
        };
        
        if(answer.length !== 0) {
           if(answer.at(-1) === arr[i]) {
               answer.pop();
               continue;
           } else {
               answer.push(arr[i]);
               continue;
           }
        }
        answer.push(arr[i]);
    }
    
    return answer.length === 0 ? [-1] : answer;
}
```

---

문제 :  
#### 배열 만들기 2

설명 :  
정수 l과 r이 주어졌을 때, l 이상 r이하의 정수 중에서 숫자 "0"과 "5"로만 이루어진 모든 정수를 오름차순으로 저장한 배열을 return 하는 solution 함수를 완성해 주세요.  
만약 그러한 정수가 없다면, -1이 담긴 배열을 return 합니다.

입출력 예  
| l | r | result |
| :-: | :-: | :-: |
| 5 | 555 | [5, 50, 55, 500, 505, 550, 555] |
| 10 | 20 | [-1] |

solution.js:
```javascript
function solution(l, r) {
    var answer = [];
    for(let i = l; i <= r; i++) {
        let str = String(i);
        let strArr = str.split("")
        let count = 0;
        for(let j = 0; j < strArr.length; j++) {
            if(String(strArr[j]).includes('5') || String(strArr[j]).includes('0')) count++;
        }
        if(strArr.length === count) answer.push(i);
    }
    if(answer.length === 0) answer.push(-1);
    return answer;
}
```

---

문제 :  
#### 코드 처리하기

설명 :  
문자열 code가 주어집니다.
code를 앞에서부터 읽으면서 만약 문자가 "1"이면 mode를 바꿉니다. mode에 따라 code를 읽어가면서 문자열 ret을 만들어냅니다.  
mode는 0과 1이 있으며, idx를 0 부터 code의 길이 - 1 까지 1씩 키워나가면서 code[idx]의 값에 따라 다음과 같이 행동합니다.  

- mode가 0일 때
- code[idx]가 "1"이 아니면 idx가 짝수일 때만 ret의 맨 뒤에 code[idx]를 추가합니다.
- code[idx]가 "1"이면 mode를 0에서 1로 바꿉니다.
- mode가 1일 때
- code[idx]가 "1"이 아니면 idx가 홀수일 때만 ret의 맨 뒤에 code[idx]를 추가합니다.
- code[idx]가 "1"이면 mode를 1에서 0으로 바꿉니다.

문자열 code를 통해 만들어진 문자열 ret를 return 하는 solution 함수를 완성해 주세요.  
단, 시작할 때 mode는 0이며, return 하려는 ret가 만약 빈 문자열이라면 대신 "EMPTY"를 return 합니다.

입출력 예  
| code | result |
| :-: | :-: | 
| "abc1abc1abc" | "acbac" |

solution.js:
```javascript
function solution(code) {
    var answer = '';
    let mode = 0;
    
    for(let i = 0; i < code.length; i++) {
        if(code[i] === '1'){
            mode === 1 ? mode = 0 : mode = 1;
        } else if(mode == 0 && i % 2 == 0) {
            answer += code[i];
        } else if(mode == 1 && i % 2 == 1) {
            answer += code[i];
        }
    }
    if(answer === "") answer = "EMPTY";
    return answer;
}
```

---

문제 :  
#### 문자열 출력하기

설명 :  
문자열 str이 주어질 때, str을 출력하는 코드를 작성해 보세요.

입출력 예  
| 입력 | 출력 |
| :-: | :-: |
| HelloWorld! | HelloWorld! |

solution.js:
```javascript
const readline = require('readline');
const rl = readline.createInterface({
    input: process.stdin,
    output: process.stdout
});

let input = [];

rl.on('line', function (line) {
    input = [line];
}).on('close',function(){
    str = input[0];
    console.log(str);
});
```

---

문제 :  
#### 외계어 사전

설명 :  
PROGRAMMERS-962 행성에 불시착한 우주비행사 머쓱이는 외계행성의 언어를 공부하려고 합니다. 알파벳이 담긴 배열 spell과 외계어 사전 dic이 매개변수로 주어집니다. spell에 담긴 알파벳을 한번씩만 모두 사용한 단어가 dic에 존재한다면 1, 존재하지 않는다면 2를 return하도록 solution 함수를 완성해주세요.

입출력 예  
| spell | dic | result |
| :-: | :-: | :-: |
| ["p", "o", "s"] | ["sod", "eocd", "qixm", "adio", "soo"] | 2 |
| ["z", "d", "x"] | ["def", "dww", "dzx", "loveaw"] | 1 |
| ["s", "o", "m", "d"] | ["moos", "dzx", "smm", "sunmmo", "som"] | 2 |

solution.js:
```javascript
function solution(spell, dic) {
    var answer = 0;
    let check = 0;
    
    for(let d of dic) {
        for(let s of spell) {
            if(d.includes(s)) check++;
        }
        if(check === spell.length) answer++;
        check = 0;
    }
    return answer === 0 ? 2 : 1;
}
```

---

문제 :  
#### 직사각형 넓이 구하기

설명 :  
2차원 좌표 평면에 변이 축과 평행한 직사각형이 있습니다. 직사각형 네 꼭짓점의 좌표 [[x1, y1], [x2, y2], [x3, y3], [x4, y4]]가 담겨있는 배열 dots가 매개변수로 주어질 때, 직사각형의 넓이를 return 하도록 solution 함수를 완성해보세요.

입출력 예  
| dots | result |
| :-: | :-: | 
| [[1, 1], [2, 1], [2, 2], [1, 2]] | 1 |
| [[-1, -1], [1, 1], [1, -1], [-1, 1]] | 4 |

solution.js:
```javascript
function solution(dots) {
    let x = [];
    let y = [];
    for(let d of dots) {
        x.push(d[0]);
        y.push(d[1]);       
    }
    x = (x.sort((a,b) => b - a))
    y = (y.sort((a,b) => b - a))
    return (x[0] - x.at(-1)) * (y[0] - y.at(-1));
}
```

---

문제 :  
#### 종이 자르기

설명 :  
머쓱이는 큰 종이를 1 x 1 크기로 자르려고 합니다. 예를 들어 2 x 2 크기의 종이를 1 x 1 크기로 자르려면 최소 가위질 세 번이 필요합니다.

입출력 예  
| M  | N | result |
| :-: | :-: | :-: |
| 2 | 2 | 3 |
| 2 | 5 | 9 |
| 1 | 1 | 0 |

solution.js:
```javascript
function solution(M, N) {
    return M * N - 1;
}
```
