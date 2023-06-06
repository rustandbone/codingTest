### 121~140 of 224  

1.	[팩토리얼](#팩토리얼)
2.	[A로 B 만들기](#A로-B-만들기)
3.	[2차원으로 만들기](#2차원으로-만들기)
4.	[특별한 이차원 배열 1](#특별한-이차원-배열-1)
5.	[문자열 잘라서 정렬하기](#문자열-잘라서-정렬하기)
6.	[콜라츠 수열 만들기](#콜라츠-수열-만들기)
7.	[모스부호 (1)](#모스부호-1)
8.	[중복된 문자 제거](#중복된-문자-제거)
9.	[두 수의 연산값 비교하기](#두-수의-연산값-비교하기)
10.	[배열 만들기 3](#배열-만들기-3)
11.	[9로 나눈 나머지](#9로-나눈-나머지)
12.	[특별한 이차원 배열 2](#특별한-이차원-배열-2)
13.	[문자열 정렬하기 (2)](#문자열-정렬하기-2)
14.	[간단한 식 계산하기](#간단한-식-계산하기)
15.	[x 사이의 개수](#x-사이의-개수)
16.	[가까운 1 찾기](#가까운-1-찾기)
17.	[문자열 돌리기](#문자열-돌리기)
18.	[문자열 섞기](#문자열-섞기)
19.	[숫자 찾기](#숫자-찾기)
20.	[주사위 게임 2](#주사위-게임-2)

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
#### 팩토리얼

설명 :  
i팩토리얼 (i!)은 1부터 i까지 정수의 곱을 의미합니다. 예를들어 5! = 5 * 4 * 3 * 2 * 1 = 120 입니다. 정수 n이 주어질 때 다음 조건을 만족하는 가장 큰 정수 i를 return 하도록 solution 함수를 완성해주세요.
- i! ≤ n

입출력 예  
| n | result |
| :-: | :-: | 
| 3628800 | 10 |
| 7 | 3 |

solution.js:
```javascript
function solution(n) {
    var answer = 0;
    let num = 1;
    for(let i = 1; i < 11; i++) {
        if(n >= num) num *= i;
        
        if(n === num) {
            answer = i;
            break;
        } else if (n < num) {
            answer = i - 1;
            break;
        }
    }
    return answer;
}
```

---

문제 :  
#### A로 B 만들기

설명 :  
문자열 before와 after가 매개변수로 주어질 때, before의 순서를 바꾸어 after를 만들 수 있으면 1을, 만들 수 없으면 0을 return 하도록 solution 함수를 완성해보세요.

입출력 예  
| before | after | result |
| :-: | :-: | :-: |
| "olleh" | "hello" | 1 |
| "allpe" | "apple" | 0 |

solution.js:
```javascript
function solution(before, after) {
    return before.split("").sort().join('') == after.split("").sort().join('') ? 1 : 0;
}
```

---

문제 :  
#### 2차원으로 만들기

설명 :  
정수 배열 num_list와 정수 n이 매개변수로 주어집니다. num_list를 다음 설명과 같이 2차원 배열로 바꿔 return하도록 solution 함수를 완성해주세요.  
num_list가 [1, 2, 3, 4, 5, 6, 7, 8] 로 길이가 8이고 n이 2이므로 num_list를 2 * 4 배열로 다음과 같이 변경합니다. 2차원으로 바꿀 때에는 num_list의 원소들을 앞에서부터 n개씩 나눠 2차원 배열로 변경합니다.

입출력 예  
| num_list | n | result |
| :-: | :-: | :-: |
| [1, 2, 3, 4, 5, 6, 7, 8] | 2 | [[1, 2], [3, 4], [5, 6], [7, 8]] |
| [100, 95, 2, 4, 5, 6, 18, 33, 948] | 3 | [[100, 95, 2], [4, 5, 6], [18, 33, 948]] |

solution.js:
```javascript
function solution(num_list, n) {
    var answer = [];
    let arr = [...num_list];
    
    for(let i = 0; i < num_list.length; i += n) {
        answer.push(num_list.splice(i, n));
        num_list = [...arr];
    }
    
    return answer;
}
```

---

문제 :  
#### 특별한 이차원 배열 1

설명 :  
정수 n이 매개변수로 주어질 때, 다음과 같은 n × n 크기의 이차원 배열 arr를 return 하는 solution 함수를 작성해 주세요.
- arr[i][j] (0 ≤ i, j < n)의 값은 i = j라면 1, 아니라면 0입니다.

입출력 예   
| n | result |
| :-: | :-: | 
| 3 | [[1, 0, 0], [0, 1, 0], [0, 0, 1]] |
| 6 | [[1, 0, 0, 0, 0, 0], [0, 1, 0, 0, 0, 0], [0, 0, 1, 0, 0, 0], [0, 0, 0, 1, 0, 0], [0, 0, 0, 0, 1, 0], [0, 0, 0, 0, 0, 1]] |
| 1 | [[1]] |

solution.js:
```javascript
function solution(n) {
    const answer = Array.from(Array(n), () => new Array(n).fill(0));
    for(let i = 0; i < n; i++){
        if(i === i) answer[i][i] = 1;
    }
    return answer;
}
```

---

문제 :  
#### 문자열 잘라서 정렬하기

설명 :  
문자열 myString이 주어집니다. "x"를 기준으로 해당 문자열을 잘라내 배열을 만든 후 사전순으로 정렬한 배열을 return 하는 solution 함수를 완성해 주세요.  
단, 빈 문자열은 반환할 배열에 넣지 않습니다.

입출력 예  
| myString | result |
| :-: | :-: |
| "axbxcxdx" | ["a","b","c","d"] |
| "dxccxbbbxaaaa" | ["aaaa","bbb","cc","d"] |

solution.js:
```javascript
function solution(myString) {
    myString = myString.split("x").sort();
    
    for(let i in myString) {
       if(myString.includes("")) myString = myString.slice(1);
       else break;
    }
    
    return myString;
}
```

---

문제 :  
#### 콜라츠 수열 만들기

설명 :  
모든 자연수 x에 대해서 현재 값이 x이면 x가 짝수일 때는 2로 나누고, x가 홀수일 때는 3 * x + 1로 바꾸는 계산을 계속해서 반복하면 언젠가는 반드시 x가 1이 되는지 묻는 문제를 콜라츠 문제라고 부릅니다.  
그리고 위 과정에서 거쳐간 모든 수를 기록한 수열을 콜라츠 수열이라고 부릅니다.  
계산 결과 1,000 보다 작거나 같은 수에 대해서는 전부 언젠가 1에 도달한다는 것이 알려져 있습니다.  
임의의 1,000 보다 작거나 같은 양의 정수 n이 주어질 때 초기값이 n인 콜라츠 수열을 return 하는 solution 함수를 완성해 주세요.

입출력 예  
| n | result | 
| :-: | :-: |
| 10 | [10, 5, 16, 8, 4, 2, 1] |

solution.js:
```javascript
function solution(n) {
    var answer = [];
    let bool = true;
    answer.push(n);
    while(bool) {
        if(n === 1) bool = false;
        else if(n % 2 === 0) {
            n /= 2;
            answer.push(n);
        }
        else {
            n = 3 * n + 1;
            answer.push(n);
        }
    }
    return answer;
}
```

---

문제 :  
#### 모스부호 (1)

설명 :  
머쓱이는 친구에게 모스부호를 이용한 편지를 받았습니다. 그냥은 읽을 수 없어 이를 해독하는 프로그램을 만들려고 합니다. 문자열 letter가 매개변수로 주어질 때, letter를 영어 소문자로 바꾼 문자열을 return 하도록 solution 함수를 완성해보세요.
모스부호는 다음과 같습니다.
```javascript
morse = { 
    '.-':'a','-...':'b','-.-.':'c','-..':'d','.':'e','..-.':'f',
    '--.':'g','....':'h','..':'i','.---':'j','-.-':'k','.-..':'l',
    '--':'m','-.':'n','---':'o','.--.':'p','--.-':'q','.-.':'r',
    '...':'s','-':'t','..-':'u','...-':'v','.--':'w','-..-':'x',
    '-.--':'y','--..':'z'
}
```

입출력 예  
| letter | result | 
| :-: | :-: |
| ".... . .-.. .-.. ---" | "hello" | 
| ".--. -.-- - .... --- -." | "python" |

solution.js:
```javascript
function solution(letter) {
    var answer = '';
    let morse = { 
    '.-':'a','-...':'b','-.-.':'c','-..':'d','.':'e','..-.':'f',
    '--.':'g','....':'h','..':'i','.---':'j','-.-':'k','.-..':'l',
    '--':'m','-.':'n','---':'o','.--.':'p','--.-':'q','.-.':'r',
    '...':'s','-':'t','..-':'u','...-':'v','.--':'w','-..-':'x',
    '-.--':'y','--..':'z'
    } 
    let arr = letter.split(" ")
    for(let a of arr) {
        answer += morse[a];
    }
    return answer;
}
```

---

문제 :  
#### 중복된 문자 제거

설명 :  
문자열 my_string이 매개변수로 주어집니다. my_string에서 중복된 문자를 제거하고 하나의 문자만 남긴 문자열을 return하도록 solution 함수를 완성해주세요.

입출력 예  
| my_string | result | 
| :-: | :-: |
| "people" | "peol" |
| "We are the world" | "We arthwold" |

solution.js:
```javascript
function solution(my_string) {
    const arr = array => [...new Set(array)];
    return arr(my_string).join('');
}
```

---

문제 :  
#### 두 수의 연산값 비교하기

설명 :  
연산 ⊕는 두 정수에 대한 연산으로 두 정수를 붙여서 쓴 값을 반환합니다. 예를 들면 다음과 같습니다.  

- 12 ⊕ 3 = 123
- 3 ⊕ 12 = 312

양의 정수 a와 b가 주어졌을 때, a ⊕ b와 2 * a * b 중 더 큰 값을 return하는 solution 함수를 완성해 주세요.  
단, a ⊕ b와 2 * a * b가 같으면 a ⊕ b를 return 합니다.

입출력 예  
| a | b | result |
| :-: | :-: | :-: |
| 2 | 91 | 364 |
| 91 | 2 | 912 |

solution.js:
```javascript
function solution(a, b) {
    var answer = 0;
    answer = Math.max(`${a}${b}`, `${2*a*b}`)
    return answer;
}
```

---

문제 :  
#### 배열 만들기 3

설명 :  
정수 배열 arr와 2개의 구간이 담긴 배열 intervals가 주어집니다.  
intervals는 항상 [[a1, b1], [a2, b2]]의 꼴로 주어지며 각 구간은 닫힌 구간입니다. 닫힌 구간은 양 끝값과 그 사이의 값을 모두 포함하는 구간을 의미합니다.  
이때 배열 arr의 첫 번째 구간에 해당하는 배열과 두 번째 구간에 해당하는 배열을 앞뒤로 붙여 새로운 배열을 만들어 return 하는 solution 함수를 완성해 주세요.

입출력 예  
| arr | intervals | result |
| :-: | :-: | :-: |
| [1, 2, 3, 4, 5] | [[1, 3], [0, 4]] | [2, 3, 4, 1, 2, 3, 4, 5] |

solution.js:
```javascript
function solution(arr, intervals) {
    var answer = [];
    answer = arr.slice(intervals[0][0], intervals[0][1] + 1)
    answer.push(arr.slice(intervals[1][0], intervals[1][1] + 1))
    return answer.flat(1);
}
```

---

문제 :  
#### 9로 나눈 나머지

설명 :  
음이 아닌 정수를 9로 나눈 나머지는 그 정수의 각 자리 숫자의 합을 9로 나눈 나머지와 같은 것이 알려져 있습니다.
이 사실을 이용하여 음이 아닌 정수가 문자열 number로 주어질 때, 이 정수를 9로 나눈 나머지를 return 하는 solution 함수를 작성해주세요.

입출력 예  
| number | result |
| :-: | :-: |
| "123" | 6 |
| "78720646226947352489" | 2 |

solution.js:
```javascript
function solution(number) {
    var answer = 0;
    for(let i of number) {
        answer += Number(number[i]);
    }
    return answer % 9;
}
```

---

문제 :  
#### 특별한 이차원 배열 2

설명 :  
n × n 크기의 이차원 배열 arr이 매개변수로 주어질 때, arr이 다음을 만족하면 1을 아니라면 0을 return 하는 solution 함수를 작성해 주세요.
- 0 ≤ i, j < n인 정수 i, j에 대하여 arr[i][j] = arr[j][i]

입출력 예  
| arr | result |
| :-: | :-: |
| [[5, 192, 33], [192, 72, 95], [33, 95, 999]] | 1 |
| [[19, 498, 258, 587], [63, 93, 7, 754], [258, 7, 1000, 723], [587, 754, 723, 81]] | 0 |

solution.js:
```javascript
function solution(arr) {
    var answer = 0;
    let count = 0;
    for(let i in arr) {
        for(let j in arr) {
            if(arr[i][j] === arr[j][i]) answer = 1;
            else count++;
        }
    }
    if(count > 0) answer = 0;
    return answer;
}
```

---

문제 :  
#### 문자열 정렬하기 (2)

설명 :  
영어 대소문자로 이루어진 문자열 my_string이 매개변수로 주어질 때, my_string을 모두 소문자로 바꾸고 알파벳 순서대로 정렬한 문자열을 return 하도록 solution 함수를 완성해보세요.

입출력 예  
| my_string | result | 
| :-: | :-: |
| "Bcad" | "abcd" | 
| "heLLo" | "ehllo" |
| "Python" | "hnopty" |

solution.js:
```javascript
function solution(my_string) {
    return my_string.toLowerCase().split('').sort().join('');
}
```

---

문제 :  
#### 간단한 식 계산하기

설명 :  
문자열 binomial이 매개변수로 주어집니다. binomial은 "a op b" 형태의 이항식이고 a와 b는 음이 아닌 정수, op는 '+', '-', '*' 중 하나입니다. 주어진 식을 계산한 정수를 return 하는 solution 함수를 작성해 주세요.

입출력 예  
| binomial | result | 
| :-: | :-: |
| "43 + 12" | 55 |
| "0 - 7777" | -7777 |
| "40000 * 40000" | 1600000000 |

solution.js:
```javascript
function solution(binomial) {
    var answer = 0;
    let arr = binomial.split(" ");
    if(arr[1] === "*") answer = arr[0] * arr[2];
    else if(arr[1] === "+") answer = Number(arr[0]) + Number(arr[2]);
    else answer = arr[0] - arr[2];
    return answer;
}
```

---

문제 :  
#### x 사이의 개수

설명 :  
문자열 myString이 주어집니다. myString을 문자 "x"를 기준으로 나눴을 때 나눠진 문자열 각각의 길이를 순서대로 저장한 배열을 return 하는 solution 함수를 완성해 주세요.

입출력 예  
| myString | result |
| :-: | :-: |
| "oxooxoxxox" | [1, 2, 1, 0, 1, 0] |
| "xabcxdefxghi" | [0, 3, 3, 3]  |

solution.js:
```javascript
function solution(myString) {
    var answer = [];
    myString = myString.split("x");
    for(let i in myString) {
        answer.push(myString[i].length);
    }
    return answer;
}
```

---

문제 :  
#### 가까운 1 찾기

설명 :  
정수 배열 arr가 주어집니다. 이때 arr의 원소는 1 또는 0입니다. 정수 idx가 주어졌을 때, idx보다 크면서 배열의 값이 1인 가장 작은 인덱스를 찾아서 반환하는 solution 함수를 완성해 주세요.  
단, 만약 그러한 인덱스가 없다면 -1을 반환합니다.

입출력 예  
| arr | idx | result |
| :-: | :-: | :-: |
| [0, 0, 0, 1] | 1 | 3 |
| [1, 0, 0, 1, 0, 0] | 4 | -1 |
| [1, 1, 1, 1, 0] | 3 | 3 |

solution.js:
```javascript
function solution(arr, idx) {
    var answer = 0;
    let realArr = arr.slice(idx)
    for(let i = 0; i < realArr.length; i++) {
        answer = realArr.indexOf(1) + idx;
        realArr.includes(1) ? answer : answer = -1;
    }
    return answer;
}
```

---

문제 :  
#### 문자열 돌리기

설명 :  
문자열 str이 주어집니다.  
문자열을 시계방향으로 90도 돌려서 아래 입출력 예와 같이 출력하는 코드를 작성해 보세요.

입출력 예  
| 입력 | 출력 |
| :-: | :-: |
| abcde | a |
|| b |
|| c |
|| d |
|| e |

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
    for(let i = 0; i < str.length; i++) {
        console.log(str[i]);        
    }

});
```

---

문제 :  
#### 문자열 섞기

설명 :  
길이가 같은 두 문자열 str1과 str2가 주어집니다.
  
두 문자열의 각 문자가 앞에서부터 서로 번갈아가면서 한 번씩 등장하는 문자열을 만들어 return 하는 solution 함수를 완성해 주세요.

입출력 예  
| str1 | str2 | result |
| :-: | :-: | :-: |
| "aaaaa" | "bbbbb" | "ababababab" |

solution.js:
```javascript
function solution(str1, str2) {
    var answer = '';
    for(i = 0; i < str1.length; i++) {
        answer += str1[i] + str2[i];
    }
    return answer;
}
```

---

문제 :  
#### 숫자 찾기

설명 :  
정수 num과 k가 매개변수로 주어질 때, num을 이루는 숫자 중에 k가 있으면 num의 그 숫자가 있는 자리 수를 return하고 없으면 -1을 return 하도록 solution 함수를 완성해보세요.

입출력 예  
| num | k | result |
| :-: | :-: | :-: |
| 29183 | 1 | 3 |
| 232443 | 4 | 4 |
| 123456 | 7 | -1 |

solution.js:
```javascript
function solution(num, k) {
    return String(num).split("").indexOf(String(k)) === -1 ? 
        -1 : String(num).split("").indexOf(String(k)) + 1;
}
```

---

문제 :  
#### 주사위 게임 2

설명 :  
1부터 6까지 숫자가 적힌 주사위가 세 개 있습니다. 세 주사위를 굴렸을 때 나온 숫자를 각각 a, b, c라고 했을 때 얻는 점수는 다음과 같습니다.

- 세 숫자가 모두 다르다면 a + b + c 점을 얻습니다.
- 세 숫자 중 어느 두 숫자는 같고 나머지 다른 숫자는 다르다면 (a + b + c) × (a2 + b2 + c2 )점을 얻습니다.
- 세 숫자가 모두 같다면 (a + b + c) × (a2 + b2 + c2 ) × (a3 + b3 + c3 )점을 얻습니다.

세 정수 a, b, c가 매개변수로 주어질 때, 얻는 점수를 return 하는 solution 함수를 작성해 주세요.

입출력 예  
| a | b | c | result |
| :-: | :-: | :-: | :-: |
| 2 |	6 | 1 | 9 |
| 5 | 3 | 3 | 473 |
| 4 | 4 | 4 | 110592 |

solution.js:
```javascript
function solution(a, b, c) {
    var answer = 0;
    if(a == b && b == c) {
        return answer = (a + b + c) * (a**2 + b**2 + c**2) * (a**3 + b**3 + c**3)
    } else if(a == b || a == c || b == c) {
        return answer = (a + b + c) * (a**2 + b**2 + c**2)
    } else {
        return answer = a + b + c;
    }
}
```
