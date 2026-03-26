#### useEffect란?
useEffect는 렌더링 이후 실행되는 Hook으로 API호출이나 이벤트 등록 같은 사이드 이펙트를 처리할 때 사용합니다.
dependency array를 통해 실행 시점을 제어할 수 있습니다.


#### dependency array 문제
dependency를 잘못 설정할 경우 무한 루프가 발생하거나, 이전 값(stale)을 참조하는 문제가 발생합니다. 
따라서 effect 내부에서 사용하는 값은 dependency에 명시하는 것이 중요합니다.


#### useRef vs state
state는 변경 시 리렌더링이 발생하지만 useRef는 값이 변경되어도 리렌더링이 발생하지 않습니다. 
따라서 useRef는 DOM 접근이나 이전 값 저장처럼 렌더링과 무관한 데이터를 다룰 때 사용합니다.


#### useEffect vs useLayoutEffect
useEffect는 화면 렌더링 이후 비동기로 실행되며,
useLayoutEffect는 DOM 변경 후 화면이 그려지기 전에 동기적으로 실행됩니다.
따라서 DOM 측정이나 즉시 변경이 필요한 경우 useLayoutEffect를 사용합니다.


#### 리렌더링 조건
state 변경, props변경, 부모 컴포넌트 리렌더링 시 발생합니다.
이를 최적화하기 위해 React.memo 등을 사용할 수 있습니다.


#### key를 사용하는 이유
key는 리스트의 요소를 고유하게 식별하기 위해 사용되며,
Virtual DOM 비교 과정에서 어떤 요소가 변경되었는지 판단하는 기준이 됩니다.
index를 사용할 경우 순서 변경 시 잘못된 요소를 재사용 할 수 있습니다.


#### 상태 관리 방법
React에서는 useState, useReducer, Contenxt API 그리고 Redux 같은 외부 상태관리 라이브러리를 사용할 수 있습니다.
상황에 따라 적절한 방법을 선택하는 것이 중요합니다.
