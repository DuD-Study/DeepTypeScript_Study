# Section 1 - Basic Syntax of TS

<br>

<pre>1. 다음 보기에서 공통적으로 빈칸에 들어갈 단어로 알맞는 것을 쓰시오. </pre>

<pre> 보기) TS는 최종적으로 ""으로 변환된다. 브라우저, 노드는 모두 ""파일을 실행한다. </pre>

<br>

<details>
  <summary>Solution</summary>
</details>

<br>

<br>

<pre>2. 다음 보기 중 ts프로젝트를 개발할 때 가장 중요한 파일을 고르고, 그 이유를 쓰시오. </pre>

<pre> 힌트) tsc --init 명령어를 통해 생성가능한 파일이다.</pre>

<br>

보기)

1. package.json
2. project.json
3. tsconfig.json
4. build-manifest.json

<br>

<details>
  <summary>Solution</summary>
</details>

<br>

<br>

<pre>3. 다음 보기 코드를 tsc를 통해 js로 트랜스파일링 한 후에 실행시킨다면 에러가 발생할까요? 안 할까요? 그 이유는 무엇일까요? </pre>

보기)

```javascript
let jeongmin = "handsome and sexy guy";
jeongmin = 01058588282;
```

<br>

<details>
  <summary>Solution</summary>
</details>

<br>

<br>

<pre> 4. 그렇다면 3번 문제에서 다룬 성질을 고려해 보았을 때, 우리는 타입 검사에 실패한 ts 코드를 js 코드로 컴파일 또는 트랜스파일해서 사용해도 될까? 지양해야할까 무시해도될까? 답과 이유에 대해서 서술하시오. </pre>

<br>

<details>
  <summary>Solution</summary>
</details>

<br>

<br>

<pre> 5. 다음 ts 코드를 js 코드로 변환해보자. </pre>

```typescript
const add = (x, y) => x + y;
```

<br>

<details>
  <summary>Solution</summary>
</details>

<br>

<br>

<pre> 6. 5번 문제에서 javascript로 변환한 코드를 이번엔 type alias 개념을 사용해서 타입스크립트 코드로 다시 작성해보시오. </pre>

<br>

<details>
  <summary>Solution</summary>
</details>

<br>

<br>

<pre> 7. 다음 코드에서 변수 check의 타입을 지정할 때 우리에게는 두 가지 선택지가 존재한다. boolean으로 타입을 지정해주는 방법과 'true'로 값 자체를 고정시켜줄 수 있다. 실제 프로젝트에서 우리가 사용할 타입은 true만 이라고 했을 때, 어떻게 타입을 지정해주는 것이 더욱 바람직하며 그 이유는 무엇인가? </pre>

```typescript
const check: true = true;
```

<br>

<details>
  <summary>Solution</summary>
</details>

<br>

<br>

<pre> 8. 다음 코드가 문제가 있는 이유는 무엇일까? (바람직한 타입스크립트를 작성하는 방법론적 관점에서 생각해보자) </pre>

```typescript
const check: string = `5`;
```

<br>

<details>
  <summary>Solution</summary>
</details>

<br>

<br>

<pre> 9.  </pre>

<br>

<details>
  <summary>Solution</summary>
</details>

<br>

<br>

<pre> 10.  </pre>

<br>

<details>
  <summary>Solution</summary>
</details>

<br>
