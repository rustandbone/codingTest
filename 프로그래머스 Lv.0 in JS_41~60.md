### 41~60 of 224  

1.	[길이에 따른 연산](#길이에-따른-연산)
2.	[문자열 정수의 합](#문자열-정수의-합)
3.	[수 조작하기 1](#수-조작하기-1)
4.	[소문자로 바꾸기](#소문자로-바꾸기)
5.	[부분 문자열인지 확인하기](#부분-문자열인지-확인하기)
6.	[카운트 다운](#카운트-다운)
7.	[조건에 맞게 수열 변환하기 3](#조건에-맞게-수열-변환하기-3)
8.	[n보다 커질 때까지 더하기](#n보다-커질-때까지-더하기)
9.	[공백으로 구분하기 1](#공백으로-구분하기-1)
10.	[짝수는 싫어요](#짝수는-싫어요)
11.	[정수 찾기](#정수-찾기)
12.	[배열에서 문자열 대소문자 변환하기](#배열에서-문자열-대소문자-변환하기)
13.	[문자열의 뒤의 n글자](#문자열의-뒤의-n글자)
14.	[카운트 업](#카운트-업)
15.	[숨어있는 숫자의 덧셈 (1)](#숨어있는-숫자의-덧셈-(1))
16.	[문자열의 앞의 n글자](#문자열의-앞의-n글자)
17.	[대문자로 바꾸기](#대문자로-바꾸기)
18.	[자릿수 더하기](#자릿수-더하기)
19.	[문자열로 변환](#문자열로-변환)
20.	[n의 배수](#n의-배수)

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
#### 길이에 따른 연산 

설명 :  
정수가 담긴 리스트 num_list가 주어질 때, 리스트의 길이가 11 이상이면 리스트에 있는 모든 원소의 합을 10 이하이면 모든 원소의 곱을 return하도록 solution 함수를 완성해주세요.

입출력 예  
| num_list | result |   
| :-: | :-: | 
| [3, 4, 5, 2, 5, 4, 6, 7, 3, 7, 2, 2, 1] | 51 |
| [2, 3, 4, 5] | 120 |

solution.js:
```javascript
function solution(num_list) {
    let answer = 0;
    if(num_list.length > 10) {
        for(let i = 0; i < num_list.length; i++) {
            answer += num_list[i]
        }
    } else {
        answer = 1;
        for(let i = 0; i < num_list.length; i++) {
            answer *= num_list[i]
        }
    }
    return answer;
}
```

---

문제 :  
#### 문자열 정수의 합 

설명 :  
한 자리 정수로 이루어진 문자열 num_str이 주어질 때, 각 자리수의 합을 return하도록 solution 함수를 완성해주세요.

입출력 예  
| num_str | result | 
| :-: | :-: | 
| "123456789" | 45 |
| "1000000" | 1 |

solution.js:
```javascript
function solution(num_str) {
    var answer = 0;
    for(let i = 0; i < num_str.length; i++) {
        answer += parseInt(num_str[i]);
    }
    return answer;
}
```

---

문제 :  
#### 수 조작하기 1 

설명 :  
정수 n과 문자열 control이 주어집니다. control은 "w", "a", "s", "d"의 4개의 문자로 이루어져 있으며, control의 앞에서부터 순서대로 문자에 따라 n의 값을 바꿉니다.  
- "w" : n이 1 커집니다.
- "s" : n이 1 작아집니다.
- "d" : n이 10 커집니다.
- "a" : n이 10 작아집니다.  

위 규칙에 따라 n을 바꿨을 때 가장 마지막에 나오는 n의 값을 return 하는 solution 함수를 완성해 주세요.

입출력 예  
| n | control | result |
| :-: | :-: | :-: |
| 0 | "wsdawsdassw" | -1 |

solution.js:
```javascript
function solution(n, control) {
    for(let i = 0; i < control.length; i++) {
        if(control[i] === 'w') n += 1
        else if(control[i] === 's') n -= 1
        else if(control[i] === 'd') n += 10
        else n -= 10
    }
    return n;
}
```

---

문제 :  
#### 소문자로 바꾸기 

설명 :  
알파벳으로 이루어진 문자열 myString이 주어집니다. 모든 알파벳을 소문자로 변환하여 return 하는 solution 함수를 완성해 주세요.

입출력 예  
| myString | result | 
| :-: | :-: | 
| "aBcDeFg" | "abcdefg" |
| "aaa" | "aaa" |

solution.js:
```javascript
function solution(myString) {
    return myString.toLowerCase();
}
```

---

문제 :  
#### 부분 문자열인지 확인하기 

설명 :  
부분 문자열이란 문자열에서 연속된 일부분에 해당하는 문자열을 의미합니다. 예를 들어, 문자열 "ana", "ban", "anana", "banana", "n"는 모두 문자열 "banana"의 부분 문자열이지만, "aaa", "bnana", "wxyz"는 모두 "banana"의 부분 문자열이 아닙니다.  
문자열 my_string과 target이 매개변수로 주어질 때, target이 문자열 my_string의 부분 문자열이라면 1을, 아니라면 0을 return 하는 solution 함수를 작성해 주세요.

입출력 예  
| my_string | target | result |
| :-: | :-: | :-: |
| "banana" | "ana" | 1 |
| "banana" | "wxyz" | 0 |

solution.js:
```javascript
function solution(my_string, target) {
    return my_string.includes(target) > 0 ? 1 : 0;
}
```

---

문제 :  
#### 카운트 다운 

설명 :  
정수 start와 end가 주어질 때, start에서 end까지 1씩 감소하는 수들을 차례로 담은 리스트를 return하도록 solution 함수를 완성해주세요.

입출력 예  
| start | end | result |
| :-: | :-: | :-: |
| 10 | 3 | [10, 9, 8, 7, 6, 5, 4, 3] |

solution.js:
```javascript
function solution(start, end) {
    let answer = [];
    for(let i = start; i >= end; i--) {
        answer.push(i);
    }
    return answer;
}
```

---

문제 :  
#### 조건에 맞게 수열 변환하기 3 

설명 :  
정수 배열 arr와 자연수 k가 주어집니다.  
만약 k가 홀수라면 arr의 모든 원소에 k를 곱하고, k가 짝수라면 arr의 모든 원소에 k를 더합니다.  
이러한 변환을 마친 후의 arr를 return 하는 solution 함수를 완성해 주세요.

입출력 예  
| arr | k | result |
| :-: | :-: | :-: |
| [1, 2, 3, 100, 99, 98] | 3 | [3, 6, 9, 300, 297, 294] | 
| [1, 2, 3, 100, 99, 98] | 2 | [3, 4, 5, 102, 101, 100] |

solution.js:
```javascript
function solution(arr, k) {
    for(let i = 0; i < arr.length; i++) {
        if(k % 2 === 0) arr[i] = arr[i] + k;
        else arr[i] = arr[i] * k;
    }
    return arr;
}
```

---

문제 :  
#### n보다 커질 때까지 더하기 

설명 :  
정수 배열 numbers와 정수 n이 매개변수로 주어집니다. numbers의 원소를 앞에서부터 하나씩 더하다가 그 합이 n보다 커지는 순간 이때까지 더했던 원소들의 합을 return 하는 solution 함수를 작성해 주세요.

입출력 예  
| numbers | n | result |
| :-: | :-: | :-: |
| [34, 5, 71, 29, 100, 34] | 123 | 139 |
| [58, 44, 27, 10, 100] | 139 | 239 |

solution.js:
```javascript
function solution(numbers, n) {
    var answer = 0;
    for(let i = 0; i < numbers.length; i++) {
        if(n >= answer) answer += numbers[i]
        else break;
    }
    return answer;
}
```

---

문제 :  
#### 공백으로 구분하기 1 

설명 :  
단어가 공백 한 개로 구분되어 있는 문자열 my_string이 매개변수로 주어질 때, my_string에 나온 단어를 앞에서부터 순서대로 담은 문자열 배열을 return 하는 solution 함수를 작성해 주세요.

입출력 예  
| my_string | result |
| :-: | :-: | 
| "i love you" | ["i", "love", "you"] |
| "programmers" | ["programmers"] |

solution.js:
```javascript
function solution(my_string) {
    return my_string.split(" ");
}
```

---

문제 :  
#### 짝수는 싫어요

설명 :  
정수 n이 매개변수로 주어질 때, n 이하의 홀수가 오름차순으로 담긴 배열을 return하도록 solution 함수를 완성해주세요.

입출력 예  
| n | result |
| :-: | :-: | 
| 10 | [1, 3, 5, 7, 9] |
| 15 | [1, 3, 5, 7, 9, 11, 13, 15] |

solution.js:
```javascript
function solution(n) {
    return Array.from({length: n+1}, (v, i) => i).filter((num) => num % 2 === 1);
}
```

---

문제 :  
#### 정수 찾기 

설명 :  
정수 리스트 num_list와 찾으려는 정수 n이 주어질 때, num_list안에 n이 있으면 1을 없으면 0을 return하도록 solution 함수를 완성해주세요.

입출력 예  
| num_list | n | result |
| :-: | :-: | :-: |
| [1, 2, 3, 4, 5] | 3 | 1 |
| [15, 98, 23, 2, 15] | 20 | 0 |

solution.js:
```javascript
function solution(num_list, n) {
    return num_list.indexOf(n) > 0 ? 1 : 0;
}
```

---

문제 :  
#### 배열에서 문자열 대소문자 변환하기 

설명 :  
문자열 배열 strArr가 주어집니다. 모든 원소가 알파벳으로만 이루어져 있을 때, 배열에서 홀수번째 인덱스의 문자열은 모든 문자를 대문자로, 짝수번째 인덱스의 문자열은 모든 문자를 소문자로 바꿔서 반환하는 solution 함수를 완성해 주세요.

입출력 예  
| strArr | result |
| :-: | :-: |
| ["AAA","BBB","CCC","DDD"] | ["aaa","BBB","ccc","DDD"] |
| ["aBc","AbC"] | ["abc","ABC"] |

solution.js:
```javascript
function solution(strArr) {
    var answer = [];
    for(let i = 0; i < strArr.length; i++) {
        if(i % 2 === 0) answer[i] = strArr[i].toLowerCase("");
        else answer[i] = strArr[i].toUpperCase();
    }
    return answer;
}
```

---

문제 :  
#### 문자열의 뒤의 n글자 

설명 :  
문자열 my_string과 정수 n이 매개변수로 주어질 때, my_string의 뒤의 n글자로 이루어진 문자열을 return 하는 solution 함수를 작성해 주세요.

입출력 예  
| my_string | n | result |
| :-: | :-: | :-: |
| "ProgrammerS123" | 11 | "grammerS123" |
| "He110W0r1d" | 5 | "W0r1d" |

solution.js:
```javascript
function solution(my_string, n) {
    return my_string.slice(my_string.length-n);
}
```

---

문제 :  
#### 카운트 업 

설명 :  
정수 start와 end가 주어질 때, start부터 end까지의 숫자를 차례로 담은 리스트를 return하도록 solution 함수를 완성해주세요.

입출력 예  
| start | end | result |
| :-: | :-: | :-: |
| 3 | 10 | [3, 4, 5, 6, 7, 8, 9, 10] |

solution.js:
```javascript
function solution(start, end) {
    var answer = [];
    for(let i = start; i <= end; i++) {
        answer.push(i);
    }
    return answer;
}
```

---

문제 :  
#### 숨어있는 숫자의 덧셈 (1)

설명 :  
문자열 my_string이 매개변수로 주어집니다. my_string안의 모든 자연수들의 합을 return하도록 solution 함수를 완성해주세요.

입출력 예  
| my_string | result | 
| :-: | :-: | 
| "aAb1B2cC34oOp" | 10 |
| "1a2b3c4d123" | 16 |

solution.js:
```javascript
function solution(my_string) {
    var answer = 0;
    for(let num of my_string) {
        if(Number(num)) answer += Number(num);
    }
    return answer;
}
```

---

문제 :  
#### 문자열의 앞의 n글자 

설명 :  
문자열 my_string과 정수 n이 매개변수로 주어질 때, my_string의 앞의 n글자로 이루어진 문자열을 return 하는 solution 함수를 작성해 주세요.

입출력 예  
| my_string | n | result |
| :-: | :-: | :-: |
| "ProgrammerS123" | 11 | "ProgrammerS" | 
| "He110W0r1d" | 5 | "He110" |

solution.js:
```javascript
function solution(my_string, n) {
    let arr = my_string.split('');
    return answer = arr.splice(0, n).join('');
}
```

---

문제 :  
#### 대문자로 바꾸기 

설명 :  
알파벳으로 이루어진 문자열 myString이 주어집니다. 모든 알파벳을 대문자로 변환하여 return 하는 solution 함수를 완성해 주세요.

입출력 예  
| myString | result |  
| :-: | :-: | 
| "aBcDeFg" | "ABCDEFG" |
| "AAA" | "AAA" |

solution.js:
```javascript
function solution(myString) {
    return myString.toUpperCase();
}
```

---

문제 :  
#### 자릿수 더하기

설명 :  
정수 n이 매개변수로 주어질 때 n의 각 자리 숫자의 합을 return하도록 solution 함수를 완성해주세요

입출력 예  
| n | result | 
| :-: | :-: |
| 1234 | 10 |
| 930211 | 16 |

solution.js:
```javascript
function solution(n) {
    var answer = 0;
    for(let num of String(n)) {
        answer += Number(num);
    }
    return answer;
}
```

---

문제 :  
#### 문자열로 변환 

설명 :  
정수 n이 주어질 때, n을 문자열로 변환하여 return하도록 solution 함수를 완성해주세요.

입출력 예  
| n | result |  
| :-: | :-: |
| 123 | "123" |
| 2573 | "2573" |

solution.js:
```javascript
function solution(n) {
    return String(n);
}
```

---

문제 :  
#### n의 배수  

설명 :  
정수 num과 n이 매개 변수로 주어질 때, num이 n의 배수이면 1을 return n의 배수가 아니라면 0을 return하도록 solution 함수를 완성해주세요.

입출력 예  
| num | n | result |
| :-: | :-: | :-: |
| 98 | 2 | 1 |
| 34 | 3 | 0 |

solution.js:
```javascript
function solution(num, n) {
    var answer = 0;
    if(num % n === 0) answer = 1;
    return answer;
}
```
