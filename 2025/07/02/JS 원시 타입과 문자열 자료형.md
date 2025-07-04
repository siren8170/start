
# 1. 원시타입과 문자열 자료형

자바스크립트에서 **타입**(Type)은 한국어로 **자료형**이라고 합니다. 변수의 타입은 다양한 데이터를 용도에 맞게 사용하는 데 필요합니다. 예를 들어, 숫자 `1234`는 **number 타입**이고, 문자 `‘jeju’`는 **string 타입**입니다. 각각의 데이터 타입은 다른 기능을 지원합니다.

## 1.1 데이터 타입의 중요성

컴퓨터에 저장되는 값은 모두 2진수로 저장되지만, 숫자와 문자의 `+` 연산은 다른 결과를 낳습니다. 예를 들어, 숫자끼리 더하면 산술 연산을 하지만, 문자끼리 더하면 문자열을 연결합니다. 변수의 타입은 데이터가 어떻게 처리될지를 결정합니다.

```javascript
let num = 1234;
let str = 'jeju';
console.log(num + 1); // 1235 (숫자 더하기)
console.log(str + ' island'); // 'jeju island' (문자열 연결)
```

## 1.2 타입 확인하기

타입을 확인하기 위해 자바스크립트에서 `typeof` 연산자를 사용할 수 있습니다.

```javascript
let num = 1234;
let str = 'jeju';
console.log(typeof num); // 'number'
console.log(typeof str); // 'string'
```

하지만 배열과 같은 자료형은 `typeof`로 확인할 때 정확하지 않을 수 있습니다. 이는 자바스크립트에서는 배열이 객체로 인식되기 때문입니다.

```javascript
let arr = [1, 2, 3];
console.log(typeof arr); // 'object'

let obj = { name: 'jeju' };
console.log(typeof obj); // 'object'
```

이렇게 타입을 알기 위한 `typeof` 연산자가 정확하게 그 타입을 알려주지 않기 때문에 더 정확한 방법이 필요합니다. 이를 위해 `Object.prototype.toString.call`을 사용합니다.

```javascript
let arr = [1, 2, 3];
console.log(typeof arr); // 'object'
console.log(Object.prototype.toString.call(arr)); // '[object Array]'
```

