### 문제 1

두 문자열을 입력받아, 대소문자를 구분하지 않고(case insensitive) 두 문자열이 동일한지를 반환하는 함수를 작성하세요.

예:
```
insensitiveEqual('hello', 'hello'); -> true
insensitiveEqual('hello', 'Hello'); -> true
insensitiveEqual('hello', 'world'); -> false
```
---
```js
function insensitiveEqual(str1, str2){
  if (str1.toLowerCase() === str2.toLowerCase()) {
    return true;
  } else {
    return false;
  }
}

function insensitiveEqual(str1, str2){
  if ()) {
    return str1.toLowerCase() === str2.toLowerCase();
  } else {
    return false;
  }
}
```
### 문제 2

문자열 `s`와 자연수 `n`을 입력받아, 만약 `s`의 길이가 `n`보다 작으면 `s`의 왼쪽에 공백으로 추가해서 길이가 `n`이 되게 만든 후 반환하고, 아니면 `s`를 그대로 반환하는 함수를 작성해보세요.

예:
```
leftPad('hello', 8); -> '   hello'
leftPad('hello', 3); -> 'hello'
```
---
```js
function leftPad(str, num){
  if(str.length < n){
    const spaceLength = num - str.length;
    return ' '.repeat(spaceLength) + str;
  } else {
    return str;
  }
}
```

### 문제 3

문자열을 입력받아, 문자열 안에 들어있는 모든 모음(a, e, i, o, u)의 갯수를 반환하는 함수를 작성하세요.
---
```js
function countVowel(str) {
  let count = 0;
  for(let i = 0; i < str.length; i++) {
    if(str[i] === 'a' || str[i] === 'e' || str[i] === 'i' || str[i] === 'o' || str[i] === 'u'){
      count++;
    } 
  }
  return count;
}

function countVowel(str) {
  let count = 0;
  for(let i = 0; i < str.length; i++) {
    if(
      str[i] === 'a' || 
      str[i] === 'e' || 
      str[i] === 'i' || 
      str[i] === 'o' || 
      str[i] === 'u'
      ){
      count++;
    } 
  }
  return count;
}
```

### 문제 4

문자열을 입력받아, 해당 문자열에 포함된 문자의 종류와 갯수를 나타내는 객체를 반환하는 함수를 작성하세요.

예:
```
countChar('tomato'); -> {t: 2, o: 2, m: 1, a: 1}
```
---
```js
function countChar(str) {
  const obj = {};
  for(let i = 0; i < str.length; i++) {
    const char = str[i];
    if (obj[char] == null) {
      obj[char] = 1;
    } else {
      obj[char]++;
    }
  }
  return obj;
}
```

### 문제 5

문자열을 입력받아 그 문자열이 회문(palindrome)인지 판별하는 함수를 작성하세요. (회문이란, '토마토', 'never odd or even'과 같이 뒤에서부터 읽어도 똑같이 읽히는 문자열을 말합니다.)
---
```js
function isPalindrome(str) {
 for (let i = 0; i < str.length / 2; i++) {
   if (str[i] !== str[str.length - i - 1]){
    return false;
    }
  }
 return true;
}

function isPalindrome(str) {
  return [...str].reverse().join('') === str;
}
```

### 문제 6

문자열을 입력받아, 그 문자열의 모든 '부분 문자열'로 이루어진 배열을 반환하는 함수를 작성하세요.

예:
```
subString('햄버거');
// 결과: ['햄', '햄버', '햄버거', '버', '버거', '거']
```
---
```js
function subString(str){
  const arr = [];
  for (let i = 0; i < str.length; i++){
    for (let j = i + 1; j < str.length + 1; j++){
      arr.push(str.slice(i, j));
    } 
    return arr;
  } 
}

subString('햄버거');
```
### 문제 7

문자열을 입력받아, 해당 문자열에서 중복된 문자가 제거된 새로운 문자열을 반환하는 함수를 작성하세요.

