# 📌 Zustand

> **실습 저장소**: [ghooman/react-zustand-basic](https://github.com/ghooman/react-zustand-basic)

---

## 1. Zustand 기본 사용 방식 (Standard Pattern)

Zustand는 `create` 함수를 통해 상태(State)와 액션(Action)이 포함된 스토어를 생성합니다.

### ✅ 기본 예시 코드

```javascript
import { create } from 'zustand';

// 1. 스토어 생성
const useStore = create((set) => ({
  count: 0,
  increment: () => set((state) => ({ count: state.count + 1 })),
  reset: () => set({ count: 0 })
}));

// 2. 컴포넌트에서 사용
function Counter() {
  const { count, increment } = useStore();
  return <button onClick={increment}>{count}</button>;
}
```

---

## 2. 프로젝트 실습 분석

### ✅ [Counter Store (useCounterStore.js)](https://github.com/ghooman/react-zustand-basic/blob/main/src/store/useCounterStore.js)

- **미들웨어**: `devtools`와 `persist`를 변수에 순차 재할당하여 적용
- **상태 업데이트 패턴**:
  - `set((state) => ({ count: state.count + 1 }))` (이전 state 기반)
  - `set({ count: number })` (직접 값 설정)
- **초기화**:
  - 상태 리셋: 스토어 내부 `reset: () => set({ count: 1 })`
  - 저장소 삭제: 컴포넌트에서 `useCounterStore.persist.clearStorage()` 호출

### ✅ [Todo Store (useTodoStore.js)](https://github.com/ghooman/react-zustand-basic/blob/main/src/store/useTodoStore.js)

- **스토리지**: `getStorage: () => sessionStorage`로 세션 스토리지 사용
- **불변성**: `todos: [...state.todos, { ... }]`로 스프레드 연산자 사용
- **CRUD 로직**: `filter`로 삭제, `map`으로 완료 상태(`isCompleted: true`) 갱신

### ✅ [User Store (useUserStore.js)](https://github.com/ghooman/react-zustand-basic/blob/main/src/store/useUserStore.js)

- **비동기 통신**: `axios`로 `async/await` 기반 API 호출
- **데이터 처리**: `response.data`를 그대로 상태에 반영
- **에러 처리**: `try-catch`로 예외 처리

---

## 3. 핵심 이론 요약

### ① 보일러플레이트 (Boilerplate)

- **정의**: 기능 구현에 반복적으로 작성되는 기본 코드
- **Zustand 특징**: Redux 대비 보일러플레이트가 적은 bear bones 스타일

### ② getId가 하단에 있어도 동작하는 이유 (호이스팅 아님)

- **코드**: `useTodoStore.js` 하단에 `const getId = () => id++` 선언
- **오개념**: `function` 선언문만 호이스팅되며, `const`/`let`은 호이스팅되지 않음
- **실제 이유**: `addTodos`는 사용자 클릭 시점에 실행되며, 그 시점에는 모듈 로딩이 끝나 `getId`가 이미 정의된 상태

### ③ 데이터 변환 및 통신

| 방식 | JSON 파싱 | 에러 처리 |
|------|-----------|----------|
| `fetch` | `response.json()`으로 수동 파싱 필요 | `response.ok` 등으로 직접 검사 |
| `axios` | `response.data`로 자동 파싱 | HTTP 에러 시 `catch`로 자동 전달 |

---

## 4. 실습 파일 링크

| 구분 | 파일 |
|------|------|
| Store | [useCounterStore.js](https://github.com/ghooman/react-zustand-basic/blob/main/src/store/useCounterStore.js) / [useTodoStore.js](https://github.com/ghooman/react-zustand-basic/blob/main/src/store/useTodoStore.js) / [useUserStore.js](https://github.com/ghooman/react-zustand-basic/blob/main/src/store/useUserStore.js) |
| Component | [Counter.js](https://github.com/ghooman/react-zustand-basic/blob/main/src/components/Counter.js) / [TodoList.js](https://github.com/ghooman/react-zustand-basic/blob/main/src/components/TodoList.js) |
