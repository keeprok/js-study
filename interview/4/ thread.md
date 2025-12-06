### 17. 동기 VS 비동기 – 예시를 통한 코드 실행 흐름 이해

1.  동기(Synchronous)

코드가 작성된 순서대로 차례대로 실행

하나의 작업이 오래 걸리면 다음 작업은 대기 → 블로킹 발생

2. 비동기(Asynchronous)

오래 걸리는 작업을 Web API/Node API로 위임

작업 완료 후 콜백/Promise 를 통해 결과 전달
→ 메인 스레드는 블로킹되지 않음

예제)

```js
console.log(1);
setTimeout(() => console.log(2), 0);
console.log(3);
```

## 18. 싱글 스레드 – 한 번에 하나의 작업만 처리하는 구조

1. 핵심 개념

JS 엔진은 싱글 스레드 + 하나의 Call Stack

한 순간에 하나의 함수만 실행 가능

동기 작업이 오래 걸리면 UI 멈춤 → 비동기로 회피

2. 구성 요소

Call Stack

Heap

(브라우저 환경일 경우) Web API
