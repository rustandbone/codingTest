### 101~120 of 224  

1.	[ad 제거하기](#ad-제거하기)
2.	[접미사 배열](#접미사-배열)
3.	[배열의 원소 삭제하기](#배열의-원소-삭제하기)
4.	[369게임](#369게임)
5.	[약수 구하기](#약수-구하기)
6.	[5명씩](#5명씩)
7.	[할 일 목록](#할-일-목록)
8.	[피자 나눠 먹기 (2)](#피자-나눠-먹기-2)
9.	[0 떼기](#0-떼기)
10.	[순서 바꾸기](#순서-바꾸기)
11.	[외계행성의 나이](#외계행성의-나이)
12.	[배열 회전시키기](#배열-회전시키기)
13.	[인덱스 바꾸기](#인덱스-바꾸기)
14.	[l로 만들기](#l로-만들기)
15.	[가장 큰 수 찾기](#가장-큰-수-찾기)
16.	[부분 문자열 이어 붙여 문자열 만들기](#부분-문자열-이어-붙여-문자열-만들기)
17.	[배열 비교하기](#배열-비교하기)
18.	[덧셈식 출력하기](#덧셈식-출력하기)
19.	[문자열 정렬하기 (1)](#문자열-정렬하기-1)
20.	[공백으로 구분하기 2](#공백으로-구분하기-2)

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
#### ad 제거하기 

설명 :  
문자열 배열 strArr가 주어집니다. 배열 내의 문자열 중 "ad"라는 부분 문자열을 포함하고 있는 모든 문자열을 제거하고 남은 문자열을 순서를 유지하여 배열로 return 하는 solution 함수를 완성해 주세요.

입출력 예  
| strArr | result | 
| :-: | :-: |
| ["and","notad","abcd"] | ["and","abcd"] |
| ["there","are","no","a","ds"] | ["there","are","no","a","ds"] |

solution.js:
```javascript
function solution(strArr) {
    var answer = [];

    for(let i in strArr) {
        strArr[i].includes("ad") ? strArr : answer.push(strArr[i]);
    }

    return answer;
}
```

---

문제 :  
#### 접미사 배열 

설명 :  
어떤 문자열에 대해서 접미사는 특정 인덱스부터 시작하는 문자열을 의미합니다. 예를 들어, "banana"의 모든 접미사는 "banana", "anana", "nana", "ana", "na", "a"입니다.  
문자열 my_string이 매개변수로 주어질 때, my_string의 모든 접미사를 사전순으로 정렬한 문자열 배열을 return 하는 solution 함수를 작성해 주세요.

입출력 예  
| my_string | result |
| :-: | :-: |
| "banana" | ["a", "ana", "anana", "banana", "na", "nana"] |
| "programmers" | ["ammers", "ers", "grammers", "mers", "mmers", "ogrammers", "programmers", "rammers", "rogrammers", "rs", "s"] |

solution.js:
```javascript
function solution(my_string) {
    var answer = [];
    for(let i = 0; i < my_string.length; i++) {
        answer[i]= my_string.slice(i);
    }
    return answer.sort();
}
```

---

문제 :  
#### 배열의 원소 삭제하기 

설명 :  
정수 배열 arr과 delete_list가 있습니다. arr의 원소 중 delete_list의 원소를 모두 삭제하고 남은 원소들은 기존의 arr에 있던 순서를 유지한 배열을 return 하는 solution 함수를 작성해 주세요.

입출력 예  
| arr | delete_list | result |
| :-: | :-: | :-: |
| [293, 1000, 395, 678, 94] | [94, 777, 104, 1000, 1, 12] | [293, 395, 678] | 
| [110, 66, 439, 785, 1] | [377, 823, 119, 43] | [110, 66, 439, 785, 1] |

solution.js:
```javascript
function solution(arr, delete_list) {
    return arr.filter(x => !delete_list.includes(x));
}
```

---

문제 :  
#### 369게임

설명 :  
머쓱이는 친구들과 369게임을 하고 있습니다. 369게임은 1부터 숫자를 하나씩 대며 3, 6, 9가 들어가는 숫자는 숫자 대신 3, 6, 9의 개수만큼 박수를 치는 게임입니다. 머쓱이가 말해야하는 숫자 order가 매개변수로 주어질 때, 머쓱이가 쳐야할 박수 횟수를 return 하도록 solution 함수를 완성해보세요.

입출력 예  
| order | result |  
| :-: | :-: |
| 3 | 1 |
| 29423 | 2 |

solution.js:
```javascript
function solution(order) {
    var answer = 0;
    let arr = Array.from(String(order));
    for(let n of arr) {
        if(n === '0') continue;
        else if(n % 3 === 0) answer++;
    }
    return answer;
}
```

---

문제 :  
#### 약수 구하기

설명 :  
정수 n이 매개변수로 주어질 때, n의 약수를 오름차순으로 담은 배열을 return하도록 solution 함수를 완성해주세요.

입출력 예  
| n | result |
| :-: | :-: | 
| 24 | [1, 2, 3, 4, 6, 8, 12, 24] |
| 29 | [1, 29] |

solution.js:
```javascript
function solution(n) {
    var answer = [];
    for(let i = 1; i <= n; i++) {
        if(n % i === 0) {
            answer.push(i)
        }
    }
    return answer;
}
```

---

문제 :  
#### 5명씩 

설명 :  
최대 5명씩 탑승가능한 놀이기구를 타기 위해 줄을 서있는 사람들의 이름이 담긴 문자열 리스트 names가 주어질 때, 앞에서 부터 5명씩 묶은 그룹의 가장 앞에 서있는 사람들의 이름을 담은 리스트를 return하도록 solution 함수를 완성해주세요. 마지막 그룹이 5명이 되지 않더라도 가장 앞에 있는 사람의 이름을 포함합니다.

입출력 예  
| names | result | 
| :-: | :-: |
| ["nami", "ahri", "jayce", "garen", "ivern", "vex", "jinx"] | ["nami", "vex"] |

solution.js:
```javascript
function solution(names) {
    var answer = [];
    for(let i = 0; i < names.length; i += 5) {
        answer.push(names[i])
    }
    return answer;
}
```

---

문제 :  
#### 할 일 목록 

설명 :  
오늘 해야 할 일이 담긴 문자열 배열 todo_list와 각각의 일을 지금 마쳤는지를 나타내는 boolean 배열 finished가 매개변수로 주어질 때, todo_list에서 아직 마치지 못한 일들을 순서대로 담은 문자열 배열을 return 하는 solution 함수를 작성해 주세요.

입출력 예  
| todo_list | finished | result |
| :-: | :-: | :-: |
| ["problemsolving", "practiceguitar", "swim", "studygraph"] | [true, false, true, false] | ["practiceguitar", "studygraph"] |

solution.js:
```javascript
function solution(todo_list, finished) {
    var answer = [];
    for(let i in todo_list) {
        if (!finished[i]) answer.push(todo_list[i]); 
    }
    return answer;
}
```

---

문제 :  
#### 피자 나눠 먹기 (2)

설명 :  
머쓱이네 피자가게는 피자를 여섯 조각으로 잘라 줍니다. 피자를 나눠먹을 사람의 수 n이 매개변수로 주어질 때, n명이 주문한 피자를 남기지 않고 모두 같은 수의 피자 조각을 먹어야 한다면 최소 몇 판을 시켜야 하는지를 return 하도록 solution 함수를 완성해보세요.

입출력 예  
| n | result |
| :-: | :-: |
| 6 | 1 |
| 10 | 5 |
| 4 | 2 |

solution.js:
```javascript
function solution(n) {
    let pizza = 6;
    while(pizza % n !== 0) {
        pizza += 6;
    }
    return pizza / 6;
}
```

---

문제 :  
#### 0 떼기 

설명 :  
정수로 이루어진 문자열 n_str이 주어질 때, n_str의 가장 왼쪽에 처음으로 등장하는 0들을 뗀 문자열을 return하도록 solution 함수를 완성해주세요.

입출력 예  
| n_str | result |  
| :-: | :-: |
| "0010" | "10" |
| "854020" | "854020" |

solution.js:
```javascript
function solution(n_str) {
    let arr = n_str.split("");
    for(let i in arr) {
        if(arr[i] > 0) return arr.slice(i).join('');
    }
}
```

---

문제 :  
#### 순서 바꾸기 

설명 :  
정수 리스트 num_list와 정수 n이 주어질 때, num_list를 n 번째 원소 이후의 원소들과 n 번째까지의 원소들로 나눠 n 번째 원소 이후의 원소들을 n 번째까지의 원소들 앞에 붙인 리스트를 return하도록 solution 함수를 완성해주세요.

입출력 예  
| num_list | n | result |
| :-: | :-: | :-: |
| [2, 1, 6] | 1 | [1, 6, 2] |
| [5, 2, 1, 7, 5] | 3 | [7, 5, 5, 2, 1] |

solution.js:
```javascript
function solution(num_list, n) {    
    let add = num_list.slice(n);
    return add.concat(num_list.slice(0, n));
}
```

---

문제 :  
#### 외계행성의 나이

설명 :  
우주여행을 하던 머쓱이는 엔진 고장으로 PROGRAMMERS-962 행성에 불시착하게 됐습니다. 입국심사에서 나이를 말해야 하는데, PROGRAMMERS-962 행성에서는 나이를 알파벳으로 말하고 있습니다. a는 0, b는 1, c는 2, ..., j는 9입니다. 예를 들어 23살은 cd, 51살은 fb로 표현합니다. 나이 age가 매개변수로 주어질 때 PROGRAMMER-962식 나이를 return하도록 solution 함수를 완성해주세요.

입출력 예  
| age | result |
| :-: | :-: |
| 23 | "cd" |
| 51 | "fb" |
| 100 | "baa" |

solution.js:
```javascript
function solution(age) {
    var answer = '';
    let ageArr = [...age.toString()];
    const trans = Array.from({ length: 10 }, (v, i) => String.fromCharCode(i + 97));
    for(let i = 0; i < ageArr.length; i++) {
        answer += trans[ageArr[i]]
    }
    return answer;
}
```

---

문제 :  
#### 배열 회전시키기

설명 :  
정수가 담긴 배열 numbers와 문자열 direction가 매개변수로 주어집니다. 배열 numbers의 원소를 direction방향으로 한 칸씩 회전시킨 배열을 return하도록 solution 함수를 완성해주세요.

입출력 예  
| numbers | direction | result |
| :-: | :-: | :-: |
| [1, 2, 3] | "right" | [3, 1, 2] | 
| [4, 455, 6, 4, -1, 45, 6] | "left" | [455, 6, 4, -1, 45, 6, 4] |

solution.js:
```javascript
function solution(numbers, direction) {
    var answer = [];
    let n;
    if(direction === 'right') {
        n = numbers.at(-1);
        numbers.pop();
        numbers.unshift(n);
    } else {
        n = numbers.at(0);
        numbers.shift();
        numbers.push(n);
    }
    return numbers;
}
```

---

문제 :  
#### 인덱스 바꾸기

설명 :  
문자열 my_string과 정수 num1, num2가 매개변수로 주어질 때, my_string에서 인덱스 num1과 인덱스 num2에 해당하는 문자를 바꾼 문자열을 return 하도록 solution 함수를 완성해보세요.

입출력 예  
| my_string | num1 | num2 | result |
| :-: | :-: | :-: | :-: |
| "hello" | 1 | 2 | "hlelo" |
| "I love you" | 3 | 6 | "I l veoyou" |

solution.js:
```javascript
function solution(my_string, num1, num2) {
    var answer = '';
    let str1 = [...my_string[num1]]
    let str2 = [...my_string[num2]]
    my_string = my_string.split("")
    my_string.splice(num1, 1, str2)
    my_string.splice(num2, 1, str1);
    return my_string.join("");
}
```

---

문제 :  
#### l로 만들기 

설명 :  
알파벳 소문자로 이루어진 문자열 myString이 주어집니다. 알파벳 순서에서 "l"보다 앞서는 모든 문자를 "l"로 바꾼 문자열을 return 하는 solution 함수를 완성해 주세요.

입출력 예  
| myString | result |  
| :-: | :-: | 
| "abcdevwxyz" | "lllllvwxyz" |
| "jjnnllkkmm" | "llnnllllmm" |

solution.js:
```javascript
function solution(myString) {
    var answer = '';
    for(let  i = 0; i < myString.length; i++) {
        if(myString[i] < 'l') answer += 'l';
        else answer += myString[i];
    }
    return answer;
}
```

---

문제 :  
#### 가장 큰 수 찾기

설명 :  
정수 배열 array가 매개변수로 주어질 때, 가장 큰 수와 그 수의 인덱스를 담은 배열을 return 하도록 solution 함수를 완성해보세요.

입출력 예  
| array | result | 
| :-: | :-: | 
| [1, 8, 3] | [8, 1] |
| [9, 10, 11, 8] | [11, 2] |

solution.js:
```javascript
function solution(array) {
    var answer = [];
    answer[0] = Math.max(...array);
    answer[1] = array.indexOf(Math.max(...array))
    return answer;
}
```

---

문제 :  
#### 부분 문자열 이어 붙여 문자열 만들기 

설명 :  
길이가 같은 문자열 배열 my_strings와 이차원 정수 배열 parts가 매개변수로 주어집니다. parts[i]는 [s, e] 형태로, my_string[i]의 인덱스 s부터 인덱스 e까지의 부분 문자열을 의미합니다. 각 my_strings의 원소의 parts에 해당하는 부분 문자열을 순서대로 이어 붙인 문자열을 return 하는 solution 함수를 작성해 주세요.

입출력 예  
| my_strings | parts | result |
| :-: | :-: | :-: |
| ["progressive", "hamburger", "hammer", "ahocorasick"] | [[0, 4], [1, 2], [3, 5], [7, 7]] | "programmers" |

solution.js:
```javascript
function solution(my_strings, parts) {
    var answer = '';
    for(let i = 0; i < my_strings.length; i++) {
        answer += my_strings[i].slice(parts[i][0], parts[i][1]+1);
    }
    return answer;
}
```

---

문제 :  
#### 배열 비교하기 

설명 :  
이 문제에서 두 정수 배열의 대소관계를 다음과 같이 정의합니다.

- 두 배열의 길이가 다르다면, 배열의 길이가 긴 쪽이 더 큽니다.
- 배열의 길이가 같다면 각 배열에 있는 모든 원소의 합을 비교하여 다르다면 더 큰 쪽이 크고, 같다면 같습니다.

두 정수 배열 arr1과 arr2가 주어질 때, 위에서 정의한 배열의 대소관계에 대하여 arr2가 크다면 -1, arr1이 크다면 1, 두 배열이 같다면 0을 return 하는 solution 함수를 작성해 주세요.

입출력 예  
| arr1 | arr2 | result |
| :-: | :-: | :-: |
| [49, 13] | [70, 11, 2] | -1 |
| [100, 17, 84, 1] | [55, 12, 65, 36] | 1 |
| [1, 2, 3, 4, 5] | [3, 3, 3, 3, 3] | 0 |

solution.js:
```javascript
function solution(arr1, arr2) {
    var answer = 0;
    let a = 0;
    let b = 0;
    
    if(arr1.length !== arr2.length) {
        arr1.length > arr2.length ? answer = 1 : answer = -1
    }
    else {
        for(let i in arr1) {
            a += Number(arr1[i])
            b += Number(arr2[i])
        }
        
        a > b ? answer = 1 : answer = -1;
        if(a === b) return 0;
    }
    return answer;
}
```

---

문제 :  
#### 덧셈식 출력하기 

설명 :  
두 정수 a, b가 주어질 때 다음과 같은 형태의 계산식을 출력하는 코드를 작성해 보세요.
`a + b = c`

입출력 예  
| 입력 | 출력 | 
| :-: | :-: |
| 4 5 | 4 + 5 = 9 |

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
    console.log(`${Number(input[0])} + ${Number(input[1])} = ${Number(input[0]) + Number(input[1])}`);
});
```

---

문제 :  
#### 문자열 정렬하기 (1)

설명 :  
문자열 my_string이 매개변수로 주어질 때, my_string 안에 있는 숫자만 골라 오름차순 정렬한 리스트를 return 하도록 solution 함수를 작성해보세요.

입출력 예  
| my_string | result | 
| :-: | :-: |
| "hi12392" | [1, 2, 2, 3, 9] |
| "p2o4i8gj2" | [2, 2, 4, 8] |
| "abcde0" | [0] |

solution.js:
```javascript
function solution(my_string) {
    var answer = [];
    for(let s of my_string) {
        if(s === '0') answer.push(0);
        else if(parseInt(s)) {
            answer.push(parseInt(s));
        }
    }
    return answer.sort((a,b) => a - b);
}
```

---

문제 :  
#### 공백으로 구분하기 2 

설명 :  
단어가 공백 한 개 이상으로 구분되어 있는 문자열 my_string이 매개변수로 주어질 때, my_string에 나온 단어를 앞에서부터 순서대로 담은 문자열 배열을 return 하는 solution 함수를 작성해 주세요.

입출력 예  
| my_string | result | 
| :-: | :-: |
| " i    love  you" | ["i", "love", "you"] |
| "    programmers  " | ["programmers"] |

solution.js:
```javascript
function solution(my_string) {
    var answer = [];
    my_string = my_string.trim().split(' ')
    for(let i in my_string) {
        if(my_string[i] !== "") answer.push(my_string[i]);
    }
    return answer;
}
```
