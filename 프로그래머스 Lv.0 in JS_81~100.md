### 81~100 of 224  

1.	[홀짝에 따라 다른 값 반환하기](#홀짝에-따라-다른-값-반환하기)
2.	[n의 배수 고르기](#n의-배수-고르기)
3.	[직각삼각형 출력하기](#직각삼각형-출력하기)
4.	[배열의 길이에 따라 다른 연산하기](#배열의-길이에-따라-다른-연산하기)
5.	[최댓값 만들기 (2)](#최댓값-만들기-(2))
6.	[주사위의 개수](#주사위의-개수)
7.	[대문자와 소문자](#대문자와-소문자)
8.	[꼬리 문자열](#꼬리-문자열)
9.	[특정한 문자를 대문자로 바꾸기](#특정한-문자를-대문자로-바꾸기)
10.	[세균 증식](#세균-증식)
11.	[암호 해독](#암호-해독)
12.	[가위 바위 보](#가위-바위-보)
13.	[홀수 vs 짝수](#홀수-vs-짝수)
14.	[더 크게 합치기](#더-크게-합치기)
15.	[개미 군단](#개미-군단)
16.	[배열의 원소만큼 추가하기](#배열의-원소만큼-추가하기)
17.	[뒤에서 5등까지](#뒤에서-5등까지)
18.	[뒤에서 5등 위로](#뒤에서-5등-위로)
19.	[제곱수 판별하기](#제곱수-판별하기)
20.	[홀짝 구분하기](#홀짝-구분하기)

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
#### 홀짝에 따라 다른 값 반환하기 

설명 :  
양의 정수 n이 매개변수로 주어질 때, n이 홀수라면 n 이하의 홀수인 모든 양의 정수의 합을 return 하고 n이 짝수라면 n 이하의 짝수인 모든 양의 정수의 제곱의 합을 return 하는 solution 함수를 작성해 주세요.

입출력 예  
| n | result |
| :-: | :-: |
| 7 | 16 |
| 10 | 220 |

solution.js:
```javascript
function solution(n) {
    var answer = 0;
    
    for (let i = 0; i <= n; i++) {
        if(n % 2 === 1 && i % 2 === 1) answer += i;
        else if(n % 2 === 0 && i % 2 === 0) answer += (i*i);
    }
    return answer;
}
```

---

문제 :  
#### n의 배수 고르기

설명 :  
정수 n과 정수 배열 numlist가 매개변수로 주어질 때, numlist에서 n의 배수가 아닌 수들을 제거한 배열을 return하도록 solution 함수를 완성해주세요.

입출력 예  
| n | numlist | result |
| :-: | :-: | :-: |
| 3 | [4, 5, 6, 7, 8, 9, 10, 11, 12] | [6, 9, 12] |
| 5 | [1, 9, 3, 10, 13, 5] | [10, 5] |
| 12 | [2, 100, 120, 600, 12, 12] | [120, 600, 12, 12] |

solution.js:
```javascript
function solution(n, numlist) {
    return numlist.filter((num) => num % n === 0);
}
```

---

문제 :  
#### 직각삼각형 출력하기

설명 :  
"*"의 높이와 너비를 1이라고 했을 때, "*"을 이용해 직각 이등변 삼각형을 그리려고합니다. 정수 n 이 주어지면 높이와 너비가 n 인 직각 이등변 삼각형을 출력하도록 코드를 작성해보세요.

입출력 예  
| 입력 | 출력 | 
| :-: | :-: | 
| 3 | * |
| | ** |
| | *** |

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
    for(let i = 1; i <= Number(input[0]); i++){
        console.log('*'.repeat(i))            
    }
});
```

---

문제 :  
#### 배열의 길이에 따라 다른 연산하기 

설명 :  
정수 배열 arr과 정수 n이 매개변수로 주어집니다. arr의 길이가 홀수라면 arr의 모든 짝수 인덱스 위치에 n을 더한 배열을, arr의 길이가 짝수라면 arr의 모든 홀수 인덱스 위치에 n을 더한 배열을 return 하는 solution 함수를 작성해 주세요.

입출력 예  
| arr | n | result |
| :-: | :-: | :-: |
| [49, 12, 100, 276, 33] | 27 | [76, 12, 127, 276, 60] |
| [444, 555, 666, 777] | 100 | [444, 655, 666, 877] |

solution.js:
```javascript
function solution(arr, n) {
    let oddEven = (arr.length % 2 === 0) ? 1 : 0;
    for(let i = oddEven; i < arr.length; i = i + 2) {
        arr[i] += n;
    }
    return arr;
}
```

---

문제 :  
#### 최댓값 만들기 (2)

설명 :  
정수 배열 numbers가 매개변수로 주어집니다. numbers의 원소 중 두 개를 곱해 만들 수 있는 최댓값을 return하도록 solution 함수를 완성해주세요.

입출력 예  
| numbers | result |  
| :-: | :-: |
| [1, 2, -3, 4, -5] | 15 |
| [0, -31, 24, 10, 1, 9] | 240 |
| [10, 20, 30, 5, 5, 20, 5] | 600 |

solution.js:
```javascript
function solution(numbers) {
    numbers.sort((a,b) => b - a);
    return numbers.at(-1) * numbers.at(-2) > numbers[0] * numbers[1] ? 
        numbers.at(-1) * numbers.at(-2) : numbers[0] * numbers[1];
}
```

---

문제 :  
#### 주사위의 개수

설명 :  
머쓱이는 직육면체 모양의 상자를 하나 가지고 있는데 이 상자에 정육면체 모양의 주사위를 최대한 많이 채우고 싶습니다. 상자의 가로, 세로, 높이가 저장되어있는 배열 box와 주사위 모서리의 길이 정수 n이 매개변수로 주어졌을 때, 상자에 들어갈 수 있는 주사위의 최대 개수를 return 하도록 solution 함수를 완성해주세요.

입출력 예  
| box | n | result |
| :-: | :-: | :-: |
| [1, 1, 1] | 1 | 1 |
| [10, 8, 6] | 3 | 12 |

solution.js:
```javascript
function solution(box, n) {
    return Math.floor(box[0] / n) * Math.floor(box[1] / n) * Math.floor(box[2] /n);
}
```

---

문제 :  
#### 대문자와 소문자

설명 :  
문자열 my_string이 매개변수로 주어질 때, 대문자는 소문자로 소문자는 대문자로 변환한 문자열을 return하도록 solution 함수를 완성해주세요.

입출력 예  
| my_string | result |
| :-: | :-: | 
| "cccCCC" | "CCCccc" |
| "abCdEfghIJ" | "ABcDeFGHij" |

solution.js:
```javascript
function solution(my_string) {
    var answer = '';
    for(let str of my_string) {
        if(str === str.toUpperCase()) answer += str.toLowerCase();
        else answer += str.toUpperCase();
    }
    return answer;
}
```

---

문제 :  
#### 꼬리 문자열 

설명 :  
문자열들이 담긴 리스트가 주어졌을 때, 모든 문자열들을 순서대로 합친 문자열을 꼬리 문자열이라고 합니다. 꼬리 문자열을 만들 때 특정 문자열을 포함한 문자열은 제외시키려고 합니다. 예를 들어 문자열 리스트 ["abc", "def", "ghi"]가 있고 문자열 "ef"를 포함한 문자열은 제외하고 꼬리 문자열을 만들면 "abcghi"가 됩니다.  

문자열 리스트 str_list와 제외하려는 문자열 ex가 주어질 때, str_list에서 ex를 포함한 문자열을 제외하고 만든 꼬리 문자열을 return하도록 solution 함수를 완성해주세요.

입출력 예  
| str_list | ex | result |
| :-: | :-: | :-: |
| ["abc", "def", "ghi"] | "ef" | "abcghi" |
| ["abc", "bbc", "cbc"] | "c" | "" |

solution.js:
```javascript
function solution(str_list, ex) {
    var answer = '';
    for(let i in str_list) {
        str_list[i].includes(ex) ? '' : answer += str_list[i];
    }
    return answer;
}
```

---

문제 :  
#### 특정한 문자를 대문자로 바꾸기 

설명 :  
영소문자로 이루어진 문자열 my_string과 영소문자 1글자로 이루어진 문자열 alp가 매개변수로 주어질 때, my_string에서 alp에 해당하는 모든 글자를 대문자로 바꾼 문자열을 return 하는 solution 함수를 작성해 주세요.

입출력 예  
| my_string | alp | result |
| :-: | :-: | :-: |
| "programmers" | "p" | "Programmers" |
| "lowercase" | "x" |"lowercase" |

solution.js:
```javascript
function solution(my_string, alp) {
    var answer = '';
    my_string = my_string.split('');
    for(let i = 0; i < my_string.length; i++) {
        if(my_string[i] === alp) my_string[i] = my_string[i].toUpperCase();
    }
    return my_string.join('');
}
```

---

문제 :  
#### 세균 증식

설명 :  
어떤 세균은 1시간에 두배만큼 증식한다고 합니다. 처음 세균의 마리수 n과 경과한 시간 t가 매개변수로 주어질 때 t시간 후 세균의 수를 return하도록 solution 함수를 완성해주세요.

입출력 예  
| n | t | result |
| :-: | :-: | :-: |
| 2 | 10 | 2048 |
| 7 | 15 | 229,376 |

solution.js:
```javascript
function solution(n, t) {
    for(let i = 1; i <= t; i++) {
        n *= 2
    }
    return n;
}
```

---

문제 :  
#### 암호 해독

설명 :  
군 전략가 머쓱이는 전쟁 중 적군이 다음과 같은 암호 체계를 사용한다는 것을 알아냈습니다.  

- 암호화된 문자열 cipher를 주고받습니다.
- 그 문자열에서 code의 배수 번째 글자만 진짜 암호입니다.

문자열 cipher와 정수 code가 매개변수로 주어질 때 해독된 암호 문자열을 return하도록 solution 함수를 완성해주세요.

입출력 예  
| cipher | code | result |
| :-: | :-: | :-: |
| "dfjardstddetckdaccccdegk" | 4 | "attack" |
| "pfqallllabwaoclk" | 2 | "fallback" |

solution.js:
```javascript
function solution(cipher, code) {
    var answer = '';
    for(let i = code-1; i < cipher.length; i += (code)) {
        answer += cipher[i];  
    }
    return answer;
}
```

---

문제 :  
#### 가위 바위 보

설명 :  
가위는 2 바위는 0 보는 5로 표현합니다. 가위 바위 보를 내는 순서대로 나타낸 문자열 rsp가 매개변수로 주어질 때, rsp에 저장된 가위 바위 보를 모두 이기는 경우를 순서대로 나타낸 문자열을 return하도록 solution 함수를 완성해보세요.

입출력 예  
| rsp | result |
| :-: | :-: | 
| "2" | "0" |
| "205" | "052" |

solution.js:
```javascript
function solution(rsp) {
    var answer = '';
    for(let a of rsp) {
        if(a === '2') answer += 0;
        else if(a === '0') answer += 5;
        else if(a === '5') answer += 2;
    }
    return answer;
}
```

---

문제 :  
#### 홀수 vs 짝수 

설명 :  
정수 리스트 num_list가 주어집니다. 가장 첫 번째 원소를 1번 원소라고 할 때, 홀수 번째 원소들의 합과 짝수 번째 원소들의 합 중 큰 값을 return 하도록 solution 함수를 완성해주세요. 두 값이 같을 경우 그 값을 return합니다.

입출력 예  
| num_list | result |
| :-: | :-: |
| [4, 2, 6, 1, 7, 6] | 17 |
| [-1, 2, 5, 6, 3] | 8 |

solution.js:
```javascript
function solution(num_list) {
    let odd = 0;
    let even = 0;
    for(let i = 0; i < num_list.length; i++) {
        if(i % 2 === 0) even += num_list[i]
        else odd += num_list[i]
    }
    return even >= odd ? even : odd;
}
```

---

문제 :  
#### 더 크게 합치기 

설명 :  
연산 ⊕는 두 정수에 대한 연산으로 두 정수를 붙여서 쓴 값을 반환합니다. 예를 들면 다음과 같습니다.  

- 12 ⊕ 3 = 123
- 3 ⊕ 12 = 312

양의 정수 a와 b가 주어졌을 때, a ⊕ b와 b ⊕ a 중 더 큰 값을 return 하는 solution 함수를 완성해 주세요.  
단, a ⊕ b와 b ⊕ a가 같다면 a ⊕ b를 return 합니다.

입출력 예  
| a | b | result |
| :-: | :-: | :-: |
| 9 | 91 | 991 |
| 89 | 8 | 898 |

solution.js:
```javascript
function solution(a, b) {
    var answer = 0;
    let str1 = String(a) + String(b);
    let str2 = String(b) + String(a);
    str1 = parseInt(str1, 10)
    str2 = parseInt(str2, 10)
    answer = str1 >= str2 ? str1 : str2
    return answer;
}
```

---

문제 :  
#### 개미 군단

설명 :  
개미 군단이 사냥을 나가려고 합니다. 개미군단은 사냥감의 체력에 딱 맞는 병력을 데리고 나가려고 합니다. 장군개미는 5의 공격력을, 병정개미는 3의 공격력을 일개미는 1의 공격력을 가지고 있습니다. 예를 들어 체력 23의 여치를 사냥하려고 할 때, 일개미 23마리를 데리고 가도 되지만, 장군개미 네 마리와 병정개미 한 마리를 데리고 간다면 더 적은 병력으로 사냥할 수 있습니다. 사냥감의 체력 hp가 매개변수로 주어질 때, 사냥감의 체력에 딱 맞게 최소한의 병력을 구성하려면 몇 마리의 개미가 필요한지를 return하도록 solution 함수를 완성해주세요.

입출력 예  
| hp | result | 
| :-: | :-: | :-: |
| 23 | 5 |
| 24 | 6 |
| 999 | 201 |

solution.js:
```javascript
function solution(hp) {
    var answer = 0;
    let remainder = 0;
    
    answer += parseInt(hp / 5);
    remainder += parseInt(hp % 5);
    answer += parseInt(remainder / 3);
    remainder = parseInt(remainder % 3);
    
    return answer + remainder;
}
```

---

문제 :  
#### 배열의 원소만큼 추가하기 

설명 :  
아무 원소도 들어있지 않은 빈 배열 X가 있습니다. 양의 정수 배열 arr가 매개변수로 주어질 때, arr의 앞에서부터 차례대로 원소를 보면서 원소가 a라면 X의 맨 뒤에 a를 a번 추가하는 일을 반복한 뒤의 배열 X를 return 하는 solution 함수를 작성해 주세요.

입출력 예  
| ar | result |
| :-: | :-: | 
| [5, 1, 4] | [5, 5, 5, 5, 5, 1, 4, 4, 4, 4] |
| [6, 6] | [6, 6, 6, 6, 6, 6, 6, 6, 6, 6, 6, 6] |
| [1] | [1] |

solution.js:
```javascript
function solution(arr) {
    var answer = [];
    for(let n = 0; n < arr.length; n++) {
        answer = answer.concat(new Array(arr[n]).fill(arr[n]))
        console.log(new Array(arr[n]).fill(arr[n]))
    }
    return answer;
}
```

---

문제 :  
#### 뒤에서 5등까지 

설명 :  
정수로 이루어진 리스트 num_list가 주어집니다. num_list에서 가장 작은 5개의 수를 오름차순으로 담은 리스트를 return하도록 solution 함수를 완성해주세요.

입출력 예  
| num_list | result |
| :-: | :-: |
| [12, 4, 15, 46, 38, 1, 14] | [1, 4, 12, 14, 15] |

solution.js:
```javascript
function solution(num_list) {
    num_list.sort((a,b) => a-b)
    return num_list.slice(0,5);
}
```

---

문제 :  
#### 뒤에서 5등 위로 

설명 :  
정수로 이루어진 리스트 num_list가 주어집니다. num_list에서 가장 작은 5개의 수를 제외한 수들을 오름차순으로 담은 리스트를 return하도록 solution 함수를 완성해주세요.

입출력 예  
| num_list | result |
| :-: | :-: |
| [12, 4, 15, 46, 38, 1, 14, 56, 32, 10] | [15, 32, 38, 46, 56] |

solution.js:
```javascript
function solution(num_list) {
    num_list.sort((a,b) => a - b)
    return num_list.slice(5);
}
```

---

문제 :  
#### 제곱수 판별하기

설명 :  
어떤 자연수를 제곱했을 때 나오는 정수를 제곱수라고 합니다. 정수 n이 매개변수로 주어질 때, n이 제곱수라면 1을 아니라면 2를 return하도록 solution 함수를 완성해주세요.

입출력 예  
| n | result | 
| :-: | :-: |
| 144 |	1 |
| 976 | 2 |

solution.js:
```javascript
function solution(n) {
    var answer = 2;
    for(let i = 1; i < 1001; i++) {
        if(i ** 2 === n) {
            answer = 1;
            break;
        }; 
    }
    return answer;
}
```

---

문제 :  
#### 홀짝 구분하기 

설명 :  
자연수 n이 입력으로 주어졌을 때 만약 n이 짝수이면 "n is even"을, 홀수이면 "n is odd"를 출력하는 코드를 작성해 보세요.

입출력 예  
| 입력 | 출력 | 
| :-: | :-: |
| 100 | 100 is even | 
| 1 | 1 is odd |

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
    n = Number(input[0]);
    if(n % 2 === 0) console.log(`${n} is even`)
    else console.log(`${n} is odd`);
});
```
