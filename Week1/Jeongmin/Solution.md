<details>
  <summary>1번 Solution</summary>
  <pre>1번 같은 경우는 string과 number를 intersection은 불가능하므로 타입 추론결과 never가 나온다.<br>
2번은 매개변수가 다양한 타입으로 들어오고 '+' 연산자를 써 주었는데, 이렇게 되면 문자열로 암묵적으로 타입변환으로 일어나 반환 타입이 string으로 잡힌다.<br>
3번은 말그대로 숫자와 null이 같이 있는 배열이니 (number | null)[]</pre>
</details>

<br>

<details>
  <summary>2번 Solution</summary>
  <strong>잉여 속성 검사</strong>
  <pre>객체리터럴을 바로 값으로 대입할때는 타입스크립트에서는 잉여 속성 검사를 합니다.
하지만 객체리터럴을 변수에 담아 대입하면 그 검사를 하지 않습니다. </pre>
</details>

<br>

<details>
  <summary>3번 Solution</summary>
  <pre>private와 protected는 공통적으로 선언된 클래스 내부에서 사용할 수 있고 인스턴스에서 접근을 못하지만, 
pretected같은 경우는 부모로부터 상속받은 클래스에서 접근이 가능하다.
그리고 자바스크립트에서 private 대신에 앞에 '#' prefix를 통해 private 필드 선언이 가능하다.</pre>

```typescript
class TypeScript {
  private a: string = 'hello';
  protected b: string = "it's me";

  print() {
    console.log(this.a);
    console.log(this.b);
  }
}

class HardScript extends TypeScript {
  print() {
    console.log(this.b);
  }
}
```

</details>

<br>

<details>
  <summary>4번 Solution</summary>
  <pre>1. npx tsc hello.ts
2. npx tsc -init
3. tsc --noEmit
4. hello.ts --watch</pre>

</details>

<br>

<details>
  <summary>5번 Solution</summary>
  <strong>오버로딩(Overloading)</strong>
  <pre>한줄에 타입정의 구현을 죽었다 깨어나도 못하는 경우에 사용하면 되시겠다.</pre>

</details>

<br>

<details>
  <summary>6번 Solution</summary>
  <strong>1. A <br>2. A<br> 3. B</strong>

</details>

<br>

<details>
  <summary>7번 Solution</summary>
  
  ```typescript
    const list = { a: 'jeongmin', b: 'jiwoo', c: 'kanghoon', d: 'hayoung' } as const 
    type members = typeof list[keyof typeof list];
  ``` 
</details>

<br>

<details>
  <summary>8번 Solution</summary>
  
  ```typescript
    // 1번 정답
    const application: Required<FormType> = {
      password: 'muscleKing44',
      email: 'IlsanKing@gmail.com',
      nickname: 'handsomehoon',
      weight: 131
    }

    // 2번 정답
    function print(a: NonNullable<PrimitiveT>){
        console.log(a);
    }

    // 3번 정답
    const adminUsers: Record<Admin, User> = {
      jeongmin : { id: 1, firstname: 'jeongmin', lastname: 'lee', age: 26 },
      jiwoo : { id: 2, firstname: 'jiwoo', lastname: 'park', age: 24 },
      kanghoon : { id: 3, firstname: 'kanghoon', lastname: 'jo', age: 28 },
      hayoung : { id: 4, firstname: 'hayoung', lastname: 'park', age: 24 },
    };

````

</details>

<br>



<details>
  <summary>9번 Solution</summary>

```typescript
// 1번 정답
function doThis(arg) {
  if (arg instanceof 코딩하기) arg.coding();
  else arg.eating();
}

//2번 정답
function isPTHogang(arg: any): arg is Hogang {
  return arg.ptMember !== undefined;
}
````

</details>

<br>

<details>
  <summary>10번 Solution</summary>

<pre>1. any는 타입 검사를 느슨하게하기 때문에 그냥 넘어가지만,
    unknown같은 경우 컴파일러가 타입을 짚고 넘어가야한다고 에러가 납니다.

2. any는 어떤 타입에다가도 할당이 가능하지만,
   unknown은 어떤 Type Assertion (e.g <> or as)나 혹은 Type Narrowing(e.g 타입 가드)을 통한
   타입이 확정 되어야 할당이 가능합니다.</pre>

```typescript
let vAny: any = 10; // any 타입에는 어떤 것이든 할당 가능합니다.
let vUnknown: unknown = 10; // unknown 타입에는 어떤 것이든 할당 가능합니다.

let s1: string = vAny; // Any타입은 다른 어떤 타입에서도 할당 가능.
let s2: string = vUnknown; // 명확한 Type Assertion없이는 불가능.

vAny.method(); // any는 가능
vUnknown.method(); // 이 변수 타입에 대해 아는 것이 없기 때문에 실행 안됨.
```

</details>