타입 체크에 관한 더 자세한 내용은 [여기](https://www.notion.so/type-check-a9264b841abe40e995c700648a7f3294?pvs=21)를 참고해 주세요.

# 2. 타입의 종류

자바스크립트의 데이터 타입은 크게 두 가지로 나눌 수 있습니다.

1. **원시타입 (Primitive types)**: 간단한 값을 저장합니다.
2. **참조타입 (Reference types)**: 복잡한 데이터를 저장합니다.

## 2.1 원시타입

원시타입은 단순한 데이터 값을 저장하며, 다음과 같은 것들이 있습니다.

- **숫자 (Number)**: 숫자를 나타냅니다.

  ```javascript
  let age = 25; // Number 타입
  ```

- **문자열 (String)**: 텍스트를 나타냅니다.

  ```javascript
  let name = 'licat'; // String 타입
  ```

- **불리언 (Boolean)**: 참(true) 또는 거짓(false)을 나타냅니다.

  ```javascript
  let isStudent = true; // Boolean 타입
  ```

- **심볼 (Symbol)**: 고유한 식별자를 나타냅니다.

  ```javascript
  let uniqueId = Symbol('id'); // Symbol 타입
  ```

- **undefined**: 변수가 값을 갖고 있지 않음을 나타냅니다.

  ```javascript
  let value; // undefined 타입 (값이 할당되지 않음)
  ```

- **null**: 값이 없음을 나타냅니다.
  ```javascript
  let emptyValue = null; // null 타입 (의도적으로 값이 없음)
  ```

## 2.2 참조타입

참조타입은 복잡한 데이터를 저장하며, 다음과 같은 것들이 있습니다.

- **객체 (Object)**: 키-값 쌍을 저장합니다.

  ```javascript
  let person = {
    name: 'Bob',
    age: 30,
  }; // Object 타입
  ```

- **배열 (Array)**: 순서가 있는 리스트를 저장합니다.

  ```javascript
  let numbers = [1, 2, 3, 4, 5]; // Array 타입
  ```

- **함수 (Function)**: 실행 가능한 코드를 저장합니다.
  ```javascript
  function greet() {
    console.log('Hello, world!');
  } // Function 타입
  ```

원시타입은 한 번 설정되면 변경되지 않는 단순한 값들을 저장하는 반면, 참조타입은 더 복잡한 데이터 구조를 저장하며, 객체, 배열, 함수 등이 포함됩니다.

# 3. 원시타입

각 타입에 대해 좀 더 자세히 알아보도록 하겠습니다. 원시타입(Primitive Types)의 **특징**은 가리키고 있는 값이 변경 불가능하다는 것입니다.

```javascript
let str1 = 'hello';
str1[0]; // 0번째 값을 불러옵니다.
str1[1] = 'w'; // 바꿔보려 시도하지만, 바뀌지 않습니다.
```

# 4. 문자열

문자열(String)은 `작은따옴표(')`나 `큰따옴표(")`로 둘러싼 일련의 문자를 가르킵니다.

## 3.1. 문자열의 특징

1. 문자열은 순서가 있습니다. 순서는 0부터 시작하며 띄어쓰기도 문자로 취급합니다. 이 순서를 index라고 부르며 아래와 같이 각괄호([ ])를 사용해 특정 순서에 위치한 글자를 가져올 수 있습니다. 아래 예제에서 숫자를 바꿔가면서 실행해보세요.

   ```javascript
   let text = 'hello world';
   ```

   | text[0]  | h   |
   | -------- | --- |
   | text[1]  | e   |
   | text[2]  | l   |
   | text[3]  | l   |
   | text[4]  | o   |
   | text[5]  |     |
   | text[6]  | w   |
   | text[7]  | o   |
   | text[8]  | r   |
   | text[9]  | l   |
   | text[10] | d   |

   ```javascript
   let text = 'hello world';
   console.log(text[0]);
   console.log(text[6]);
   ```

2. 문자열은 length 라는 속성이 있습니다. length 속성을 통해 문자열의 길이를 구할 수 있습니다.

   ```javascript
   let myPassword = 'qwer123!@#';
   console.log(myPassword.length);
   ```

3. 한번 만들어진 문자열은 변하지 않습니다. 이러한 성질을 불변(immutable) 이라고 합니다. 아래 예시에서도 알 수 있듯 어떠한 문자열 메소드도 문자열 자체를 변경하지 않습니다. 새로운 문자열을 반환할 뿐입니다. 아래 예제에서 주석을 해제하고 실행해보세요. 에러가 발생하는 것을 확인할 수 있습니다. 브라우저 콘솔에서는 에러가 발생되지 않지만 그렇다 하더라도 문자열은 변경되지 않습니다.

   ```javascript
   let 불변성 = 'immutable';
   // 불변성[0] = 'l';
   // console.log(불변성);

   console.log(불변성.toUpperCase());
   console.log(불변성);
   ```

4. 문자열은 `+`연산자로 연결될 수 있습니다. 문자열은 연결된 순서만 동일하다면 같은 문자열로 판단합니다. `==`는 같은지를 비교하는 연산자입니다.

   ```javascript
   let one = 'hello';
   let two = ' world';

   console.log(one + two);
   console.log('hello world' == one + two);
   ```

## 3.2. 문자열 메소드

자바스크립트는 문자열 타입에서 사용할 수 있도록 여러가지 **메소드**를 지원하고 있습니다. 많이 사용하는 유용한 메소드 몇 가지를 살펴보겠습니다.

1. indexOf()

   문자열 안에 존재하는 특정한 문자를 검색하여 문자의 인덱스를 반환합니다. **검색할 문자**와 검색을 시작할 **인덱스 번호** 두 가지를 인자로 전달 할 수 있습니다. 문자열 안에 검색하고자하는 문자가 존재하지 않으면 -1을 반환합니다. 실행해보고 값을 확인해보세요.

   ```javascript
   let text = 'Next level 제껴라 제껴라 제껴라';
   console.log(text.indexOf('level'));
   console.log(text.indexOf('제껴라'));
   console.log(text.indexOf('제껴라', 16));
   console.log(text.indexOf('광야'));
   ```

2. replace()

   문자열안에서 일치하는 첫번째 문자열을 찾고, 대체하여 새로운 문자열을 반환합니다. 첫 번째 인자는 찾아야하는 문자열, 두 번째 인자는 대체할 값을 전달합니다. 정규표현식 지원하며 이를 이용해 g플래그를 사용하면 일치하는 모든 부분을 대체할 수 있습니다.

   ```javascript
   console.log('제껴라 제껴라 제껴라 huh!'.replace('제껴라', 'check it out'));
   console.log('제껴라 제껴라 제껴라 huh!'.replace(/제껴라/g, 'check it out'));
   ```

   
> 💡  **정규표현식**(**Regular Expression**)은 자바스크립트 뿐만 아니라 파이썬, 자바 등에서도 널리 사용되는 문자열을 검색하거나 대체할 때 사용하는 패턴입니다. 정규표현식은 문자열을 다루는데 유용하며, 문자열의 검색, 대체, 분리 등을 할 때 사용됩니다.


3. slice()

   slice는 "얇게 썰다"라는 의미처럼 문자열의 일부분을 복사하여(썰어서) 새로운 문자열을 반환합니다. 시작 인덱스와 종료 인덱스를 인자로 전달합니다. 종료 인덱스는 옵션이며 기본값은 문자열의 길이(`.length`) 입니다. 음수값도 지원합니다. 아래 예제에서 시작 인덱스와 종료 인덱스를 조정해가며 확인해보세요.

   ```javascript
   console.log('중심을 잃고 목소리도 잃고'.slice(7));
   console.log('중심을 잃고 목소리도 잃고'.slice(7, 14));
   console.log('중심을 잃고 목소리도 잃고'.slice(-3));
   console.log('중심을 잃고 목소리도 잃고'.slice(-3, 13));
   ```

4. split()

   split은 "쪼개다" 라는 의미처럼 인자로 전달하는 구분자로 문자열을 쪼개어 각각의 값을 원소로 하는 배열을 반환합니다. 두 번째 인자로 나눌 갯수를 전달 할 수 있으며, 구분자가 빈 문자열이라면 문자열 하나하나가 모두 쪼개진 배열이 반환됩니다.

   ```javascript
   console.log('La la la la la la'.split(' '));
   console.log('La la la la la la'.split(''));
   console.log('La-la-la-la-la-la'.split('-', 3));
   ```

5. toLowerCase(), toUpperCase()

   문자열을 소문자, 혹은 대문자로 변환한 새로운 문자열을 생성하여 반환합니다.

   ```javascript
   console.log("What's the name? Black mamba".toLowerCase());
   console.log('Watch me while I make it out'.toUpperCase());
   ```

6. trim()

   문자열 앞 뒤의 공백을 제거합니다.

   ```javascript
   console.log('         abc  '.trim());
   ```

## 3.3. 템플릿 리터럴

템플릿 리터럴은 문자열을 생성합니다. 그런데 작은 따옴표나 큰 따옴표로 생성한 문자열과는 다르게 문자열 안에 변수를 삽입할 수 있도록 해주는 기능입니다. 템플릿 리터럴은 키보드 1 옆에 있는 백틱(\`)을 사용하여 문자열을 감싸고, `${}` 안에 변수를 넣어 사용합니다.

```javascript
let name = 'licat';
let age = 10;
console.log(`제 이름은 ${name}입니다! 나이는 ${age} 이에요!`);
```

템플릿 리터럴은 변수를 삽입할 수 있을 뿐만 아니라, 연산도 가능합니다.

```javascript
let num1 = 10;
let num2 = 20;
console.log(`두 수의 합은 ${num1 + num2}입니다.`);
```
