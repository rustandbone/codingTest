### 21~40 of 224  

1. [공배수](#공배수)
2. [flag에 따라 다른 값 반환하기](#flag에-따라-다른-값-반환하기)
3. [문자열을 정수로 변환하기](#문자열을-정수로-변환하기)
4. [문자 반복 출력하기](#문자-반복-출력하기)
5. [부분 문자열](#부분-문자열)
6. [정수 부분](#정수-부분)
7. [원소들의 곱과 합](#원소들의-곱과-합)
8. [배열 두 배 만들기](#배열-두-배-만들기)
9. [배열의 유사도](#배열의-유사도)
10.	[머쓱이보다 키 큰 사람](#머쓱이보다-키-큰-사람)
11.	[옷가게 할인 받기](#옷가게-할인-받기)
12.	[순서쌍의 개수](#순서쌍의-개수)
13.	[최댓값 만들기(1)](#최댓값-만들기(1))
14.	[중복된 숫자 개수](#중복된-숫자-개수)
15.	[중앙값 구하기](#중앙값-구하기)
16.	[특정 문자 제거하기](#특정-문자-제거하기)
17.	[피자 나눠 먹기 (3)](#피자-나눠-먹기-(3))
18.	[아이스 아메리카노](#아이스-아메리카노)
19.	[점의 위치 구하기](#점의-위치-구하기)
20.	[문자열 뒤집기](#문자열-뒤집기)

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
#### 공배수  

설명 :  
정수 number와 n, m이 주어집니다. number가 n의 배수이면서 m의 배수이면 1을 아니라면 0을 return하도록 solution 함수를 완성해주세요.

입출력 예  
| number | n | m | result |
| :-: | :-: | :-: | :-: |
| 60 | 2 | 3 | 1 |
| 55 | 10 | 5 | 0 |

solution.js:
```javascript
function solution(number, n, m) {
    var answer = 0;
    return answer = (number % n === 0 && number % m === 0) ? 1 : 0; 
}
```

---

문제 :  
#### flag에 따라 다른 값 반환하기  

설명 :  
두 정수 a, b와 boolean 변수 flag가 매개변수로 주어질 때, flag가 true면 a + b를 false면 a - b를 return 하는 solution 함수를 작성해 주세요.

입출력 예  
| a | b | flag | result |
| :-: | :-: | :-: | :-: |
| -4 | 7 | true | 3 |
| -4 |7 | false | -11 |

solution.js:
```javascript
function solution(a, b, flag) {
    return answer = flag === true ? a + b : a - b;
}
```

---

문제 :  
#### 문자열을 정수로 변환하기  

설명 :  
숫자로만 이루어진 문자열 n_str이 주어질 때, n_str을 정수로 변환하여 return하도록 solution 함수를 완성해주세요.

입출력 예  
| n_str | result | 
| :-: | :-: |
|"10" | 10 |
| "8542" | 8542 | 

solution.js:
```javascript
function solution(n_str) {
    return parseInt(n_str);
}
```

---

문제 :  
#### 문자 반복 출력하기  

설명 :  
문자열 my_string과 정수 n이 매개변수로 주어질 때, my_string에 들어있는 각 문자를 n만큼 반복한 문자열을 return 하도록 solution 함수를 완성해보세요.

입출력 예  
| my_string | n | result |
| :-: | :-: | :-: |
| "hello" | 3 | "hhheeellllllooo" |

solution.js:
```javascript
function solution(my_string, n) {
    var answer = '';
    for(let str of my_string) {
        for(let i = 0; i < n; i++) {
            answer += str;
        }
    }
    return answer;
}
```

---

문제 :  
#### 부분 문자열  

설명 :  
어떤 문자열 A가 다른 문자열 B안에 속하면 A를 B의 부분 문자열이라고 합니다. 예를 들어 문자열 "abc"는 문자열 "aabcc"의 부분 문자열입니다.  
문자열 str1과 str2가 주어질 때, str1이 str2의 부분 문자열이라면 1을 부분 문자열이 아니라면 0을 return하도록 solution 함수를 완성해주세요.

입출력 예  
| str1 | str2 | result |
| :-: | :-: | :-: |
| "abc" | "aabcc" | 1 | 
| "tbt" | "tbbttb" | 0 |

solution.js:
```javascript
function solution(str1, str2) {
    return str2.includes(str1) ? 1 : 0;
}
```

---

문제 :  
#### 정수 부분  

설명 :  
실수 flo가 매개 변수로 주어질 때, flo의 정수 부분을 return하도록 solution 함수를 완성해주세요.

입출력 예  
| flo | result |  
| :-: | :-: | 
| 1.42 | 1 |
| 69.32 | 69 |

solution.js:
```javascript
function solution(flo) {
    var answer = 0;
    return answer = parseInt(flo);
}
```

---

문제 :  
#### 원소들의 곱과 합  

설명 :  
정수가 담긴 리스트 num_list가 주어질 때, 모든 원소들의 곱이 모든 원소들의 합의 제곱보다 작으면 1을 크면 0을 return하도록 solution 함수를 완성해주세요.

입출력 예  
| num_list | result |
| :-: | :-: |
| [3, 4, 5, 2, 1] | 1 |
| [5, 7, 8, 3] | 0 |

solution.js:
```javascript
function solution(num_list) {
    var answer = 0;
    let multiply = 1;
    let sum = 0;
    for(let i = 0; i < num_list.length; i++) {
        sum += num_list[i]
        multiply *= num_list[i]
    }
    return answer = multiply > (sum * sum) ? 0 : 1;
}
```

---

문제 :  
#### 배열 두 배 만들기  

설명 :  
정수 배열 numbers가 매개변수로 주어집니다. numbers의 각 원소에 두배한 원소를 가진 배열을 return하도록 solution 함수를 완성해주세요.

입출력 예  
| numbers | result | 
| :-: | :-: |
| [1, 2, 3, 4, 5] | [2, 4, 6, 8, 10] |
| [1, 2, 100, -99, 1, 2, 3] | [2, 4, 200, -198, 2, 4, 6] | 

solution.js:
```javascript
function solution(numbers) {
    return numbers.map(num => num * 2);
}
```

---

문제 :  
#### 배열의 유사도  

설명 :  
두 배열이 얼마나 유사한지 확인해보려고 합니다. 문자열 배열 s1과 s2가 주어질 때 같은 원소의 개수를 return하도록 solution 함수를 완성해주세요.

입출력 예  
| s1 | s2 | result |
| :-: | :-: | :-: |
| ["a", "b", "c"] | ["com", "b", "d", "p", "c"] | 2 |
| ["n", "omg"] | ["m", "dot"] | 0 |

solution.js:
```javascript
function solution(s1, s2) {
    var answer = 0;
    for(let i of s1) {
        for(let j of s2) {
            if(i === j) answer++;
        }
    }
    return answer;
}
```

---

문제 :  
#### 머쓱이보다 키 큰 사람  

설명 :  
머쓱이는 학교에서 키 순으로 줄을 설 때 몇 번째로 서야 하는지 궁금해졌습니다. 머쓱이네 반 친구들의 키가 담긴 정수 배열 array와 머쓱이의 키 height가 매개변수로 주어질 때, 머쓱이보다 키 큰 사람 수를 return 하도록 solution 함수를 완성해보세요.

입출력 예  
| array | height | result |
| :-: | :-: | :-: |
| [149, 180, 192, 170] | 167 | 3 | 
| [180, 120, 140] | 190 |	0 |

solution.js:
```javascript
function solution(array, height) {
    var answer = 0;
    array.map((a) => {
        if(a > height) answer++;
    })
    return answer;
}
```

---

문제 :  
#### 옷가게 할인 받기  

설명 :   
머쓱이네 옷가게는 10만 원 이상 사면 5%, 30만 원 이상 사면 10%, 50만 원 이상 사면 20%를 할인해줍니다.  
구매한 옷의 가격 price가 주어질 때, 지불해야 할 금액을 return 하도록 solution 함수를 완성해보세요.

입출력 예  
| price | result |  
| :-: | :-: |
| 150,000 | 142,500 |
| 580,000 | 464,000 |

solution.js:
```javascript
function solution(price) {
    var answer = 0;
    return price >= 500000 ? parseInt(price * 0.8) : 
            price >= 300000 ? parseInt(price * 0.9) : 
            price >= 100000 ? parseInt(price * 0.95) : price;
}
```

---

문제 :  
#### 순서쌍의 개수  

설명 :  
순서쌍이란 두 개의 숫자를 순서를 정하여 짝지어 나타낸 쌍으로 (a, b)로 표기합니다. 자연수 n이 매개변수로 주어질 때 두 숫자의 곱이 n인 자연수 순서쌍의 개수를 return하도록 solution 함수를 완성해주세요.

입출력 예  
| n | result |
| :-: | :-: |
| 20 | 6 |
| 100 | 9 |

solution.js:
```javascript
function solution(n) {
    var answer = 0;
    for(let  i = 1; i <= n; i++) {
        if(n % i === 0) answer++;
    }
    return answer;
}
```

---

문제 :  
#### 최댓값 만들기(1)  

설명 :  
정수 배열 numbers가 매개변수로 주어집니다. numbers의 원소 중 두 개를 곱해 만들 수 있는 최댓값을 return하도록 solution 함수를 완성해주세요.

입출력 예  
| numbers | result | 
| :-: | :-: | 
| [1, 2, 3, 4, 5] |	20 |
| [0, 31, 24, 10, 1, 9] | 744 |

solution.js:
```javascript
function solution(numbers) {
    numbers.sort((a,b) => a - b)
    return numbers.at(-1) * numbers.at(-2);
}
```

---

문제 :  
#### 중복된 숫자 개수  

설명 :  
정수가 담긴 배열 array와 정수 n이 매개변수로 주어질 때, array에 n이 몇 개 있는 지를 return 하도록 solution 함수를 완성해보세요.

입출력 예  
| array | n | result |
| :-: | :-: | :-: |
| [1, 1, 2, 3, 4, 5] | 1 | 2 |
| [0, 2, 3, 4] | 1 | 0 |

solution.js:
```javascript
function solution(array, n) {
    var answer = 0;
    for(let arr of array) {
        if(arr === n) answer++;
    }
    return answer;
}
```

---

문제 :  
#### 중앙값 구하기  

설명 :  
중앙값은 어떤 주어진 값들을 크기의 순서대로 정렬했을 때 가장 중앙에 위치하는 값을 의미합니다. 예를 들어 1, 2, 7, 10, 11의 중앙값은 7입니다. 정수 배열 array가 매개변수로 주어질 때, 중앙값을 return 하도록 solution 함수를 완성해보세요.

입출력 예  
| array | result |
| :-: | :-: |
| [1, 2, 7, 10, 11] |	7 |
| [9, -1, 0] | 0 |

solution.js:
```javascript
function solution(array) {
    array.sort((a,b) => a - b);
    return array[parseInt(array.length/2)];
}
```

---

문제 :  
#### 특정 문자 제거하기  

설명 :  
문자열 my_string과 문자 letter이 매개변수로 주어집니다. my_string에서 letter를 제거한 문자열을 return하도록 solution 함수를 완성해주세요.

입출력 예  
| my_string | letter | result |
| :-: | :-: | :-: |
| "abcdef" | "f" | "abcde" |
| "BCBdbe" | "B" | "Cdbe" |

solution.js:
```javascript
function solution(my_string, letter) {
    return (my_string.split("").map((str) => {
        if(str !== letter) return str;
    })).join('');
}
```

---

문제 :  
#### 피자 나눠 먹기 (3)  

설명 :  
머쓱이네 피자가게는 피자를 두 조각에서 열 조각까지 원하는 조각 수로 잘라줍니다. 피자 조각 수 slice와 피자를 먹는 사람의 수 n이 매개변수로 주어질 때, n명의 사람이 최소 한 조각 이상 피자를 먹으려면 최소 몇 판의 피자를 시켜야 하는지를 return 하도록 solution 함수를 완성해보세요.

입출력 예  
| slice | n | result |
| :-: | :-: | :-: |
| 7 | 10 | 2 |
| 4 | 12 | 3 |

solution.js:
```javascript
function solution(slice, n) {
    for(let i = 1; i < 51; i++) {
        slice *= i;
        if(n / slice <= 1) return i;
        else slice = slice /= i  
    }
}
```

---

문제 :  
#### 아이스 아메리카노  

설명 :  
머쓱이는 추운 날에도 아이스 아메리카노만 마십니다. 아이스 아메리카노는 한잔에 5,500원입니다. 머쓱이가 가지고 있는 돈 money가 매개변수로 주어질 때, 머쓱이가 최대로 마실 수 있는 아메리카노의 잔 수와 남는 돈을 순서대로 담은 배열을 return 하도록 solution 함수를 완성해보세요.

입출력 예  
| money | result | 
| :-: | :-: | 
| 5,500 | [1, 0] | 
| 15,000 | [2, 4000] |

solution.js:
```javascript
function solution(money) {
    return [parseInt(money / 5500), money % 5500];
}
```

---

문제 :  
#### 점의 위치 구하기  

설명 :  
사분면은 한 평면을 x축과 y축을 기준으로 나눈 네 부분입니다. 사분면은 아래와 같이 1부터 4까지 번호를 매깁니다.
- x 좌표와 y 좌표가 모두 양수이면 제1사분면에 속합니다.
- x 좌표가 음수, y 좌표가 양수이면 제2사분면에 속합니다.
- x 좌표와 y 좌표가 모두 음수이면 제3사분면에 속합니다.
- x 좌표가 양수, y 좌표가 음수이면 제4사분면에 속합니다.

x 좌표 (x, y)를 차례대로 담은 정수 배열 dot이 매개변수로 주어집니다. 좌표 dot이 사분면 중 어디에 속하는지 1, 2, 3, 4 중 하나를 return 하도록 solution 함수를 완성해주세요.  

입출력 예  
| dot | result |
| :-: | :-: | 
| [2, 4] | 1 | 
| [-7, 9] | 2 |  

solution.js:
```javascript
function solution(dot) {
    return dot[0] > 0 && dot[1] > 0 ? 1 : dot[0] > 0 ? 4 : dot[1] > 0 ? 2 : 3;
}
```

---

문제 :  
#### 문자열 뒤집기  

설명 :  
문자열 my_string이 매개변수로 주어집니다. my_string을 거꾸로 뒤집은 문자열을 return하도록 solution 함수를 완성해주세요.

입출력 예  
| my_string | return |
| :-: | :-: |
| "jaron" | "noraj" |
| "bread" | "daerb" |

solution.js:
```javascript
function solution(my_string) {
    return my_string.split("").reverse().join('');
}
```
