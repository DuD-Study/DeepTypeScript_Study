# Section 1 - Basic Syntax of TS

<br>


<pre>1. 다음 각 변수들에 커서를 올리면 타입 추론이 어떻게 나올까요? </pre>

```typescript
  type c = string & number;   // 1.

  function func (a: string, b: number, c:boolean) { 
    return a+b+c;
  } // 2.

  let something = [0, 1, null]; // 3.
```

<br>

<details>
  <summary>Solution</summary>
  <pre>1번 같은 경우는 string과 number를 intersection은 불가능하므로 타입 추론결과 never가 나온다.<br>
2번은 매개변수가 다양한 타입으로 들어오고 '+' 연산자를 써 주었는데, 이렇게 되면 문자열로 암묵적으로 타입변환으로 일어나 반환 타입이 string으로 잡힌다.<br>
3번은 말그대로 숫자와 null이 같이 있는 배열이니 number | null[]</pre>
</details>

<br>

<pre>2. 밑에 코드에서 a라는 변수에 A타입을 선언해주고, 객체 리터럴로 값을<br>   할당해주면 아래와 같은 에러가 발생하고, 해당 객체값을 b라는 변수로 빼주고,<br>   c라는 변수에 A타입을 선언해주고 b변수를 할당하면 에러가 나지 않는다.<br>   이런 특성을 뭐라고하는가 ?</pre>

```typescript
type A = { firstName: string };

//Type '{ firstName: 'Jeongmin', lastName: 'Lee' }' is not assignable to type 'A'.
const a: A = { firstName: 'Jeongmin', lastName: 'Lee' };


const b = { firstName: 'Jeongmin', lastName: 'Lee' };
const c: A = b;
```

<br>

<details>
  <summary>Solution</summary>
  <strong>잉여 속성 검사</strong>
</details>

<br>

<pre>3. TS의 class에서 private와 protected의 차이점을 서술하고, 
   private 필드 대신해서 사용해줄 수 있는 것은 prefix는 ? </pre>

```typescript
class TypeScript implements Javascript {
  private a: string;
  protected b: string;
}
```

<br>

<details>
  <summary>Solution</summary>
  <pre>private와 protected는 공통적으로 클래스 내부에서 사용할 수 있고 인스턴스에서 사용을 못하지만, 
pretected 클래스를 부모로써 상속받은 클래스만은 접근이 가능하다.
그리고 private 대신에 앞에 '#' prefix를 통해 private 필드 선언이 가능하다.</pre>

```typescript
  class TypeScript implements Javascript {
  #a: string;
  protected b: string;
}
```
</details>

<br>


<pre>4. 다음 해당하는 커맨드를 입력해보세요. </pre>

<br>

1. hello.ts라는 파일만 컴파일하고 싶을때 -> <code>??? ????????</code><br>
2. tsconfig.json 생성 -> <code>??? ????</code> <br>
3. 타입 검사만 하고 싶다면 -> <code>??? ????????</code> <br>
4. hello.ts라는 파일 실시간을 컴파일하고 싶을때 -> <code>?????? ????????</code>


<br>

<details>
  <summary>Solution</summary>
  <pre>1. npx tsc hello.ts
2. npx tsc -init
3. tsc --noEmi
4. hello.ts --watch</pre>

</details>

<br>


<pre>5. lib.es5.d.ts를 보면 아래와 같이 매개변수에 변화를 주거나 타입에 변화를 주어 다른 버전의 같은 함수를 정의해 놓는 것을 뭐라고 하나요? </pre>

```typescript
    reduce(callbackfn: (previousValue: T, currentValue: T, currentIndex: number, array: readonly T[]) => T): T;
    reduce(callbackfn: (previousValue: T, currentValue: T, currentIndex: number, array: readonly T[]) => T, initialValue: T): T;
```

<br>

<details>
  <summary>Solution</summary>
  <strong>오버로딩(Overloading)</strong>
  <pre>한줄에 타입정의 구현을 죽었다 깨어나도 못하는 경우에 사용하면 되시겠다.</pre>

</details>

<br>

<pre>6. 객관식 맞쳐보세용 </pre>

1. TypeScript에서 Arrow 함수 옳게 쓰인것은 무엇인가요? 
```typescript
   A. let sum = (x: number, y: number) => x + y;
   B. let sum() = (x: number, y: number):number => x + y;
   C. let sum = (x: number, y: number) => return x + y;
   D. let sum:(x: number, y: number) => x + y;
```

<br>

2. TypeScript에서 Tuple 옳게 쓴것은 무엇일까요?
```typescript
  A. var employee:[number, string] = [1, "Bill"];
  B. var employee:[number | string] = [1, "Bill"];
  C. var employee = [1, "Bill"];
```

<br>

3. TypeScript에서 Union Type 옳게 쓴것은 무엇일까요?
```typescript
  A. var slave:[number, string] = [1, "Jeongmin"];
  B. var slave:[number | string] = 456;
  C. var slave:string[] = ["Bill"];
```

<br>

<details>
  <summary>Solution</summary>
  <strong>1. A <br>2. A<br> 3. B</strong>

</details>

<br>

<pre>7. 아래 코드처럼 list 객체 키의 value들로 타입들로 만들어보세요.</pre>

```typescript
    // type members = 'jeongmin' | 'jiwoo' | 'kanghoon' | 'hayoung'
    
    const list = { a: 'jeongmin', b: 'jiwoo', c: 'kanghoon', d: 'hayoung' } as const 
    type members = // type your code ;
```
<div align="center">
  <details>
    <summary>Hint</summary>
    <pre>keyof 와 typeof 사용해보세요.</pre>
  </details>
</div>

<br>

<details>
  <summary>Solution</summary>
  
  ```typescript
    const list = { a: 'jeongmin', b: 'jiwoo', c: 'kanghoon', d: 'hayoung' } as const 
    type members = typeof list[keyof typeof list];
  ``` 
</details>

<br>