#타입스크립트에서 타입을 뺐을때 정상 동작하는 js코드여야한다!

## 타입 추론
const a: string = "abc" 과 같은 타입 선언은 문제의 여지가 있다.
<br> "abc"라는 정확한 타입을 주었다가 string으로 변경되기 때문이다.<br> 굳이 해줄 필요가 없다.
타입스크립트가 추론을 잘못했을때만 고쳐주면 된다.<br>
매개변수에는 반드시 타입을 붙여주는 것이 좋다. return 값은 매개변수의 타입값을 기반으로 타입 추론을 하기 떄문.<br>
추론을 잘해주면 추론에 맡기자.

## 

1. const A: number = 3

2. 다음 중 타입 선언이 잘못 된 경우는?
3. 1.type Greeting = `hello ${world}`
4. 2.function rest(...arg: string[])
   3.const tuple: [string, number]
5. 4.잘못된 것 넣기

