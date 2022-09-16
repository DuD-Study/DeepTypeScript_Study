1. 다음 객체에서 key의 type을 추출 할 수 있는 코드는 무엇인가?
```js
const obj = {a: 'jiwoo', b: 'hayoung', c:'jeongmin'} as const;
```

type C = keyof typeof obj; 

2. 위 문제에서 value값만 가지고 오는 방법은?
type Key = typeof obj[keyof typeof obj];
3. 위 문제에서 as const 의 이유는?

4.타입가드 (is문법)

5.인터페이스 유니온

6. 매개변수에 옵셔널 타입이 필수 타입 앞에 위치했을떄 문제점

7. 공변성, 매개변수를 더 좁게해서 해보기

8. 제네릭

9. 오버로딩

