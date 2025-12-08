### 20. 콜백 함수와 콜백 지옥

#### 콜백 함수 정의

- 비동기 작업 완료 시 실행되도록 다른 함수의 인자로 전달되는 함수.

- 대표 사용처:

  - setTimeout, setInterval

  - ddEventListener

  - XMLHttpRequest (옛날 Ajax 방식)

  - Node.js의 초기 API

#### 장점

- 구현이 단순하다.

- 브라우저/Node.js 런타임이 기본적으로 지원한다.

#### 콜백 지옥 문제점

- 들여쓰기 증가 → 가독성 떨어짐.

- 흐름 파악 어려움.

- 에러 처리 어려움 (try/catch 불가능).

- 유지보수 어려움.

### 21. Promise

#### Promise란?

- 비동기 작업의 성공/실패와 결과를 저장하는 객체.

#### 3가지 상태

- pending

- fulfilled (resolve)

- rejected (reject)

#### 장점

- then 체이닝을 통한 흐름 구조화.

- catch 하나로 에러 통합 처리.

- 병렬 처리 가능 (Promise.all).

- async/await의 기반.

#### 기본 예시

- new Promise로 생성

- then, catch로 후속 처리 연결

### 22. then / catch / finally

#### then

- Promise가 성공(resolve) 되었을 때 실행.

#### catch

- 실패(reject) 또는 then 내부 에러 잡기.

#### finally

- 성공/실패 관계없이 항상 실행.

- 로딩 스피너 제거, cleanup 용도로 많이 사용.

### 23. 마이크로태스크 큐

#### 개념

- 이벤트 루프는 Microtask Queue를 Task Queue보다 먼저 실행한다.

- Microtask: Promise.then, MutationObserver, queueMicrotask

- Task: setTimeout, setInterval, DOM 이벤트

#### 실행 순서 결과

- Promise.then은 setTimeout보다 먼저 실행됨.

#### 실무에서 중요성

- React state 업데이트 타이밍

- Node.js nextTick vs setImmediate 차이

- 비동기 타이밍 관련 이슈 해결

### 24. async / await

#### 개념

- Promise 기반 비동기 코드를 동기처럼 보이도록 만드는 문법.

- async 함수는 항상 Promise를 반환.

- await는 Promise가 완료될 때까지 기다림.

#### 장점

- then 체이닝보다 가독성이 좋다.

- try/catch로 동기식 에러 처리.

#### 구조

- async 함수 내부에서 await로 단계적 처리.

### 25. async/await 에러 처리

#### try/catch

- await에서 발생한 에러를 동기 코드처럼 catch 가능.

#### finally

- 항상 실행되는 cleanup 블록.

#### 병렬 처리 최적화

- await를 여러 번 쓰면 직렬 처리됨.

- Promise.all로 병렬 처리 가능.
