### 161~180 of 224  

1.	[2의 영역](#2의-영역)
2.	[qr code](#qr-code)
3.	[문자열 묶기](#문자열-묶기)
4.	[구슬을 나누는 경우의 수](#구슬을-나누는-경우의-수)
5.	[커피 심부름](#커피-심부름)
6.	[조건에 맞게 수열 변환하기 2](#조건에-맞게-수열-변환하기-2)
7.	[수열과 구간 쿼리 4](#수열과-구간-쿼리-4)
8.	[특수문자 출력하기](#특수문자-출력하기)
9.	[문자열 계산하기](#문자열-계산하기)
10.	[잘라서 배열로 저장하기](#잘라서-배열로-저장하기)
11.	[영어가 싫어요](#영어가-싫어요)
12.	[배열의 길이를 2의 거듭제곱으로 만들기](#배열의-길이를-2의-거듭제곱으로-만들기)
13.	[공 던지기](#공-던지기)
14.	[세 개의 구분자](#세-개의-구분자)
15.	[7의 개수](#7의-개수)
16.	[빈 배열에 추가, 삭제하기](#빈-배열에-추가,-삭제하기)
17.	[소인수분해](#소인수분해)
18.	[문자열이 몇 번 등장하는지 세기](#문자열이-몇-번-등장하는지-세기)
19.	[가까운 수](#가까운-수)
20.	[합성수 찾기](#합성수-찾기)

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
#### 2의 영역 

설명 :  
정수 배열 arr가 주어집니다. 배열 안의 2가 모두 포함된 가장 작은 연속된 부분 배열을 return 하는 solution 함수를 완성해 주세요.  
단, arr에 2가 없는 경우 [-1]을 return 합니다.

입출력 예  
| arr | result |
| :-: | :-: | 
| [1, 2, 1, 4, 5, 2, 9] | [2, 1, 4, 5, 2] |
| [1, 2, 1] | [2] | 
| [1, 1, 1] | [-1] |
| [1, 2, 1, 2, 1, 10, 2, 1] | [2, 1, 2, 1, 10, 2] |

solution.js:
```javascript
function solution(arr) {
    let answer = arr.slice(arr.indexOf(2), arr.lastIndexOf(2)+1);
    answer.length === 0 ? answer.push(-1) : answer;
    return answer;
}
```

---

문제 :  
#### qr code

설명 :  
두 정수 q, r과 문자열 code가 주어질 때, code의 각 인덱스를 q로 나누었을 때 나머지가 r인 위치의 문자를 앞에서부터 순서대로 이어 붙인 문자열을 return 하는 solution 함수를 작성해 주세요.

입출력 예  
| q | r | code | result |
| :-: | :-: | :-: | :-: |
| 3 | 1 | "qjnwezgrpirldywt" | "jerry" |
| 1 | 0 | "programmers" | "programmers" |

solution.js:
```javascript
function solution(q, r, code) {
    var answer = '';
    for(let [index, arr] of code.split("").entries()) {
        if(index % q === r) answer += arr;
    }
    return answer;
}
```

---

문제 :  
#### 문자열 묶기

설명 :  
문자열 배열 strArr이 주어집니다. strArr의 원소들을 길이가 같은 문자열들끼리 그룹으로 묶었을 때 가장 개수가 많은 그룹의 크기를 return 하는 solution 함수를 완성해 주세요.

입출력 예  
| strArr | result |
| :-: | :-: |
| ["a","bc","d","efg","hi"] | 2 |

solution.js:
```javascript
function solution(strArr) {
    var answer = [];
    
    let count = strArr.map(x => x.length);
    const result = count.reduce((accu, curr) => { 
        accu[curr] = (accu[curr] || 0) + 1; 
        return accu;
    }, {});

    for(let i in result) {
        answer.push(result[i]);
    }
    
    return Math.max(...answer);
}
```

---

문제 :  
#### 구슬을 나누는 경우의 수

설명 :  
머쓱이는 구슬을 친구들에게 나누어주려고 합니다. 구슬은 모두 다르게 생겼습니다. 머쓱이가 갖고 있는 구슬의 개수 balls와 친구들에게 나누어 줄 구슬 개수 share이 매개변수로 주어질 때, balls개의 구슬 중 share개의 구슬을 고르는 가능한 모든 경우의 수를 return 하는 solution 함수를 완성해주세요.

입출력 예  
| balls | share | result |
| :-: | :-: | :-: |
| 3 | 2 | 3 |
| 5 | 3 | 10|

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
#### 커피 심부름

설명 :  
팀의 막내인 철수는 아메리카노와 카페 라테만 판매하는 카페에서 팀원들의 커피를 사려고 합니다. 아메리카노와 카페 라테의 가격은 차가운 것과 뜨거운 것 상관없이 각각 4500, 5000원입니다. 각 팀원에게 마실 메뉴를 적어달라고 하였고, 그 중에서 메뉴만 적은 팀원의 것은 차가운 것으로 통일하고 "아무거나"를 적은 팀원의 것은 차가운 아메리카노로 통일하기로 하였습니다.  
각 직원이 적은 메뉴가 문자열 배열 order로 주어질 때, 카페에서 결제하게 될 금액을 return 하는 solution 함수를 작성해주세요. order의 원소는 아래의 것들만 들어오고, 각각의 의미는 다음과 같습니다.  
| order의 원소 | 의미 | 
| :-: | :-: |
| "iceamericano", "americanoice" | 차가운 아메리카노 |
| "hotamericano", "americanohot" | 따뜻한 아메리카노 |
| "icecafelatte", "cafelatteice" | 차가운 카페 라테 |
| "hotcafelatte", "cafelattehot" | 따뜻한 카페 라테 |
| "americano" | 아메리카노 |
| "cafelatte" | 카페 라테 |
| "anything" | 아무거나 |



입출력 예  
| order | result |
| :-: | :-: |
| ["cafelatte", "americanoice", "hotcafelatte", "anything"] | 19000 |
| ["americanoice", "americano", "iceamericano"] | 13500 |

solution.js:
```javascript
function solution(order) {
    var answer = 0;
    for(let menu of order) {
        if(menu.includes('cafelatte')) answer += 5000;
        else answer += 4500;
    }
    return answer;
}
```

---

문제 :  
#### 조건에 맞게 수열 변환하기 2

설명 :  
정수 배열 arr가 주어집니다. arr의 각 원소에 대해 값이 50보다 크거나 같은 짝수라면 2로 나누고, 50보다 작은 홀수라면 2를 곱하고 다시 1을 더합니다.  
이러한 작업을 x번 반복한 결과인 배열을 arr(x)라고 표현했을 때, arr(x) = arr(x + 1)인 x가 항상 존재합니다. 이러한 x 중 가장 작은 값을 return 하는 solution 함수를 완성해 주세요.  
단, 두 배열에 대한 "="는 두 배열의 크기가 서로 같으며, 같은 인덱스의 원소가 각각 서로 같음을 의미합니다.

입출력 예  
| arr | result |
| :-: | :-: |
| [1, 2, 3, 100, 99, 98] | 5 |

solution.js:
```javascript
function solution(arr) {
    var answer = 0;
    let before = [];
    
    for(let i = 0; i < 1000000; i++) {
        before = [...arr];
        for(let a in arr) {
            if(arr[a] >= 50 && arr[a] % 2 === 0) {
                arr[a] /= 2;
            } else if (arr[a] < 50 && arr[a] % 2 === 1){
                arr[a] *= 2;
                arr[a]++;
            }
        }
        ++answer;
        if(arr.length === before.length && 
           arr.every((value, idx) => value === before[idx])) break;
    }
    
    return answer-1;
}
```

---

문제 :  
#### 수열과 구간 쿼리 4

설명 :  
정수 배열 arr와 2차원 정수 배열 queries이 주어집니다. queries의 원소는 각각 하나의 query를 나타내며, [s, e, k] 꼴입니다.  
각 query마다 순서대로 s ≤ i ≤ e인 모든 i에 대해 i가 k의 배수이면 arr[i]에 1을 더합니다.  
위 규칙에 따라 queries를 처리한 이후의 arr를 return 하는 solution 함수를 완성해 주세요.

입출력 예  
| arr | queries | result |
| :-: | :-: | :-: |
| [0, 1, 2, 4, 3] | [[0, 4, 1],[0, 3, 2],[0, 3, 3]] | [3, 2, 4, 6, 4] |

solution.js:
```javascript
function solution(arr, queries) {
    var answer = [...arr];
    let temp = [];
    for(let i = 0; i < queries.length; i++) {
        temp = arr.slice(queries[i][0], queries[i][1] + 1);
        for(let j = queries[i][0]; j <= queries[i][1]; j++) {
            if(j % queries[i][2] === 0) answer[j]++;
        }
    }
    return answer;
}
```

---

문제 :  
#### 특수문자 출력하기

설명 :  
다음과 같이 출력하도록 코드를 작성해 주세요.

입출력 예  
| 출력 |
| :-: |
| !@#$%^&*(\'"<>?:; |

solution.js:
```javascript
const readline = require('readline');
const rl = readline.createInterface({
    input: process.stdin,
    output: process.stdout
});

rl.on('close', function () {
    console.log(`!@#$%^&*(\\'"<>?:;`);
});
```

---

문제 :  
#### 문자열 계산하기

설명 :  
my_string은 "3 + 5"처럼 문자열로 된 수식입니다. 문자열 my_string이 매개변수로 주어질 때, 수식을 계산한 값을 return 하는 solution 함수를 완성해주세요.

입출력 예  
| my_string | result | 
| :-: | :-: |
| "3 + 4" | 7 |

solution.js:
```javascript
function solution(my_string) {
    var answer = 0;
    let arr = my_string.split(" ");
    for(let i = 0; i < arr.length; i++) {
        if(i === 0) answer += Number(arr[i]);
        
        if(arr[i] === '+') {
            answer += Number(arr[i+1]);
        } else if(arr[i] === '-') {
            answer -= arr[i+1];
        }
    }
    
    return answer;
}
```

---

문제 :  
#### 잘라서 배열로 저장하기

설명 :  
문자열 my_str과 n이 매개변수로 주어질 때, my_str을 길이 n씩 잘라서 저장한 배열을 return하도록 solution 함수를 완성해주세요.

입출력 예  
| my_str | n | result |
| :-: | :-: | :-: |
| "abc1Addfggg4556b" | 6 | ["abc1Ad", "dfggg4", "556b"] |
| "abcdef123" | 3 | ["abc", "def", "123"] |

solution.js:
```javascript
function solution(my_str, n) {
    var answer = [];
    for(let i = 0; i < my_str.length; i = i + n) {
        answer.push(my_str.slice(i, i + n))
    }
    return answer;
}
```

---

문제 :  
#### 영어가 싫어요

설명 :  
영어가 싫은 머쓱이는 영어로 표기되어있는 숫자를 수로 바꾸려고 합니다. 문자열 numbers가 매개변수로 주어질 때, numbers를 정수로 바꿔 return 하도록 solution 함수를 완성해 주세요.

입출력 예  
| numbers | result |
| :-: | :-: | 
| "onetwothreefourfivesixseveneightnine" | 123456789 |
| "onefourzerosixseven" | 14067 |

solution.js:
```javascript
function solution(numbers) {
    var answer = '';
    let engNum = ["zero", "one", "two", "three", "four", "five", "six", "seven", "eight", "nine"]
    let num = ["0", "1", "2", "3", "4", "5", "6", "7", "8", "9"]
    for(let i = 0; i < 10; i++) {
        answer = numbers.replaceAll(engNum[i], num[i])
        numbers = answer;
    }
    
    return Number(answer);
}
```

---

문제 :  
#### 배열의 길이를 2의 거듭제곱으로 만들기

설명 :  
정수 배열 arr이 매개변수로 주어집니다. arr의 길이가 2의 정수 거듭제곱이 되도록 arr 뒤에 정수 0을 추가하려고 합니다. arr에 최소한의 개수로 0을 추가한 배열을 return 하는 solution 함수를 작성해 주세요.

입출력 예  
| arr | result |
| :-: | :-: |
| [1, 2, 3, 4, 5, 6]	[1, 2, 3, 4, 5, 6, 0, 0]
[58, 172, 746, 89]	[58, 172, 746, 89] |

solution.js:
```javascript
function solution(arr) {
    var answer = [];
    for(let i = 0; i <= 1000; i++) {
        if(arr.length <= 2 ** i) {
            answer = Array.from({length: 2 ** i}, () => 0);;
            answer.splice(0, arr.length, arr.splice(0, arr.length, arr));
            break;
        };
    }
    return answer.flat(1);
}
```

---

문제 :  
#### 공 던지기

설명 :  
머쓱이는 친구들과 동그랗게 서서 공 던지기 게임을 하고 있습니다. 공은 1번부터 던지며 오른쪽으로 한 명을 건너뛰고 그다음 사람에게만 던질 수 있습니다. 친구들의 번호가 들어있는 정수 배열 numbers와 정수 K가 주어질 때, k번째로 공을 던지는 사람의 번호는 무엇인지 return 하도록 solution 함수를 완성해보세요.

입출력 예  
| numbers | k | result |
| :-: | :-: | :-: |
| [1, 2, 3, 4] | 2 | 3 |
| [1, 2, 3, 4, 5, 6] | 5 | 3 |
| [1, 2, 3] | 3 | 2 |

solution.js:
```javascript
function solution(numbers, k) {
    var answer = 0;
    for(let i = 0; i < k*2; i += 2) {
        answer = i;
    }
    while(answer > numbers.length) {
        answer -= numbers.length;
    }
    return numbers[answer];
}
```

---

문제 :  
#### 세 개의 구분자

설명 :  
임의의 문자열이 주어졌을 때 문자 "a", "b", "c"를 구분자로 사용해 문자열을 나누고자 합니다.  
예를 들어 주어진 문자열이 "baconlettucetomato"라면 나눠진 문자열 목록은 ["onlettu", "etom", "to"] 가 됩니다.  
문자열 myStr이 주어졌을 때 위 예시와 같이 "a", "b", "c"를 사용해 나눠진 문자열을 순서대로 저장한 배열을 return 하는 solution 함수를 완성해 주세요.  
단, 두 구분자 사이에 다른 문자가 없을 경우에는 아무것도 저장하지 않으며, return할 배열이 빈 배열이라면 ["EMPTY"]를 return 합니다.  

입출력 예  
| myStr | result |
| :-: | :-: |
| "baconlettucetomato" | ["onlettu", "etom", "to"] |
| "abcd" | ["d"] | 
| "cabab" | ["EMPTY"] |

solution.js:
```javascript
function solution(myStr) {
    var answer = [];
    answer = myStr.split(/[a,b,c]/).filter(str => str);
    if(answer.length === 0) answer.push("EMPTY")
    return answer;
}
```

---

문제 :  
#### 7의 개수

설명 :  
머쓱이는 행운의 숫자 7을 가장 좋아합니다. 정수 배열 array가 매개변수로 주어질 때, 7이 총 몇 개 있는지 return 하도록 solution 함수를 완성해보세요.

입출력 예  
| array | result |
| :-: | :-: |
| [7, 77, 17] | 4 |
| [10, 29] | 0 |

solution.js:
```javascript
function solution(array) {
    var answer = '';
    answer += [...array]
    return answer.split(7).length - 1;
}
```

---

문제 :  
#### 빈 배열에 추가, 삭제하기

설명 :  
아무 원소도 들어있지 않은 빈 배열 X가 있습니다. 길이가 같은 정수 배열 arr과 boolean 배열 flag가 매개변수로 주어질 때, flag를 차례대로 순회하며 flag[i]가 true라면 X의 뒤에 arr[i]를 arr[i] × 2 번 추가하고, flag[i]가 false라면 X에서 마지막 arr[i]개의 원소를 제거한 뒤 X를 return 하는 solution 함수를 작성해 주세요.

입출력 예  
| arr | flag | result |
| :-: | :-: | :-: |
| [3, 2, 4, 1, 3] | [true, false, true, false, false] | [3, 3, 3, 3, 4, 4, 4, 4] |

solution.js:
```javascript
function solution(arr, flag) {
    var answer = [];
    for(let [i,a] of arr.entries()) {
        if(flag[i]) {
            for(let j = 0; j < arr[i]*2; j++) {
                answer.push(Number(arr[i]));
            }
        }
        else {
            for(let j = 0; j < arr[i]; j++) {
                answer.pop();
            }
        }
    }
    return answer;
}
```

---

문제 :  
#### 소인수분해

설명 :  
소인수분해란 어떤 수를 소수들의 곱으로 표현하는 것입니다. 예를 들어 12를 소인수 분해하면 2 * 2 * 3 으로 나타낼 수 있습니다. 따라서 12의 소인수는 2와 3입니다. 자연수 n이 매개변수로 주어질 때 n의 소인수를 오름차순으로 담은 배열을 return하도록 solution 함수를 완성해주세요.

입출력 예  
| n | result |
| :-: | :-: |
| 12 | [2, 3] |
| 17 | [17] |
| 420 | [2, 3, 5, 7] |

solution.js:
```javascript
function solution(n) {
    var answer = [];
    let num = 2;
    while(n !== 1) {
        if(n % num === 0) {
            n /= num;
            answer.push(num);
        }
        else {
            num++;
        }
    }
    const set = new Set(answer.sort((a,b) => a-b))
    return [...set];
}
```

---

문제 :  
#### 문자열이 몇 번 등장하는지 세기

설명 :  
문자열 myString과 pat이 주어집니다. myString에서 pat이 등장하는 횟수를 return 하는 solution 함수를 완성해 주세요.

입출력 예  
| myString | pat | result |
| :-: | :-: | :-: |
| "banana" | "ana" | 2 |
| "aaaa" | "aa" | 3 |

solution.js:
```javascript
function solution(myString, pat) {
    var answer = 0;
    for(let [i, ele] of myString.split("").entries()) {
        if(myString.slice(i, i+pat.length) === pat) answer++;
    }
    return answer;
}
```

---

문제 :  
#### 가까운 수

설명 :  
정수 배열 array와 정수 n이 매개변수로 주어질 때, array에 들어있는 정수 중 n과 가장 가까운 수를 return 하도록 solution 함수를 완성해주세요.

입출력 예  
| array | n | result |
| :-: | :-: | :-: |
| [3, 10, 28] | 20 | 28 |
| [10, 11, 12] | 13 | 12 |

solution.js:
```javascript
function solution(array, n) {
    var answer = [];
    array.sort((a,b) => a - b).map(a => answer.push(Math.abs(a - n)));
    console.log(answer, array, answer.indexOf(Math.min(...answer)))
    return array[answer.indexOf(Math.min(...answer))];
}
```

---

문제 :  
#### 합성수 찾기

설명 :  
약수의 개수가 세 개 이상인 수를 합성수라고 합니다. 자연수 n이 매개변수로 주어질 때 n이하의 합성수의 개수를 return하도록 solution 함수를 완성해주세요.

입출력 예  
| n | result |
| :-: | :-: |
| 10 | 5 | 
| 15 | 8 | 

solution.js:
```javascript
function solution(n) {
    var answer = 0;
    let check = 0;
    for(let i = 4; i <= n; i++) {
        check = 0;
        for(let j = 1; j <= i; j++) {
            if(i % j === 0) {
                check++;
            }
        }
        if(check > 2) answer++;
    }
    return answer;
}
```
