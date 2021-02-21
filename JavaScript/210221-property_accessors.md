# 20210221

*from [https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Operators/Property_Accessors](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Operators/Property_Accessors)*

## 속성 접근자(Property accessors)

- 객체의 속성에 접근할 수 있도록 해줌.

### 점 표기법

```jsx
object.property
```

- property는 변수로 사용할 수 있는 식별자여야 함. (object.1 사용 불가)

### 괄호 표기법

```jsx
object[property_name]
```

- 점 표기법과 달리 유효한 식별자가 아니어도 된다.
- 다만, 속성 이름을 직접 쓰는 경우, 따옴표를 써야 한다.

### 속성 이름

```jsx
let foo = {unique_prop: 1}, bar = {unique_prop: 2}, object = {};
object[foo] = 'value';
console.log(object[bar]);
```

- 속성의 이름은 항상 문자열이나 Symbol이다.
- 그 밖의 자료형의 경우에는 문자열로 변환된다.
- 위의 예시에서 foo와 bar이 문자열 "['object Object']"로 변환되어 같은 속성 이름으로 취급된다.

→ 직접 속성이름에 접근하는 경우에는 주로 점 표기법, 변수를 이용한 속성 이름 접근에는 주로 괄호 표기법이 사용된다.