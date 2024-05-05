# Section02 자바스크립트 새로고침

## 리액트 프로젝트 구축 프로세스

리액트 프로젝트에서 빌드 프로세스를 사용하는 이유

1\) 처리되지 않은 리액트 코드`JSX`는 브라우저에서 실행할 수 없음

2\) 작성한 코드가 프로덕션을 위해 최적화되지 않았기 `간소화`때문

## "import" 및 "export"

```
export let 변수 및 함수의 이름 = "example";
```

```
import {변수 및 함수의 이름} from "상대 경로"
```

> react로 할 때는 상대 경로에 파일 확장자를 적지 않아도 됨 -> 뒤에서 작동하는 빌드 프로세스가 확장자를 추가하기 때문

```
export default "example"
```

```
import 이름_할당 from "상대 경로"
```

> 이름을 할당하지 않고 그냥 값을 export
>
> 이 파일에서 export한 기본 값이 됨
>
> 파일별로 하나의 값만 default export할 수 있음

```
import {변수1, 함수2} from "상대 경로"
```

```
import * as util from "상대 경로"

console.log(util.변수1)
```

## 변수 `let 키워드`

변수: 값을 저장하는 데이터 컨테이너

- 원하는 이름 할당
- 코드 내에서 이 이름을 식별자로 사용해 변수에 저장된 값을 사용해야 할 때 그 이름을 사용하면 됨

## 상수 `const 키워드`

변수와의 차이점: 상수에는 값을 다시 할당할 수 없음

> 다시 할당하지 않아야 할 값에는 const를 사용하는 것이 좋음

## 함수 `function 키워드`

```js
function createGreeting(userName, message = "Hello!") {
  console.log(userName);
  console.log(message);
}

//  createGreeting -> 함수 이름
//  userName, message 매개 변수, message는 기본값 할당
```

## 함수 `화살표 함수 문법`

```js
(userName, message) => {
  console.log("Hello");
  return userName + message;
};

//  1- 매개변수가 하나일 때는 목록 괄호 생략 가능
//  2- 반환문 에 다른 로직이 없는 경우, `return 키워드`와 중괄호를 생략할 수 있음
```

## 객체와 클래스

```js
//  키 - 값 쌍
const user = {
  name: "Max",
  greet() {
    console.log(this.name);
  },
};

console.log(user.name); // 점 표기법을 사용해서 객체의 값 엑세스
user.greet(); // 객체 안 메서드 호출
```

```js
class User {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  greet() {
    console.log("Hi!");
  }
}

const user1 = new User("Manuel, 35");
console.log(user1);
```

## 배열 및 배열 메소드

- 배열: 다른 배열이나 객체, 숫자, 문자열 등 원하는 모든 값을 저장할 수 있음
- 배열에 저장된 값을 반환하거나 읽는 사용할 수 있는 다양한 내장유틸리티 메소드가 존재

```js
//  map은 기존 배열은 변하지 않고 새 배열을 반환함
const editedHobbies = hobbies.map((item) => ({ text: item }));
console.log(editedHobbies);
```

## 디스트럭처링

1\) 점 표기법
2\) 디스트럭처링

```js
//  배열은 원소의 순서를 기준으로
const [firstName, lastName] = ["Max", "Schwarzmuller"];

//  객체는 프로퍼티 이름을 기준으로
const { name: userName, age } = {
  name: "Max",
  age: 34,
};

console.log(userName);
console.log(age);
```

```js
//  내부적으로 디스트럭처링된 객체 받는 함수
function storeOrder({ id, currency }) {
  localStorage.setItem("id", id);
  localStorage.setItem("currency", currency);
}
```

## 스프레드 연산

> 새 리스트에 쉼표로 구분해 값을 추가
>
> 전개 연산자를 사용하면 각 배열에서 값을 가져와 개별 값을 배열에 추가함

```js
//  배열
const hobbies = ["Sports", "Cooking"];
const newHobbies = ["Reading"];
const mergedHobbies = [...hobbies, ...newHobbies];

//  객체
const user = {
  name: "Max",
  age: 34,
};

const extendedUser = {
  isAdmin: true,
  ...user,
};
```

## 함수를 값으로 사용하기

> 모든 함수에서 다른 함수를 입력받을 수 있음

```js
//  ex) setTimeout
const handleTimeout2 = () => {
  console.log("Time out ... again!");
};

// 이 함수가 바로 실행되지 않도록 소괄호()를 붙이면 안 됨
// setTimeout이 내부적으로 실행함
setTimeout(handleTimeout2, 3000);
```

## 참조형과 기본 값 비교

참조형: 상수에는 주소를 저장, 주소는 변경되지 않음으로 상수를 덮어쓸 수 없다는 개념을 위반하는 것이 아님
