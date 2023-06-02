### 61~80 of 224  

1.	[A 강조하기](#A-강조하기)
2.	[문자열 안에 문자열](#문자열-안에-문자열)
3.	[글자 이어 붙여 문자열 만들기](#글자-이어-붙여-문자열-만들기)
4.	[주사위 게임 1](#주사위-게임-1)
5.	[이어 붙인 수](#이어-붙인-수)
6.	[첫 번째로 나오는 음수](#첫-번째로-나오는-음수)
7.	[문자열 곱하기](#문자열-곱하기)
8.	[접미사인지 확인하기](#접미사인지-확인하기)
9.	[n개 간격의 원소들](#n개-간격의-원소들)
10.	[접두사인지 확인하기](#접두사인지-확인하기)
11.	[문자열 바꿔서 찾기](#문자열-바꿔서-찾기)
12.	[문자 리스트를 문자열로 변환하기](#문자-리스트를-문자열로-변환하기)
13.	[rny_string](#rny_string)
14.	[마지막 두 원소](#마지막-두원소)
15.	[배열 만들기 1](#배열-만들기-1)
16.	[원하는 문자열 찾기](#원하는-문자열-찾기)
17.	[n 번째 원소까지](#n-번째-원소까지)
18.	[n 번째 원소부터](#n-번째-원소부터)
19.	[문자열 붙여서 출력하기](#문자열-붙여서-출력하기)
20.	[조건에 맞게 수열 변환하기 1](#조건에-맞게-수열-변환하기-1)

---

문제 :  


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
#### A 강조하기 

설명 :  
문자열 myString이 주어집니다. myString에서 알파벳 "a"가 등장하면 전부 "A"로 변환하고, "A"가 아닌 모든 대문자 알파벳은 소문자 알파벳으로 변환하여 return 하는 solution 함수를 완성하세요.

입출력 예  
| myString | result |
| :-: | :-: |
| "abstract algebra" | "AbstrAct AlgebrA" | 
| "PrOgRaMmErS" | "progrAmmers" |

solution.js:
```javascript
function solution(myString) {
    myString = myString.split('');
    for (let i in myString) {
        if(myString[i] === 'A' || myString[i] === 'a') myString[i] = myString[i].toUpperCase();
        else myString[i] = myString[i].toLowerCase();
    }
    return myString.join('');
}
```

---

문제 :  
#### 문자열 안에 문자열

설명 :  
문자열 str1, str2가 매개변수로 주어집니다. str1 안에 str2가 있다면 1을 없다면 2를 return하도록 solution 함수를 완성해주세요.

입출력 예  
| str1 | str2 | result |
| :-: | :-: | :-: |
| "ab6CDE443fgh22iJKlmn1o" | "6CD" | 1 |
| "ppprrrogrammers" | "pppp" | 2 |
| "AbcAbcA" | "AAA" | 2 |

solution.js:
```javascript
function solution(str1, str2) {
    return str1.includes(str2) ? 1 : 2;
}
```

---

문제 :  
#### 글자 이어 붙여 문자열 만들기 

설명 :  
문자열 my_string과 정수 배열 index_list가 매개변수로 주어집니다. my_string의 index_list의 원소들에 해당하는 인덱스의 글자들을 순서대로 이어 붙인 문자열을 return 하는 solution 함수를 작성해 주세요.

입출력 예  
| my_string | index_list | result |
| :-: | :-: | :-: |
| "cvsgiorszzzmrpaqpe" | [16, 6, 5, 3, 12, 14, 11, 11, 17, 12, 7] | "programmers" |
| "zpiaz" | [1, 2, 0, 0, 3] | "pizza" |

solution.js:
```javascript
function solution(my_string, index_list) {
    var answer = [];
    for(let i = 0; i < index_list.length; i++) {
        answer.push(my_string[index_list[i]]);
    }
    return answer.join('');
}
```

---

문제 :  
#### 주사위 게임 1 

설명 :  
1부터 6까지 숫자가 적힌 주사위가 두 개 있습니다. 두 주사위를 굴렸을 때 나온 숫자를 각각 a, b라고 했을 때 얻는 점수는 다음과 같습니다.  
- a와 b가 모두 홀수라면 a2 + b2 점을 얻습니다.
- a와 b 중 하나만 홀수라면 2 × (a + b) 점을 얻습니다.
- a와 b 모두 홀수가 아니라면 |a - b| 점을 얻습니다.

두 정수 a와 b가 매개변수로 주어질 때, 얻는 점수를 return 하는 solution 함수를 작성해 주세요.

입출력 예  
| a | b | result |
| :-: | :-: | :-: |
| 3 |	5 |	34 |
| 6 | 1 | 14 |
| 2 | 4 | 2 |

solution.js:
```javascript
function solution(a, b) {
    var answer = 0;
    if(a % 2 === 1 && b % 2 === 1) answer = a**2 + b**2
    else if(a % 2 === 1 || b % 2 === 1) answer = 2 * (a + b)
    else answer = Math.abs(a - b);
    return answer;
}
```

---

문제 :  
#### 이어 붙인 수 

설명 :  
정수가 담긴 리스트 num_list가 주어집니다. num_list의 홀수만 순서대로 이어 붙인 수와 짝수만 순서대로 이어 붙인 수의 합을 return하도록 solution 함수를 완성해주세요.

입출력 예  
| num_list | result | 
| :-: | :-: | 
| [3, 4, 5, 2, 1] |	393 |
| [5, 7, 8, 3] | 581 |

solution.js:
```javascript
function solution(num_list) {
    var answer = 0;
    let odd = new String();
    let even = new String();
    for(let i = 0; i < num_list.length; i++) {
        if(num_list[i] % 2 === 0) even += String(num_list[i])
        else odd += String(num_list[i])
    }
    answer = parseInt(even) + parseInt(odd)
    return answer;
}
```

---

문제 :  
#### 첫 번째로 나오는 음수 

설명 :  
정수 리스트 num_list가 주어질 때, 첫 번째로 나오는 음수의 인덱스를 return하도록 solution 함수를 완성해주세요. 음수가 없다면 -1을 return합니다.

입출력 예  
| num_list | result | 
| :-: | :-: |
| [12, 4, 15, 46, 38, -2, 15] | 5 |
| [13, 22, 53, 24, 15, 6] | -1 |

solution.js:
```javascript
function solution(num_list) {
    var answer = -1;
    for(let i = 0; i < num_list.length; i++) {
        console.log(num_list[i])
        if(num_list[i] < 0) {
            answer = i;
        }
    }
    return answer;
}
```

---

문제 :  
#### 문자열 곱하기 

설명 :  
문자열 my_string과 정수 k가 주어질 때, my_string을 k번 반복한 문자열을 return 하는 solution 함수를 작성해 주세요.

입출력 예  
| my_string | k | result |
| :-: | :-: | :-: |
| "string" | 3 | "stringstringstring" |
| "love" | 10 | "lovelovelovelovelovelovelovelovelovelove" |

solution.js:
```javascript
function solution(my_string, k) {
    var answer = '';
    answer = my_string.repeat(k);
    return answer;
}
```

---

문제 :  
#### 접미사인지 확인하기 

설명 :  
어떤 문자열에 대해서 접미사는 특정 인덱스부터 시작하는 문자열을 의미합니다. 예를 들어, "banana"의 모든 접미사는 "banana", "anana", "nana", "ana", "na", "a"입니다.  
문자열 my_string과 is_suffix가 주어질 때, is_suffix가 my_string의 접미사라면 1을, 아니면 0을 return 하는 solution 함수를 작성해 주세요.

입출력 예  
| my_string | is_suffix | result |
| :-: | :-: | :-: |
| "banana" | "ana" | 1 |
| "banana" | "nan" | 0 |
| "banana" | "wxyz" | 0 |
| "banana" | "abanana" | 0 |

solution.js:
```javascript
function solution(my_string, is_suffix) {
    return my_string.endsWith(is_suffix) ? 1 : 0;
}
```

---

문제 :  
#### n개 간격의 원소들 

설명 :  
정수 리스트 num_list와 정수 n이 주어질 때, num_list의 첫 번째 원소부터 마지막 원소까지 n개 간격으로 저장되어있는 원소들을 차례로 담은 리스트를 return하도록 solution 함수를 완성해주세요.

입출력 예  
| num_list | n | result |
| :-: | :-: | :-: |
| [4, 2, 6, 1, 7, 6] | 2 | [4, 6, 7] |
| [4, 2, 6, 1, 7, 6] | 4 | [4, 7] |

solution.js:
```javascript
function solution(num_list, n) {
    var answer = [];
    for(let i = 0; i < num_list.length; i = i + n) {
        answer.push(num_list[i])
    }
    return answer;
}
```

---

문제 :  
#### 접두사인지 확인하기 

설명 :  
어떤 문자열에 대해서 접두사는 특정 인덱스까지의 문자열을 의미합니다. 예를 들어, "banana"의 모든 접두사는 "b", "ba", "ban", "bana", "banan", "banana"입니다.  
문자열 my_string과 is_prefix가 주어질 때, is_prefix가 my_string의 접두사라면 1을, 아니면 0을 return 하는 solution 함수를 작성해 주세요.

입출력 예  
| my_string | is_prefix | result |
| :-: | :-: | :-: |
| "banana" | "ban" | 1 |
| "banana" | "nan" | 0 | 
| "banana" | "abcd" | 0 |
| "banana" | "bananan" | 0 |

solution.js:
```javascript
function solution(my_string, is_prefix) {
    return my_string.slice(0, is_prefix.length) === is_prefix ? 1 : 0;
}
```

---

문제 :  
#### 문자열 바꿔서 찾기 

설명 :  
문자 "A"와 "B"로 이루어진 문자열 myString과 pat가 주어집니다. myString의 "A"를 "B"로, "B"를 "A"로 바꾼 문자열의 연속하는 부분 문자열 중 pat이 있으면 1을 아니면 0을 return 하는 solution 함수를 완성하세요.

입출력 예  
| myString | pat | result |
| :-: | :-: | :-: |
| "ABBAA" | "AABB" | 1 |
| "ABAB" | "ABAB" | 0 |

solution.js:
```javascript
function solution(myString, pat) {
    var answer = 0;
    myString = myString.split('');
    for(let i in myString) {
        if(myString[i] === 'A') myString[i] = 'B'
        else myString[i] = 'A'
    }
    myString = myString.join('')
    return myString.includes(pat) ? 1 : 0;   
}
```

---

문제 :  
#### 문자 리스트를 문자열로 변환하기 

설명 :  
문자들이 담겨있는 배열 arr가 주어집니다. arr의 원소들을 순서대로 이어 붙인 문자열을 return 하는 solution함수를 작성해 주세요.

입출력 예  
| arr | result | 
| :-: | :-: |
| ["a","b","c"]	| "abc" |

solution.js:
```javascript
function solution(arr) {
    var answer = '';
    answer = arr.join('');
    return answer;
}
```

---

문제 :  
#### rny_string 

설명 :  
'm'과 "rn"이 모양이 비슷하게 생긴 점을 활용해 문자열에 장난을 하려고 합니다. 문자열 rny_string이 주어질 때, rny_string의 모든 'm'을 "rn"으로 바꾼 문자열을 return 하는 solution 함수를 작성해 주세요.

입출력 예  
| rny_string | result |
| :-: | :-: | 
| "masterpiece" | "rnasterpiece" | 
| "programmers" | "prograrnrners" | 
| "jerry" | "jerry" | 
| "burn" | "burn" |

solution.js:
```javascript
function solution(rny_string) {
    let answer = '';
    for(let i = 0; i < rny_string.length; i++) {
        if(rny_string[i] === 'm') answer += 'rn'
        else answer += rny_string[i];
    }
    return answer;
}
```

---

문제 :  
#### 마지막 두 원소 

설명 :  
정수 리스트 num_list가 주어질 때, 마지막 원소가 그전 원소보다 크면 마지막 원소에서 그전 원소를 뺀 값을 마지막 원소가 그전 원소보다 크지 않다면 마지막 원소를 두 배한 값을 추가하여 return하도록 solution 함수를 완성해주세요.

입출력 예  
| num_list | result |
| :-: | :-: | 
| [2, 1, 6]	| [2, 1, 6, 5] |
| [5, 2, 1, 7, 5] | [5, 2, 1, 7, 5, 10] |

solution.js:
```javascript
function solution(num_list) {
    num_list[num_list.length - 1] > num_list[num_list.length - 2] ? 
        num_list.push(num_list[num_list.length - 1] - num_list[num_list.length - 2]) : 
            num_list.push(num_list[num_list.length - 1] * 2)
    return num_list;
}
```

---

문제 :  
#### 배열 만들기 1 

설명 :  
정수 n과 k가 주어졌을 때, 1 이상 n이하의 정수 중에서 k의 배수를 오름차순으로 저장한 배열을 return 하는 solution 함수를 완성해 주세요.

입출력 예  
| n | k | result |
| :-: | :-: | :-: |
| 10 | 3 | [3, 6, 9] |
| 15 | 5 | [5, 10, 15] |

solution.js:
```javascript
function solution(n, k) {
    var answer = [];
    for(let i = 1; i <= n; i++) {
        if(i % k === 0) answer.push(i);
    }
    return answer;
}
```

---

문제 :  
#### 원하는 문자열 찾기 

설명 :  
알파벳으로 이루어진 문자열 myString과 pat이 주어집니다. myString의 연속된 부분 문자열 중 pat이 존재하면 1을 그렇지 않으면 0을 return 하는 solution 함수를 완성해 주세요.  
단, 알파벳 대문자와 소문자는 구분하지 않습니다.

입출력 예  
| myString | pat | return |
| :-: | :-: | :-: |
| "AbCdEfG" | "aBc" | 1 |
| "aaAA" | "aaaaa" | 0 |

solution.js:
```javascript
function solution(myString, pat) {
    myString = myString.toLowerCase();
    pat = pat.toLowerCase();
    return myString.includes(pat) ? 1 : 0;
}
```

---

문제 :  
#### n 번째 원소까지 

설명 :  
정수 리스트 num_list와 정수 n이 주어질 때, num_list의 첫 번째 원소부터 n 번째 원소까지의 모든 원소를 담은 리스트를 return하도록 solution 함수를 완성해주세요.

입출력 예  
| num_list | n | result |
| :-: | :-: | :-: |
| [2, 1, 6] | 1 | [2] |
| [5, 2, 1, 7, 5] | 3 | [5, 2, 1] |

solution.js:
```javascript
function solution(num_list, n) {
    num_list.length = n
    return num_list;
}
```

---

문제 :  
#### n 번째 원소부터 

설명 :  
정수 리스트 num_list와 정수 n이 주어질 때, n 번째 원소부터 마지막 원소까지의 모든 원소를 담은 리스트를 return하도록 solution 함수를 완성해주세요.

입출력 예  
| num_list | n | result |
| :-: | :-: | :-: |
| [2, 1, 6] | 3 | [6] | 
| [5, 2, 1, 7, 5] | 2 | [2, 1, 7, 5] |

solution.js:
```javascript
function solution(num_list, n) {
    return num_list.slice(n-1);
}
```

---

문제 :  
#### 문자열 붙여서 출력하기 

설명 :  
두 개의 문자열 str1, str2가 공백으로 구분되어 입력으로 주어집니다.
입출력 예와 같이 str1과 str2을 이어서 출력하는 코드를 작성해 보세요.

입출력 예  
| 입력 | 출력 |
| :-: | :-: |
| apple pen | applepen |
| Hello World! | HelloWorld! |

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
    str1 = input[0];
    str2 = input[1];
    console.log(str1 + str2);
});
```

---

문제 :
#### 조건에 맞게 수열 변환하기 1

설명 :  
정수 배열 arr가 주어집니다. arr의 각 원소에 대해 값이 50보다 크거나 같은 짝수라면 2로 나누고, 50보다 작은 홀수라면 2를 곱합니다. 그 결과인 정수 배열을 return 하는 solution 함수를 완성해 주세요.

입출력 예  
| arr | result |
| :-: | :-: |
| [1, 2, 3, 100, 99, 98] | [2, 2, 6, 50, 99, 49] |

solution.js:
```javascript
function solution(arr) {
    var answer = [];
    for(let i in arr) {
        if(arr[i] >= 50 && arr[i] % 2 === 0) arr[i] /= 2;
        else if(arr[i] < 50 && arr[i] % 2 === 1) arr[i] *= 2
    }
    return arr;
}
```
