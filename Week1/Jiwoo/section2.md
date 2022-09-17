# Section 2 - analysis of 'lib.es5.d.ts'

<br>

<pre>1. 에러가 발생하는 곳의 번호를 고르세요.</pre>

```js
function a(x: number | string): number {
  return +x;
}
type B = (x: string) => number;
let b: B = a; // 1️⃣

function c(x: string): number {
  return +x;
}
type D = (x: number | string) => number;
let d: D = c; // 2️⃣
```

<br>

<details>
  <summary>Solution</summary>
  <strong>2️⃣</strong>
  <p>기본적으로 타입 호환은 오른쪽에 있는 타입이 더 많은 속성 및 구조적으로 더 크면 왼쪽과 호환이 된다.</p>
</details>
