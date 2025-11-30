## 15. 클로저 – 외부 변수를 기억하고 유지하는 함수의 작동 원리

1. 핵심 개념

클로저는 함수가 선언될 당시의 외부 변수(상위 스코프)를 기억하고,
함수가 그 스코프 밖에서 실행되더라도 해당 변수에 접근할 수 있게 해주는 기능이다.

2. 구조

함수가 생성될 때 Lexical Environment 를 함께 패키징해 보관

inner 함수는 outer 함수의 환경 레코드를 참조할 수 있음

예시)

```js
function outer() {
  let count = 0;
  return function inner() {
    count++;
    return count;
  };
}

const counter = outer();
counter(); // 1
counter(); // 2
```

## 16. 클로저 활용과 한계 – 은닉화·콜백에서의 장점과 메모리 누수·디버깅 이슈

1. 장점

변수 은닉(private) 구현 가능
→ JS에 클래스 private 없던 시절 완전 필수 기능

상태 유지

콜백 / 이벤트 리스너에서 외부 값을 안정적으로 참조

2.  단점

렉시컬 환경을 유지하므로 메모리 점유 증가

해제되지 않으면 메모리 누수(memory leak)

디버깅 난이도 증가 (스코프 체인 추적 어려움)
