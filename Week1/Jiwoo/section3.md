# Section 3 - Utility Types

<br>

<pre>1. Pick을 사용자 정의 P 타입으로 구현하세요.</pre>

```js
interface Profile {
  name: string;
  age: number;
  married: boolean;
}

// type P 정의

const user: P<Profile, "name" | "age"> = {
  name: "jiwoo",
  age: 24,
};
```

<br>

<details>
  <summary>Solution</summary>

```js
type P<T,S extends keyof T> = {
  [key in S ]: T[key];
}
const user:P<Profile,'name'|'age'> = {
  name: "jiwoo",
  age: 24
}
```

</details>

<br>

<pre>2. 타입에 해당하는 값을 할당하세요.</pre>

```js
interface Profile {
  name: string;
  age: number;
  married: boolean;
}

type A = Extract<keyof Profile, 'married'>;
type B = Exclude<keyof Profile, 'age'>;
type C = Pick<Profile,'married'>;
type D = Omit<Profile,'married'>;

const a:A = // 1.
const b:B = // 2.
const c:C = // 3.
const d:D = // 4.
```

<br>

<details>
  <summary>Solution</summary>

```js
type A = 'married';
type B = 'name' | 'married'
type C = { married: boolean; }
type D = { name: string; age: number; }

const a:A = 'married';
const b:B = 'name'; or // 'married'
const c:C = { married: false }
const d:D = { name: 'zooyaho'; age: 24; }
```

</details>

<br>

<pre>3. 코드를 보고 타입 R을 정의하세요.(name, age, married는 필수 속성입니다)</pre>

```js
interface Profile {
  readonly name?: string;
  readonly age?: number;
  readonly married?: boolean;
}

type R<T> = {
  // 작성
}

const user: R<Profile> = {
  name: "jiwoo",
  age: 24,
  married: false,
};
user.age = 25;
```

<br>

<details>
  <summary>Solution</summary>

```js
type R<T> = {
  -readonly [key in keyof T]-? : T[key];
}
```

</details>
