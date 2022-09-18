# Section 1 - Basic Syntax of TS

<br>

<pre>1. 다음 코드에서 타입 추론이 어떻게 나올까요? </pre>

```typescript
type c = string & number;

function func(a: string, b: number, c: boolean) {
  return a + b + c;
}

let something = [0, 1, null];

// 1번 type c의 타입
// 2번 func의 반환값
// 3번 something 타입 추론 값
```

<br>
<br>
<br>

<pre>2. 밑에 코드에서 me라는 변수에 MyInfo타입을 선언해주고, 객체 리터럴로 값을
   할당해주면 아래와 같은 에러가 발생하고, 해당 객체값을 nameCard라는 변수로 빼주고,
   newMe에 MyInfo타입을 선언해주고 nameCard를 할당하면 에러가 나지 않는다.
   이것을 무슨 검사라고 하는가 ~ ?</pre>

```typescript
interface MyInfo {
  firstName: string;
}

//Type '{ firstName: 'Jeongmin', lastName: 'Lee' }' is not assignable to type 'MyInfo'.
const me: MyInfo = { firstName: 'Jeongmin', lastName: 'Lee' };

const nameCard = { firstName: 'Jeongmin', lastName: 'Lee' };
const newMe: MyInfo = nameCard;
```

<br>
<br>
<br>

<pre>3. TS의 class에서 private와 protected의 공통점, 차이점을 서술하고, 
   자바스크립트에서 private 대신해서 사용해줄 수 있는 것은 prefix는 ? </pre>

```typescript
class TypeScript {
  private a: string = 'hello';
  protected b: string = "it's me";

  print() {
    console.log(this.a);
    console.log(this.b);
  }
}

class CrazyScript extends TypeScript {
  print() {
    console.log(this.a);
    console.log(this.b);
  }
}
```

<br>
<br>
<br>

<pre>4. 다음 해당하는 커맨드를 입력해보세요. </pre>

<br>

1. hello.ts라는 파일만 컴파일하고 싶을때 -> <code>??? ????????</code><br>
2. tsconfig.json 생성 -> <code>??? ????</code> <br>
3. 타입 검사만 하고 싶다면 -> <code>??? ????????</code> <br>
4. hello.ts라는 파일 실시간을 컴파일하고 싶을때 -> <code>?????? ????????</code>

<br>
<br>
<br>

<pre>5. lib.es5.d.ts를 보면 아래와 같이 매개변수에 변화를 주거나 타입에 변화를 주어 다른 버전의 같은 함수를 정의해 놓는 것을 뭐라고 하나요? </pre>

```typescript
    reduce(callbackfn: (previousValue: T, currentValue: T, currentIndex: number, array: readonly T[]) => T): T;
    reduce(callbackfn: (previousValue: T, currentValue: T, currentIndex: number, array: readonly T[]) => T, initialValue: T): T;
```

<br>
<br>
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
<br>
<br>

<pre>7. 아래 주석처럼 list 객체 키의 value들로 타입들로 만들어보세요.</pre>

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
<br>
<br>

<pre>8. 어떤 유틸리티 타입을 써야하는지 적어보시오.</pre>

```typescript
  // 1. application에 weight도 반드시 쓰게하도록 속성 변경할 수 있는
  //    유틸리티 타입을 써서 수정해주세요.
    interface FormType{
      email: string,
      password: string
      nickname: string
      weight?: number
    }

    // 여기만 수정
    const application: FormType = {
      password: 'muscleKing44'
      email: 'IlsanKing@gmail.com'
      nickname: 'handsomehoon'
    }

    // 2. null과 undefined만 에러가 나게끔 아래 함수를 타이핑해주세요.

    ype PrimitiveT = string | number  | null | undefined

    // 여기만 수정하면됨
    function print(a){
        console.log(a);
    }

    print('2')
    print(2)
    print(null)  // Argument of type 'null' is not assignable to parameter of type
    print(undefined) // Argument of type 'undefined' is not assignable to parameter of type


    // 3. adminUsers에 jeongmin만 허용되게끔 타이핑을 하고싶다.
    //    Admin, User 타입을 사용해서 타이핑을 해보자 ~
    interface User {
      id: number;
      firstname: string;
      lastname: string;
      age?: number;
    }

    type Admin = 'jeongmin'

    const adminUsers: ???? = {
      jeongmin : { id: 1, firstname: 'jeongmin', lastname: 'lee', age: 26 },
      jiwoo : { id: 2, firstname: 'jiwoo', lastname: 'park', age: 24 },
      kanghoon : { id: 3, firstname: 'kanghoon', lastname: 'jo', age: 28 },
      hayoung : { id: 4, firstname: 'hayoung', lastname: 'park', age: 24 },
    };
```

<br>
<br>
<br>

<pre>9. 타입가드를 넣어주세요. </pre>

```typescript
// 1번 타입가드 해보즈아..
class 코딩하기 {
  coding() {
    console.log('죽을맛이노');
  }
}
class 폭식하기 {
  eating() {
    console.log('이맛에사노');
  }
}
function doThis(arg) {
  // 타입가드해서 둘다 하나씩 나와야겠죠?
}
doThis(new 코딩하기());
doThis(new 폭식하기());

// 2번 커스텀 타입 가드 함수를 만들어보자 ~

interface Hogang {
  ptMember: boolean;
  normalMember: boolean;
  name: string;
}

interface Gang {
  normalMember: boolean;
  name: string;
}

function isPTHogang() {}

function doCheck(arg: Hogang | Gang) {
  if (isPTHogang(arg)) console.log(`안녕하세요 ${arg.name}님!!!`);
  else console.log('..안녕하세요');
}

const min: Hogang = { ptMember: true, normalMember: true, name: '정민' };
const hoon: Gang = { normalMember: true, name: '강훈' };

doCheck(min); // 안녕하세요 정민님!!!
doCheck(hoon); // ..안녕하세요
```

<br>
<br>
<br>

<pre>10. any와 unknown의 차이점을 적어봅시다.

1. 타입 검사시의 차이점 :

2. 다른 typed 변수에 할당 시의 차이점 :</pre>

<br>
