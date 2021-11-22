# Javascript

자바스크립트 기초

## 식별자

- 숫자로 시작할 수 없고 공백을 포함할 수 없다.
- 길이 제한은 없음
- `$`로 시작 가능
- 코드는 데이터로 변환할 수 없지만, 데이터는 식별자로 변환 가능 

```javascript
let age = 18;
function setAge(){}
const person ={
    age: 12,
    // 데이터를 식별자로 변환 가능(숫자시작, 공백 포함 가능)
    ['name']: "남"
}
person.name;
person.['name']; //공백이나 숫자로 시작할 때는 이렇게 접근 가능
```

> 네이밍 관습

상수는 대문자, 단어와 단어 사이는 카멜 케이스

<br>

## 값(value)

```
- 기본자료형
  Boolean
  Null
  Undefined
  Number
  String
  Symbol

- 위의 기본자료형 외의 모든 것은 Object
```

<br>

## 타입

자바스크립트, 변수에 할당될때 타입이 정해짐. 느슨한 타입이므로 문제 상황발생시 런타임에서 예외상황을 처리해줘야 함.

타입스크립트, 개발하는 상황에서 처리할 수 있음

<br>

## 변수와 상수

```javascript
let x = 10;
const y = 200;

const obj ={
    height: 200,
    width:300,
}
// 속성에 대해서는 변경가능
obj.heigt = 300

// object를 다른 값으로 변경할 때 오류가 남.
obj = 100;
```

변수는 데이터 변경 가능, 상수는 데이터 변경 불가

<br>

## 식

식(값)과 문(~문)

식은 반드시 세미콜론으로 구분되어 있음, 하나의 값으로 수렴한다.

문은 세미콜론 없음.

### 구조분해 할당

```javascript
const colors = ['red','yellow','black']
const Colors = {blue:'blue', green:'green', sky:'sky'}

const [red, yellow, black] = colors // 배열
const [, yellow] = colors // 배열
const { sky, green } = Colors //객체
```

할당 연산자 :  =, +=, -=, /= 등

비교연산자 : ==, !=, === 등

논리 연산자 : &&, ||, !

문자열 연산자 : "my" + "string" - 현재는 템플릿 리터럴을 많이 사용

삼항 연산자: a === b? 0  : 1

typeof : 타입 확인

<br>

연산자 우선순위 : 괄호를 감싸서 더 명확하게 우선순위를 지정해주는 게 좋음

```javascript
값이 될 수 있는 것을 값이 아닌 상황에서 괄호를 감싸면 값으로 지정 가능
(function foo(){
    
})
```

<br>

## 참조와 복사

**기본 데이터 타입은 복사가 되고, 객체는 참조가 됨.**

객체는 한곳에 저장되어있고 위치값만 변수에 기록됨.

```javascript
let a = 10;
let b = 1;
b = 20 // a= 10 b= 20

let o = {
    isLoading: false
}
let o2 = o;
o2.isLoading = true; // o:{isLoading: true} o2:{isLoading: true}

function foo(o){
    o.isLoading = false;
}
foo(o); // o:{isLoading: true} 
// 인자로 넘겨도 객체의 경우는 참조 메커니즘이 작동한다.
```



## 조건문

**if 와 switch**

{} 모든 객체는 빈객체도 참으로 판정

switch는 일치하면 다음케이스도 다 실행되므로, break로 코드의 중단점을 표시해줘야 한다.

대상이 매번 동일하고, 일치하는 지 비교할 때는 switch가 좋음.

어떤 걸 사용할지는 개발자의 선택사항



## 반복문

```javascript
const array = ['a', 'b', 'c'];

// 기본 for문
for (i=0; i<arr.length; i++){
    console.log(arr[i])
}

```



