### 36. 자바스크립트 실행 과정과 스크립트 로딩 전략

#### JS 실행 흐름

- HTML 파싱 중 <script> 를 만나면 실행이 중단됨

- 이를 해결하기 위한 속성:

- defer: HTML 파싱 끝난 후 실행 (순서 보장)

- async: 다운로드 완료 시 즉시 실행 (순서 보장 안 됨)

#### 실무 전략

- 대부분의 일반 스크립트는 defer 사용

- 외부 스크립트 광고/SDK 등은 async가 유리

### 37. DOM 조작 — 노드 선택·추가·수정·삭제

#### 핵심 변경 방식

- 선택: querySelector

- 추가: append, prepend, insertAdjacentHTML

- 수정: textContent, classList

- 삭제: remove()

#### 특징

- DOM 조작은 비용이 크므로 최소화

- 가급적 Virtual DOM 또는 프레임워크 사용 권장

### 38. 이벤트 처리와 전파 — addEventListener, 캡처링, 버블링

#### 이벤트 흐름 단계

1. 캡처링 (window → target)

2. 타깃 도달

3. 버블링 (target → window)

#### 캡처링 사용

- addEventListener(event, handler, true)

#### 이벤트 위임

- 부모에 이벤트를 걸어 하위 요소의 이벤트를 한 번에 처리

- 성능과 유지보수에 매우 유리

### 39. 이벤트 기본 동작 제어 — preventDefault, stopPropagation

#### preventDefault()

- 링크 이동, 폼 제출 등의 브라우저 기본 동작을 막음

#### stopPropagation()

- 이벤트 전파(캡처링/버블링) 중단

#### 실무 활용 예

- form 제출 시 새로고침 방지

- 모달 내부 클릭은 유지, 배경 클릭만 닫기 등 제어 가능
