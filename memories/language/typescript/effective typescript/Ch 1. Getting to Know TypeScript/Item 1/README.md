# Item 1: Understand the Relationship Between TypeScript and JavaScript

## Summary

- 타입스크립트는 자바스크립트의 상위집합이다. 다시 말해서, 모든 자바스크립트 프로그램은 이미 타입스크립트 프로그램입니다. 반대로, 타입스크립트는 별도의 문법을 가지고 있기 때문에 일반적으로는 유효한 자바스크립트 프로그램이 아닙니다.

```ts
function greet(who: string) {
  console.log("Hello", who);
}
```

> 위 코드는 `: string` 이라는 문법을 포함하고 있기 떄문에 자바스크립트 파일이 아닙니다.

- 타입스크립트는 자바스크립트 런타임 동작을 모델링하는 타입 시스템을 가지고 있기 때문에 런타임 오류를 발생시키는 코드를 찾아내려고 합니다. 그러나 모든 오류를 찾아내리라 기대하면 안 됩니다. 타입 체커를 통과하면서도 런타임 오류를 발생시키는 코드는 충분히 존재할 수 있습니다.

```ts
const names = ["Alice", "Bob"];
console.log(names[2].toUpperCase());
```

> 위 코드에서는 앞의 배열이 범위 내에서 사용될 것이라 가정했지만 실제로는 그렇지 않았고, 오류가 발생했습니다.

- 타입스크립트 타입 시스템은 전반적으로 자바스크립트 동작을 모델링합니다. 그러나 잘못된 매개변수 개수로 함수를 호출하는 경우처럼, 자바스크립트에서는 허용되지만 타입스크립트에서는 문제가 되는 경우도 있습니다. 이러한 문법의 엄격함은 온전히 취향의 차이이며 우열을 가릴 수 없는 문제입니다.

```ts
const a = null + 7; // 자바스크립트에서는 a 값이 7이 됩니다.

const b = [] + 12; // 자바스크립트에서는 b 값이 '12'가 됩니다.

alert("Hello", "TypeScript"); // 자바스크립트에서는 "Hello" 경고를 표시합니다.
```

> 위 세 구문은 타입스크립트에서는 동작하지 않습니다.
