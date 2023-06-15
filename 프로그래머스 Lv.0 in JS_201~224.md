### 201~224 of 224  

1.	[구슬을 나누는 경우의 수](#구슬을-나누는-경우의-수)
2.	[로그인 성공?](#로그인-성공)
3.	[치킨 쿠폰](#치킨-쿠폰)
4.	[등수 매기기](#등수-매기기)
5.	[유한소수 판별하기](#유한소수-판별하기)
6.	[저주의 숫자 3](#저주의-숫자-3)
7.	[특이한 정렬](#특이한-정렬)
8.	[문자열 밀기](#문자열-밀기)
9.	[최빈값 구하기](#최빈값-구하기)

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
#### 구슬을 나누는 경우의 수

설명 :  
머쓱이는 구슬을 친구들에게 나누어주려고 합니다. 구슬은 모두 다르게 생겼습니다. 머쓱이가 갖고 있는 구슬의 개수 balls와 친구들에게 나누어 줄 구슬 개수 share이 매개변수로 주어질 때, balls개의 구슬 중 share개의 구슬을 고르는 가능한 모든 경우의 수를 return 하는 solution 함수를 완성해주세요.

입출력 예  
| balls  | share | result |
| :-: | :-: | :-: |
| 3 | 2 | 3 |
| 5 | 3 | 10 |

solution.js:
```javascript
function fac(n) {
    let num = BigInt(1);
    for(let i = n; i > 1; i--) {
        num *= BigInt(i);
    }
    return num;
}

function solution(balls, share) {
    return fac(balls) / (fac(balls-share) * fac(share));
}
```

---

문제 :  
#### 로그인 성공?

설명 :  
머쓱이는 프로그래머스에 로그인하려고 합니다. 머쓱이가 입력한 아이디와 패스워드가 담긴 배열 id_pw와 회원들의 정보가 담긴 2차원 배열 db가 주어질 때, 다음과 같이 로그인 성공, 실패에 따른 메시지를 return하도록 solution 함수를 완성해주세요.
- 아이디와 비밀번호가 모두 일치하는 회원정보가 있으면 "login"을 return합니다.
- 로그인이 실패했을 때 아이디가 일치하는 회원이 없다면 “fail”를, 아이디는 일치하지만 비밀번호가 일치하는 회원이 없다면 “wrong pw”를 return 합니다.

입출력 예  
| id_pw | db | result |
| :-: | :-: | :-: |
| ["meosseugi", "1234"] | [["rardss", "123"], ["yyoom", "1234"], ["meosseugi", "1234"]] | "login" |
| ["programmer01", "15789"] | [["programmer02", "111111"], ["programmer00", "134"], ["programmer01", "1145"]] | "wrong pw" | 
| ["rabbit04", "98761"] | [["jaja11", "98761"], ["krong0313", "29440"], ["rabbit00", "111333"]] | "fail" |

solution.js:
```javascript
function solution(id_pw, db) {
    var answer = '';
    for(let d of db) {
        if(d[0] === id_pw[0]) {
            if(d[1] === id_pw[1]) {
                return "login"
            } else {
                return "wrong pw"
            }
        }
    }
    return "fail";
}
```

---

문제 :  
#### 치킨 쿠폰

설명 :  
프로그래머스 치킨은 치킨을 시켜먹으면 한 마리당 쿠폰을 한 장 발급합니다. 쿠폰을 열 장 모으면 치킨을 한 마리 서비스로 받을 수 있고, 서비스 치킨에도 쿠폰이 발급됩니다. 시켜먹은 치킨의 수 chicken이 매개변수로 주어질 때 받을 수 있는 최대 서비스 치킨의 수를 return하도록 solution 함수를 완성해주세요.

입출력 예  
| chicken | result | 
| :-: | :-: |
| 100 | 11 |
| 1,081 | 120 |

solution.js:
```javascript
function solution(chicken) {
    var answer = 0;
    let cou = 0;
    while(chicken > 9) {
        cou += chicken % 10
        chicken -= chicken % 10;
        answer += (chicken /= 10)
        chicken += cou;
        cou -= cou;
    }
    return answer;
}
```

---

문제 :  
#### 등수 매기기

설명 :  
영어 점수와 수학 점수의 평균 점수를 기준으로 학생들의 등수를 매기려고 합니다. 영어 점수와 수학 점수를 담은 2차원 정수 배열 score가 주어질 때, 영어 점수와 수학 점수의 평균을 기준으로 매긴 등수를 담은 배열을 return하도록 solution 함수를 완성해주세요.

입출력 예  
| score | result |
| :-: | :-: | 
| [[80, 70], [90, 50], [40, 70], [50, 80]] | [1, 2, 4, 3] |
| [[80, 70], [70, 80], [30, 50], [90, 100], [100, 90], [100, 100], [10, 30]] | [4, 4, 6, 2, 2, 1, 7] |

solution.js:
```javascript
function solution(score) {
    var answer = [];
    let rank = 1;
    let avg = score.map(n => (n[0] + n[1]) / 2);
    
    for(let a1 of avg) {
        for(let a2 of avg) {
            if(a1 < a2) rank++;
        }
        answer.push(rank);
        rank = 1;
    }
    
    return answer;
}
```

---

문제 :  
#### 유한소수 판별하기

설명 :  
소수점 아래 숫자가 계속되지 않고 유한개인 소수를 유한소수라고 합니다. 분수를 소수로 고칠 때 유한소수로 나타낼 수 있는 분수인지 판별하려고 합니다. 유한소수가 되기 위한 분수의 조건은 다음과 같습니다.
- 기약분수로 나타내었을 때, 분모의 소인수가 2와 5만 존재해야 합니다.
두 정수 a와 b가 매개변수로 주어질 때, a/b가 유한소수이면 1을, 무한소수라면 2를 return하도록 solution 함수를 완성해주세요.

입출력 예  
| a | b | result |
| :-: | :-: | :-: |
| 7 | 20 | 1 |
| 11 | 22 | 1 |
| 12 | 21 | 2 |

solution.js:
```javascript
function solution(a, b) {
    let gcd = (num1, num2) => (num2 > 0 ? gcd(num2, num1 % num2) : num1);
    b /= gcd(a,b);
    while(b % 2 === 0) {
        b /= 2;
    }
    while(b % 5 === 0) {
        b /= 5;
    }
    return b === 1 ? 1 : 2;
}
```

---

문제 :  
#### 저주의 숫자 3

설명 :  
3x 마을 사람들은 3을 저주의 숫자라고 생각하기 때문에 3의 배수와 숫자 3을 사용하지 않습니다. 3x 마을 사람들의 숫자는 다음과 같습니다.
| 10진법 | 3x 마을에서 쓰는 숫자 | 10진법 | 3x 마을에서 쓰는 숫자 |
| :-: | :-: | :-: | :-: |
| 1 | 1 | 6 | 8 |
| 2 | 2 | 7 | 10 |
| 3 | 4 | 8 | 11 |
| 4 | 5 | 9 | 14 |
| 5 | 7 | 10 |16 |

정수 n이 매개변수로 주어질 때, n을 3x 마을에서 사용하는 숫자로 바꿔 return하도록 solution 함수를 완성해주세요.

입출력 예  
| n | result |
| :-: | :-: |
| 15 | 25 |
| 40 | 76 |

solution.js:
```javascript
function solution(n) {
    var answer = 0;
    for(let i = 1; i <= n; i++) {
        answer++;
        while(answer % 3 === 0 || (String(answer).indexOf(3)) >= 0) {
            answer++;
        }
    }
    return answer;
}
```

---

문제 :  
#### 특이한 정렬

설명 :  
정수 n을 기준으로 n과 가까운 수부터 정렬하려고 합니다. 이때 n으로부터의 거리가 같다면 더 큰 수를 앞에 오도록 배치합니다. 정수가 담긴 배열 numlist와 정수 n이 주어질 때 numlist의 원소를 n으로부터 가까운 순서대로 정렬한 배열을 return하도록 solution 함수를 완성해주세요.

입출력 예  
| numlist | n | result |
| :-: | :-: | :-: |
| [1, 2, 3, 4, 5, 6] | 4 | [4, 5, 3, 6, 2, 1] |
| [10000,20,36,47,40,6,10,7000] | 30 | [36, 40, 20, 47, 10, 6, 7000, 10000] |

solution.js:
```javascript
function solution(numlist, n) {
    return numlist.sort((a,b) => Math.abs(n-b) - Math.abs(n-a) || a - b).reverse();
}
```

---

문제 :  
#### 문자열 밀기

설명 :  
문자열 "hello"에서 각 문자를 오른쪽으로 한 칸씩 밀고 마지막 문자는 맨 앞으로 이동시키면 "ohell"이 됩니다. 이것을 문자열을 민다고 정의한다면 문자열 A와 B가 매개변수로 주어질 때, A를 밀어서 B가 될 수 있다면 밀어야 하는 최소 횟수를 return하고 밀어서 B가 될 수 없으면 -1을 return 하도록 solution 함수를 완성해보세요.

입출력 예  
| A | B | result |
| :-: | :-: | :-: |
| "hello" | "ohell" | 1 |
| "apple" | "elppa" | -1 |
| "atat" | "tata" | 1 |
| "abc" | "abc" | 0 |

solution.js:
```javascript
function solution(A, B) {
    var answer = 0;
    A = A.split("")
    B = B.split("")
    for(let i = 0; i < B.length; i++) {
        if(String(A) === String(B)) return answer; 
        A.unshift(A.pop());
        answer++;
    }
    return -1;
}
```

---

문제 :  
#### 최빈값 구하기

설명 :  
최빈값은 주어진 값 중에서 가장 자주 나오는 값을 의미합니다. 정수 배열 array가 매개변수로 주어질 때, 최빈값을 return 하도록 solution 함수를 완성해보세요. 최빈값이 여러 개면 -1을 return 합니다.

입출력 예  
| array | result |
| :-: | :-: | 
| [1, 2, 3, 3, 3, 4] | 3 |
| [1, 1, 2, 2] | -1 |
| [1] | 1 |

solution.js:
```javascript
function solution(array) {
    let count = [];
    let arr = [];
    
    const result = array.reduce((accu, curr) => { 
        accu[curr] = (accu[curr] || 0) + 1; 
        return accu;
    }, {});
    
    for(let r in result) {
        count.push(result[r]);
        arr.push(Number(r));
    }
    
    let max = Math.max(...count);
    
    return count.indexOf(max) == count.lastIndexOf(max) ? 
        arr[count.indexOf(max)] : -1;
}
```

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
