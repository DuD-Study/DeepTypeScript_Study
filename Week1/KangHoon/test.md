1. 다음 코드의 type은 무엇으로 추론되는가?
```ts
let Type = "Type";
```

2. 타입을 강제로 변환하는 방법에는 무엇이 있는가?

아래와 같은 객체가 있다.
```ts
const obj = {a: 'jiwoo', b: 'hayoung', c:'jeongmin'} as const;
```

3. 위 객체의 타입은 어떻게 추론되는가?
4. 위 객체의 key 값을 type으로 갖는 type을 생성하는 방법은 무엇이 있는가?
5. 위 객체의 key 값의 type을 type으로 갖는 type을 생성하는 방법은 무엇이 있는가?


6. 아래 코드에 문제점은 무엇인가?
```ts
interface A {
    name: string;
    location: string;
}

interface B {
	name: string;
	age: number;
}

const type = (info: A | B) : void => {
	info.age = "28";
}
```

7. 아래 코드의 문제점은 무엇인가?
```ts
const logger = (a?: number, b: number) => {
	console.log(a,b)
}

logger(1,2);
```

8. 아래 코드의 문제점은 무엇인가?
```ts
const A = (a:number): number | string => {
	if (Math.random() > 0.5) return a.toString();
	else return a;
}

type B = (a: number | string) => number;

let b:B = a;
```


9.
```ts
type User = {
name: string;
age: number;
};

const user: User = {
name: "조강훈",
age: 28
};

function me = <T>(user: T): T {
return user;
};
```

10. 오버로딩
11. Exclude/Extract 와 Pick/Omit의 차이

12. INFER

