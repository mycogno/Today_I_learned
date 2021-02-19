# Destructuring assignment

_from [https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment)_

## 비구조화 할당(Destructuring assignment)

- 배열이나 객체의 요소를 분해하여 각 값을 개별 변수에 담을 수 있도록 하는 방법

### 배열

```jsx
const a = [1, 2, 3, 4, 5];
const [x, y] = a; // x, y에는 각각 1, 2가 할당되며 개별 변수로 쓸 수 있다.
```

```jsx
const a, b;
[a, b] = [1]; // a에는 1이 할당되지만 b는 할당될 요소가 없어 undefined가 된다.

const a, b;
[a=5, b=7] = [1]; // 이렇게 하면 undefined일 때 사용할 기본값을 대신 사용한다.
// 따라서 a에는 1, b에는 7이 저장된다.
```

```jsx
let a = 1;
let b = 3;
[a, b] = [b, a]; // 이런 식으로 a, b 값을 서로 바꿀 수 있다.
```

```jsx
const arr = [1, 2, 3, 4, 5];
const [a, , b] = arr; // 필요하지 않은 값을 무시할 수 있다.
// a는 1, b는 3이 저장된다.
```

```jsx
const [a, ...b] = [1, 2, 3]; // ...b는 분해한 나머지 부분을 하나의 배열로 변수 b에 저장한다.
console.log(a); // 1
console.log(b); // [2, 3]
```

---

### 객체

```jsx
const o = { p: 42, q: true };
const { p, q } = o;
// 객체 o의 속성인 p, q를 개별변수 p, q로 사용할 수 있다.
console.log(p); // 42
console.log(q); // true
```

```jsx
const { a = 10, b = 5 } = { a: 3 };
// 배열의 경우와 마찬가지로 기본값을 할당할 수 있다.
console.log(a); // 3
console.log(b); // 5
```

```jsx
const { a: aa = 10, b: bb = 5 } = { a: 3 };
// 기본값을 지정하면서 새로운 이름의 변수에 할당할 수 있다.
console.log(aa); // 3
console.log(bb); // 5
```

```jsx
const people = [
  {
    name: "Mike Smith",
    family: {
      mother: "Jane Smith",
      father: "Harry Smith",
      sister: "Samantha Smith",
    },
    age: 35,
  },
  {
    name: "Tom Jones",
    family: {
      mother: "Norah Jones",
      father: "Richard Jones",
      brother: "Howard Jones",
    },
    age: 25,
  },
];

for (const {
  name,
  family: { father },
} of people) {
  console.log("Name: " + name + ", Father: " + father);
}
// 중첩된 객체에서의 구조분해
// "Name: Mike Smith, Father: Harry Smith"
// "Name: Tom Jones, Father: Richard Jones"
```

```jsx
for (const {
  name: n,
  family: { father: f },
} of people) {
  console.log("Name: " + n + ", Father: " + f);
}
// 다른 변수명을 지정하려면 이렇게!
```

```jsx
// 함수의 매개 변수로 전달할 때
function userId({ id }) {
  // {id} = user
  return id;
}

// {displayName: displayName, fullName: {firstName: name}} = user
function whois({ displayName: displayName, fullName: { firstName: name } }) {
  console.log(displayName + " is " + name);
}

const user = {
  id: 42,
  displayName: "jdoe",
  fullName: {
    firstName: "John",
    lastName: "Doe",
  },
};

console.log("userId: " + userId(user)); // "userId: 42"
whois(user); // "jdoe is John"
```

```jsx
let key = 100 + 23;
let { [key]: foo } = { 123: "bar" };

console.log(foo); // "bar"

// 변수 명을 속성이름으로 사용할 수 있다.
// computed property name
```

```jsx
let { a, c, ...rest } = { a: 10, b: 20, c: 30, d: 40 };
console.log(rest); // { b: 20, d: 40 }

// 함수와 마찬가지로 ...으로 남은 부분을 하나의 변수에 보을 수 있음
// rest말고 다른 변수 써도 무관
```

```jsx
const foo = { "fizz-buzz": true };
const { "fizz-buzz": fizzBuzz } = foo;
// 변수명으로 사용할 수 없는 경우에는 무조건 변수 사용가능한 다른 식별자명으로 대체해야 함
console.log(fizzBuzz); // "true"
```
