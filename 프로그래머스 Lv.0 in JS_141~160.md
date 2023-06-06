### 141~160 of 224  

1.	[컨트롤 제트](#컨트롤-제트)
2.	[문자열 뒤집기](#문자열-뒤집기)
3.	[이진수 더하기](#이진수-더하기)
4.	[특정 문자열로 끝나는 가장 긴 부분 문자열 찾기](#특정-문자열로-끝나는-가장-긴-부분-문자열-찾기)
5.	[세로 읽기](#세로-읽기)
6.	[간단한 논리 연산](#간단한-논리-연산)
7.	[이차원 배열 대각선 순회하기](#이차원-배열-대각선-순회하기)
8.	[날짜 비교하기](#날짜-비교하기)
9.	[글자 지우기](#글자-지우기)
10.	[한 번만 등장한 문자](#한-번만-등장한-문자)
11.	[문자열 반복해서 출력하기](#문자열-반복해서-출력하기)
12.	[수열과 구간 쿼리 3](#수열과-구간-쿼리-3)
13.	[수열과 구간 쿼리 1](#수열과-구간-쿼리-1)
14.	[1로 만들기](#1로-만들기)
15.	[숨어있는 숫자의 덧셈 (2)](#숨어있는-숫자의-덧셈-2)
16.	[배열 만들기 5](#배열-만들기-5)
17.	[진료순서 정하기](#진료순서-정하기)
18.	[k의 개수](#k의-개수)
19.	[수 조작하기 2](#수-조작하기-2)
20.	[등차수열의 특정한 항만 더하기 ](#등차수열의-특정한-항만-더하기)

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
#### 컨트롤 제트

설명 :  
숫자와 "Z"가 공백으로 구분되어 담긴 문자열이 주어집니다. 문자열에 있는 숫자를 차례대로 더하려고 합니다. 이 때 "Z"가 나오면 바로 전에 더했던 숫자를 뺀다는 뜻입니다. 숫자와 "Z"로 이루어진 문자열 s가 주어질 때, 머쓱이가 구한 값을 return 하도록 solution 함수를 완성해보세요.

입출력 예  
| s | result |
| :-: | :-: |
| "1 2 Z 3" | 4 |
| "10 20 30 40" | 100 |
| "10 Z 20 Z 1" | 1 |
| "10 Z 20 Z" | 0 |
| "-1 -2 -3 Z" | -3 |

solution.js:
```javascript
function solution(s) {
    let answer = [];
    let arr = s.split(" ");
    for(let [i, a] of arr.entries()) {
        if(a === 'Z') {
            answer.pop();
            continue;
        } else {
            answer.push(Number(a));
        }
    }
    return answer.length === 0 ? 0 : answer.reduce((a,b) => (a+b));
}
```

---

문제 :  
#### 문자열 뒤집기

설명 :  
문자열 my_string과 정수 s, e가 매개변수로 주어질 때, my_string에서 인덱스 s부터 인덱스 e까지를 뒤집은 문자열을 return 하는 solution 함수를 작성해 주세요.

입출력 예  
| my_string | s | e | result |
| :-: | :-: | :-: | :-: |
| "Progra21Sremm3" | 6 | 12 | "ProgrammerS123" |
| "Stanley1yelnatS" | 4 | 10 | "Stanley1yelnatS" |

solution.js:
```javascript
function solution(my_string, s, e) {
    var answer = '';
    answer += my_string.slice(0, s);
    answer += my_string.slice(s, e + 1).split('').reverse().join('');
    answer += my_string.slice(e + 1);
    return answer;
}
```

---

문제 :  
#### 이진수 더하기

설명 :  
이진수를 의미하는 두 개의 문자열 bin1과 bin2가 매개변수로 주어질 때, 두 이진수의 합을 return하도록 solution 함수를 완성해주세요.

입출력 예  
| bin1 | bin2 | result |
| :-: | :-: | :-: |
| "10" | "11" | "101" |
| "1001" | "1111" | "11000" |

solution.js:
```javascript
function solution(bin1, bin2) {
    return ((parseInt(bin1, 2) + parseInt(bin2, 2)).toString(2));
}
```

---

문제 :  
#### 특정 문자열로 끝나는 가장 긴 부분 문자열 찾기

설명 :  
문자열 myString과 pat가 주어집니다. myString의 부분 문자열중 pat로 끝나는 가장 긴 부분 문자열을 찾아서 return 하는 solution 함수를 완성해 주세요.

입출력 예  
| myString | pat | result |
| :-: | :-: | :-: |
| "AbCdEFG" | "dE" | "AbCdE" |
| "AAAAaaaa" | "a" | "AAAAaaaa" |

solution.js:
```javascript
function solution(myString, pat) {
    return myString.slice(0, myString.lastIndexOf(pat)+pat.length);
}
```

---

문제 :  
#### 세로 읽기

설명 :  
문자열 my_string과 두 정수 m, c가 주어집니다. my_string을 한 줄에 m 글자씩 가로로 적었을 때 왼쪽부터 세로로 c번째 열에 적힌 글자들을 문자열로 return 하는 solution 함수를 작성해 주세요.

입출력 예  
| my_string | m | c | result |
| :-: | :-: | :-: | :-: |
| "ihrhbakrfpndopljhygc" | 4 | 2 | "happy" |
| "programmers" | 1 | 1 | "programmers" |

solution.js:
```javascript
function solution(my_string, m, c) {
    var answer = '';
    for(let i = c - 1; i < my_string.length; i += m) {
        if(m == 1) return my_string;
        answer += my_string[i];
    }
    return answer;
}
```

---

문제 :  
#### 간단한 논리 연산

설명 :  
boolean 변수 x1, x2, x3, x4가 매개변수로 주어질 때, 다음의 식의 true/false를 return 하는 solution 함수를 작성해 주세요.
- (x1 ∨ x2) ∧ (x3 ∨ x4)

입출력 예  
| x1 | x2 | x3 | x4 | result |
| :-: | :-: | :-: | :-: | :-: |
| false | true | true | true | true |
| true | false | false | false | false |

solution.js:
```javascript
function solution(x1, x2, x3, x4) {
    var answer = false;
    let a = false;
    let b = false;
    
    if(x1 && x2 && x3 && x4) return true;
    else if(!x1 && !x2 && !x3 && !x4) return false;
    
    if(x1 || x2) a = true;
    if(x3 || x4) b = true;
    a !== b ? answer = false : answer = true;
    return answer;
}
```

---

문제 :  
#### 이차원 배열 대각선 순회하기

설명 :  
2차원 정수 배열 board와 정수 k가 주어집니다.  
i + j <= k를 만족하는 모든 (i, j)에 대한 board[i][j]의 합을 return 하는 solution 함수를 완성해 주세요.

입출력 예  
| board | k | result |
| :-: | :-: | :-: |
| [[0, 1, 2],[1, 2, 3],[2, 3, 4],[3, 4, 5]] | 2 | 8 |

solution.js:
```javascript
function solution(board, k) {
    var answer = 0;
    for(let i in board) {
        for(let j in board[i]) {
            if(Number(i) + Number(j) <= k) answer += board[i][j];
        }
    }
    return answer;
}
```

---

문제 :  
#### 날짜 비교하기

설명 :  
정수 배열 date1과 date2가 주어집니다. 두 배열은 각각 날짜를 나타내며 [year, month, day] 꼴로 주어집니다. 각 배열에서 year는 연도를, month는 월을, day는 날짜를 나타냅니다.  
만약 date1이 date2보다 앞서는 날짜라면 1을, 아니면 0을 return 하는 solution 함수를 완성해 주세요.

입출력 예  
| date1 | date2 | result |
| :-: | :-: | :-: |
| [2021, 12, 28] | [2021, 12, 29] | 1 |
| [1024, 10, 24] | [1024, 10, 24] | 0 |

solution.js:
```javascript
function solution(date1, date2) {
    var answer = 0;
    
    if(date1[0] < date2[0]) {
        return answer = 1;
    } else if(date1[0] === date2[0]) {
        if(date1[1] < date2[1]) {
            return answer = 1;
        } else if(date1[1] === date2[1]) {
            if(date1[2] < date2[2]) {
                return answer = 1;
            }
        }
    }
    
    return answer;
}
```

---

문제 :  
#### 글자 지우기

설명 :  
문자열 my_string과 정수 배열 indices가 주어질 때, my_string에서 indices의 원소에 해당하는 인덱스의 글자를 지우고 이어 붙인 문자열을 return 하는 solution 함수를 작성해 주세요.

입출력 예  
| my_string | indices | result |
| :-: | :-: | :-: |
| apporoograpemmemprs" | [1, 16, 6, 15, 0, 10, 11, 3] | "programmers" |

solution.js:
```javascript
function solution(my_string, indices) {
    var answer = '';
    indices.sort((a,b) => a -b);
    for(let [i,element] of my_string.split("").entries()) {
        if(indices.includes(i)) continue;
        answer += element;
    }
    return answer;
}
```

---

문제 :  
#### 한 번만 등장한 문자

설명 :  
문자열 s가 매개변수로 주어집니다. s에서 한 번만 등장하는 문자를 사전 순으로 정렬한 문자열을 return 하도록 solution 함수를 완성해보세요. 한 번만 등장하는 문자가 없을 경우 빈 문자열을 return 합니다.

입출력 예  
| s | result |
| :-: | :-: | 
| "abcabcadc" | "d" |
| "abdc" | "abcd" |
| "hello" | "eho" |

solution.js:
```javascript
function solution(s) {
    let answer = "";
    let arr = s.split("").sort();
    const result = arr.reduce((accu, curr) => {
        accu[curr] = (accu[curr] || 0) + 1; 
        return accu;
    }, {});
    
    for(let r in result) {
        if(result[r] === 1) answer += r;
    }
    
    return answer;
}
```

---

문제 :  
#### 문자열 반복해서 출력하기

설명 :  
문자열 str과 정수 n이 주어집니다.  
str이 n번 반복된 문자열을 만들어 출력하는 코드를 작성해 보세요.

입출력 예  
| 입력 | 출력 |
| :-: | :-: |
| string 5 | stringstringstringstringstring |

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
    str = input[0];
    n = Number(input[1]);
    for(let i = 0; i < n; i++) {
        result = str.repeat(i + 1)
        if(i === n - 1) console.log(result)
    }
});
```

---

문제 :  
#### 수열과 구간 쿼리 3

설명 :  
정수 배열 arr와 2차원 정수 배열 queries이 주어집니다. queries의 원소는 각각 하나의 query를 나타내며, [i, j] 꼴입니다.  
각 query마다 순서대로 arr[i]의 값과 arr[j]의 값을 서로 바꿉니다.  
위 규칙에 따라 queries를 처리한 이후의 arr를 return 하는 solution 함수를 완성해 주세요.

입출력 예  
| arr | queries | result |
| :-: | :-: | :-: |
| [0, 1, 2, 3, 4] | [[0, 3],[1, 2],[1, 4]] | [3, 4, 1, 0, 2] |

solution.js:
```javascript
function solution(arr, queries) {
    var answer = [];
    let a;
    let b;
    for(let i in queries) {
        a = arr[queries[i][0]];
        b = arr[queries[i][1]];
        arr[queries[i][1]] = a;
        arr[queries[i][0]] = b;
    }
    return arr;
}
```

---

문제 :  
#### 수열과 구간 쿼리 1

설명 :  
정수 배열 arr와 2차원 정수 배열 queries이 주어집니다. queries의 원소는 각각 하나의 query를 나타내며, [s, e] 꼴입니다.  
각 query마다 순서대로 s ≤ i ≤ e인 모든 i에 대해 arr[i]에 1을 더합니다.  
위 규칙에 따라 queries를 처리한 이후의 arr를 return 하는 solution 함수를 완성해 주세요.

입출력 예  
| arr | queries | result |
| :-: | :-: | :-: |
| [0, 1, 2, 3, 4] | [[0, 1],[1, 2],[2, 3]] | [1, 3, 4, 4, 4] |

solution.js:
```javascript
function solution(arr, queries) {
    for(let i in queries) {
        for(let j = queries[i][0]; j <= queries[i][1]; j++) {
            arr[j] += 1;            
        }
    }
    return arr;
}
```

---

문제 :  
#### 1로 만들기

설명 :  
정수가 있을 때, 짝수라면 반으로 나누고, 홀수라면 1을 뺀 뒤 반으로 나누면, 마지막엔 1이 됩니다. 예를 들어 10이 있다면 다음과 같은 과정으로 1이 됩니다.

- 10 / 2 = 5
- (5 - 1) / 2 = 4
- 4 / 2 = 2
- 2 / 2 = 1

위와 같이 4번의 나누기 연산으로 1이 되었습니다.  
정수들이 담긴 리스트 num_list가 주어질 때, num_list의 모든 원소를 1로 만들기 위해서 필요한 나누기 연산의 횟수를 return하도록 solution 함수를 완성해주세요.

입출력 예  
| num_list | result |
| :-: | :-: |
| [12, 4, 15, 1, 14] | 11 |

solution.js:
```javascript
function solution(num_list) {
    var answer = 0;
    let bool = true;
    
    for(let i in num_list) {
        while(bool) {
            if(num_list[i] === 1) bool = false;
            else if(num_list[i] % 2 == 0) {
                num_list[i] /= 2;
                answer += 1;
            }
            else {
                num_list[i] = (num_list[i] - 1)/2;
                answer += 1;
            }
        }
        bool = true;
    }
    return answer;
}
```

---

문제 :  
#### 숨어있는 숫자의 덧셈 (2)

설명 :  
문자열 my_string이 매개변수로 주어집니다. my_string은 소문자, 대문자, 자연수로만 구성되어있습니다. my_string안의 자연수들의 합을 return하도록 solution 함수를 완성해주세요.

입출력 예  
| my_string | result |
| :-: | :-: | 
| "aAb1B2cC34oOp" | 37 |
| "1a2b3c4d123Z" | 133 |

solution.js:
```javascript
function solution(my_string) {
    var answer = 0;
    let arr = my_string.split(/[a-z, A-Z]/);
    for(let n of arr) {
        answer += Number(n)
    }
    return answer;
}
```

---

문제 :  
#### 배열 만들기 5

설명 :  
문자열 배열 intStrs와 정수 k, s, l가 주어집니다. intStrs의 원소는 숫자로 이루어져 있습니다.  
배열 intStrs의 각 원소마다 s번 인덱스에서 시작하는 길이 l짜리 부분 문자열을 잘라내 정수로 변환합니다. 이때 변환한 정수값이 k보다 큰 값들을 담은 배열을 return 하는 solution 함수를 완성해 주세요.

입출력 예  
| intStrs | k | s | l | result |
| :-: | :-: | :-: | :-: | :-: |
| ["0123456789","9876543210","9999999999999"] | 50000 | 5 | 5 | [56789, 99999] |

solution.js:
```javascript
function solution(intStrs, k, s, l) {
    var answer = [];
    for(let i of intStrs) {
        if(i.slice(s, s+l) > k) answer.push(Number(i.slice(s, s+l))); 
    }
    return answer;
}
```

---

문제 :  
#### 진료순서 정하기

설명 :  
외과의사 머쓱이는 응급실에 온 환자의 응급도를 기준으로 진료 순서를 정하려고 합니다. 정수 배열 emergency가 매개변수로 주어질 때 응급도가 높은 순서대로 진료 순서를 정한 배열을 return하도록 solution 함수를 완성해주세요.

입출력 예  
| emergency | result |  
| :-: | :-: |
| [3, 76, 24] | [3, 1, 2] |
| [1, 2, 3, 4, 5, 6, 7] | [7, 6, 5, 4, 3, 2, 1] | 
| [30, 10, 23, 6, 100] | [2, 4, 3, 5, 1] |

solution.js:
```javascript
function solution(emergency) {
    var answer = [];
    let arr = [...emergency];
    emergency.sort((a, b) => b - a);
    for(let a of arr) {
        for(let e of emergency) {
            if(a === e) {
                answer.push(emergency.indexOf(e) + 1);
                continue;
            }
        }
    }
    return answer;
}
```

---

문제 :  
#### k의 개수

설명 :  
1부터 13까지의 수에서, 1은 1, 10, 11, 12, 13 이렇게 총 6번 등장합니다. 정수 i, j, k가 매개변수로 주어질 때, i부터 j까지 k가 몇 번 등장하는지 return 하도록 solution 함수를 완성해주세요.

입출력 예  
| i | j | k | result |
| :-: | :-: | :-: | :-: |
| 1 | 13 | 1 | 6 |
| 10 | 50 | 5 | 5 |
| 3 | 10 | 2 | 0 |

solution.js:
```javascript
function solution(i, j, k) {
    var answer = 0;
    let arr = [];
    for(let num = i; num <= j; num++) {
        if(String(num).includes(k)) {
            arr = String(num).split("");
            for(let a of arr) {
                if(a === String(k)) {
                    answer++;
                }
            }
        }
    }
    return answer;
}
```

---

문제 :  
#### 수 조작하기 2

설명 :  
정수 배열 numLog가 주어집니다. 처음에 numLog[0]에서 부터 시작해 "w", "a", "s", "d"로 이루어진 문자열을 입력으로 받아 순서대로 다음과 같은 조작을 했다고 합시다.

- "w" : 수에 1을 더한다.
- "s" : 수에 1을 뺀다.
- "d" : 수에 10을 더한다.
- "a" : 수에 10을 뺀다.

그리고 매번 조작을 할 때마다 결괏값을 기록한 정수 배열이 numLog입니다. 즉, numLog[i]는 numLog[0]로부터 총 i번의 조작을 가한 결과가 저장되어 있습니다.  
주어진 정수 배열 numLog에 대해 조작을 위해 입력받은 문자열을 return 하는 solution 함수를 완성해 주세요.

입출력 예  
| log | result |
| :-: | :-: |
| [0, 1, 0, 10, 0, 1, 0, 10, 0, -1, -2, -1] | "wsdawsdassw" |

solution.js:
```javascript
function solution(numLog) {
    var answer = '';
    for(let i = 0; i < numLog.length-1; i++) {
        if(numLog[i] + 1 === numLog[i+1]) answer += 'w';
        else if(numLog[i] - 1 === numLog[i+1]) answer += 's';
        else if(numLog[i] + 10 === numLog[i+1]) answer += 'd';
        else answer += 'a';
    }
    return answer;
}
```

---

문제 :  
#### 등차수열의 특정한 항만 더하기 

설명 :  
두 정수 a, d와 길이가 n인 boolean 배열 included가 주어집니다. 첫째항이 a, 공차가 d인 등차수열에서 included[i]가 i + 1항을 의미할 때, 이 등차수열의 1항부터 n항까지 included가 true인 항들만 더한 값을 return 하는 solution 함수를 작성해 주세요.

입출력 예  
| a | d | included | result | 
| :-: | :-: | :-: | :-: |
| 3 | 4 | [true, false, false, true, true] | 37 |
| 7 | 1 | [false, false, false, true, false, false, false] | 10 |

solution.js:
```javascript
function solution(a, d, included) {
    var answer = 0;
    let number = a;
    for(let i = 0; i < included.length; i++) {
        answer = included[i] ? answer += number : answer += 0
        number += (d * 1);
    }
    return answer;
}
```