예:
```
removeDuplicates('tomato'); -> 'toma'
removeDuplicates('bartender'); -> 'bartend'
```
---
```js
function removeDuplicates(str){
  let newStr = '';
  for(let i = 0; i < str.length; i++){
    if(!newStr.includes(str[i])){
      newStr += str[i];
    }
  }
  return newStr;
}

removeDuplicates('tomato');
```
### 문제 8

이메일 주소를 입력받아, 아이디 부분을 별표(`*`)로 가린 새 문자열을 반환하는 함수를 작성하세요.

- 루프로 먼저 풀어보세요.
- `split` 메소드를 이용해서 풀어보세요.
---
```js
function emailAddr(email){
  const arr = email.split('@');
  const atPos = '*'.repeat(arr[0].length); 
  return atPos + '@' + arr[1]
}

emailAddr('echwn@gmail.com');
```
### 문제 9

문자열을 입력받아, 대문자는 소문자로, 소문자는 대문자로 바꾼 결과를 반환하는 함수를 작성하세요.
---
```js
function swapCase(str){
  let newStr = '';
  for (let i = 0; i < str.length; i++){
    if (str[i].toLowerCase() === str[i]) {
      newStr += str[i].toUpperCase();
    } else {
      newStr += str[i].toLowerCase();
    }
  }
  return newStr;
}
```
### 문제 10

문자열을 입력받아, 각 단어의 첫 글자를 대문자로 바꾼 결과를 반환하는 함수를 작성하세요. (문자열에 개행이 없다고 가정합니다.)
---
```js
function Capitalize(str){
  let newStr = '';
  for(let i = 0; i < str.length; i++){
    if (str[i] === 0 || str[i - 1] === ' ' ) {
      newStr += str[i]toUpperCase();
    } else {
      newStr += str[i];
    }
  }
  return newStr;
}

Capitalize('hallo chaewon');
```

### 문제 11

문자열을 입력받아, 문자열 안에 들어있는 단어 중 가장 긴 단어의 길이를 반환하는 함수를 작성하세요. (문자열에 개행이 없다고 가정합니다.)
---
```js
function maxLength(str) {
  let currentLen = 0;
  let maxLen = 0;
  for(let i = 0; i < str.length; i++){
    if (str[i] === ' '){
      maxLen = maxLen > currentLen ? maxLen : currentLen;
      currentLen = 0;
    } else {
      currentLen++;
    }
  }
  return maxLen > currentLen ? maxLen : currentLen;
}

maxLength('hallo ich bin chaewon');


function maxLength(str){
  const words = str.split(' ');
  let maxLen = 0; 
  for(let i = 0; i < words.length; i++){
    maxLen = words[i].length > maxLen ? words[i].length : maxLen;
  } 
  return maxLen;
}

maxLength('hallo ich bin chaewon');
```

### 문제 12

문자열 `s`과 자연수 `n`을 입력받아, `s`의 첫 `n`개의 문자만으로 이루어진 새 문자열을 반환하는 함수를 작성하세요.

### 문제 13

Camel case의 문자열을 입력받아, snake case로 바꾼 새 문자열을 반환하는 함수를 작성하세요.

### 문제 14

Snake case의 문자열을 입력받아, camel case로 바꾼 새 문자열을 반환하는 함수를 작성하세요.

### 문제 15

`String.prototype.split`과 똑같이 동작하는 함수를 작성하세요.

예:
```
split('Hello World'); -> ['Hello World']
split('Hello World', ' '); -> ['Hello', 'World']
split('let,const,var', ',') -> ['let', 'const', 'var']
```

### 문제 16

2진수를 표현하는 문자열을 입력받아, 그 문자열이 나타내는 수 타입의 값을 반환하는 함수를 작성하세요. (`parseInt`를 사용하지 말고 작성해보세요.)

예:
```
convertBinary('1101'); -> 13
```

### 문제 17

숫자로만 이루어진 문자열을 입력받아, 연속된 두 짝수 사이에 하이픈(-)을 끼워넣은 문자열을 반환하는 함수를 작성하세요.

예:
```
insertHyphen('437027423'); -> '4370-274-23'
```
