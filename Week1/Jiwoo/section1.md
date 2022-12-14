# Section 1 - Basic Syntax of TS

<br>

<pre>1. Res1, Res2에 적용되는 타입을 추론하세요.</pre>

```js
type Res1 = never | string; // 1.
type Res2 = never & string; // 2.
```

<br>

<details>
  <summary>Solution</summary>
  <strong>1. string 2. never</strong>
  <p>never 타입은 유니언 타입에서 없어지고, 교차 타입을 덮어쓴다.</p>
</details>

<br>

<pre>2. ODirection 객체를 이용하여 EDirection과 같은 Direction타입을 만들어 해당 출력값이 나오도록 하세요.</pre>

```js
const enum EDirection {
  UP,
  DOWN,
  LEFT,
  RIGHT
}

// ODirection 객체 생성
// Direction 타입 생성

function walk(dir: Direction ){
  console.log(dir); // 3
}
walk(EDirection.RIGHT);
```

<br>

<details>
  <summary>Solution</summary>

```js
const ODirection = {
    UP: 0,
    DOWN: 1,
    LEFT: 2,
    RIGHT: 3
  } as const;

type Direction = typeof ODirection[ keyof typeof ODirection];

function run(dir: Direction) {
  console.log(dir);
}
run(ODirection.RIGHT);
```

</details>

<br>

<pre>3. error가 발생한 이유를 설명하고, { name: "Mark", age: 25, gender: "F" }을 error가 발생하지 않게 user에 대입하세요.</pre>

```js
type Name = { name: string };
type Age = { age: number };

type Person = Name & Age;

const user: Person = { name: "Mark", age: 25, gender: "F" }; // error
```

<br>

<details>
  <summary>Solution</summary>
  <strong>error발생 원인은 user에 객체 리터럴을 대입하여 잉여 속성 체크가 발생한 것이다. 이때 할당가능 검사는 통과 하였지만 잉여 속성 체크는 통과하지 못했다. 그러므로 obj변수에 값 할당 후 user에 대입하면 할당 가능 검사만 체크하여 통과하게되어 error가 발생하지 않는다.(객체 리터럴을 직접 대입하지 않았기때문)</strong>
  <pre>
  const obj = { name: "Mark", age: 25, gender: "F" }
  const user: Person = obj;
  </pre>
</details>

<br>

<pre>4. 출력값을 예상하시오.</pre>

```js
function a(cb: () => void) {
  console.log(cb()); // 1. ?
}
a(() => {
  return 3;
});

interface Person {
  walk: () => void;
}
const User: Person = {
  walk() {
    return "run";
  },
};
console.log(User.walk); // 2. ?
```

<br>

<details>
  <summary>Solution</summary>
  <strong>1. 3 2. run</strong>
  <p>객체의 메서드와 콜백함수의 반환 타입이 void일 경우 반환값이 있어도 error가 발생하지 않는다. <b>이때 void는 반환값이 무엇이던 상관하지 않는다는 의미이다.</b></p>
</details>

<br>

<pre>5. privileges, startDate를 출력하기 위한 타입가드를 작성하세요. </pre>

```js
interface Admin {
  name: string;
  privileges: string[];
}
interface Employee {
  name: string;
  startDate: Date;
}

function printEmployeeInfo(emp: Admin | Employee) {
  // 타입 가드 작성
}
printEmployeeInfo({ name: "Mark", privileges: ["read"] });
printEmployeeInfo({ name: "Jun", startDate: new Date() });
```

<br>

<details>
  <summary>Solution</summary>
  <pre>
  if('privileges' in emp){
    console.log(emp.privileges);
  } else {
    console.log(emp.startDate);
  }
  </pre>
</details>

<br>

<pre>6. v4.8에서 error가 발생하는 변수를 고르세요.</pre>

```js
const a: {} = "hello";
const b: {} = undefined;
const c: Object = "hi";
const d: Object = null;
const e: Object = { x: 1 };
const f: object = "hi";
const g: object = { y: 2 };
const h: unknown = "z";
const i: unknown = null;
```

<br>

<details>
  <summary>Solution</summary>
  <strong>b, d, f</strong>
  <pre>{}, Object는 null과 undefined를 제외한 모든 타입을 할당할 수 있으며,<br>unknown는 null과 undefined를 포함한 모든 타입을 할당할 수 있다.</pre>
</details>

<br>

<pre>7. A타입을 인덱스드 시그니처를 사용하여 정의하세요.</pre>

```js
// A타입 정의
const obj: A = {
  a: 123,
  2: 2,
};
```

<br>

<details>
  <summary>Solution</summary>

```js
type A = {
  [key: string]: number,
};
```

</details>
