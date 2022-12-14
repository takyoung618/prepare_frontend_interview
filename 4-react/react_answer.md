# prepare_frontend_interview

## React

- [prepare\_frontend\_interview](#prepare_frontend_interview)
  - [React](#react)
  - [React 시작](#react-시작)
    - [리액트는 라이브러리인가요 프레임워크인가요](#리액트는-라이브러리인가요-프레임워크인가요)
    - [리액트를 사용하는 이유](#리액트를-사용하는-이유)
    - [virtual DOM에 대해서 아나요](#virtual-dom에-대해서-아나요)
    - [React에서 함수 컴포넌트와 클래스 컴포넌트의 차이](#react에서-함수-컴포넌트와-클래스-컴포넌트의-차이)
    - [리액트에서 함수형 컴포넌트라고 부르지 않고 함수 컴포넌트라고 부르는 이유가 무엇인가요](#리액트에서-함수형-컴포넌트라고-부르지-않고-함수-컴포넌트라고-부르는-이유가-무엇인가요)
    - [props와 state의 차이](#props와-state의-차이)
    - [props가 컴포넌트간에 전달받는 것이라고 했는데 자식에서 부모로도 전달할 수 있는가](#props가-컴포넌트간에-전달받는-것이라고-했는데-자식에서-부모로도-전달할-수-있는가)
    - [FLUX에 대해서 아나요](#flux에-대해서-아나요)
    - [리덕스에 대해서 아나요](#리덕스에-대해서-아나요)
    - [리덕스의 기본 원칙은](#리덕스의-기본-원칙은)
    - [React에서 state의 불변성을 유지하라는 말이 있는데 이에 대해 설명해달라](#react에서-state의-불변성을-유지하라는-말이-있는데-이에-대해-설명해달라)
    - [리듀서 내부에서 불변성을 지키는 이유는? 전개 연산자의 단점을 해결할 수 있는 방법은 무엇인가](#리듀서-내부에서-불변성을-지키는-이유는-전개-연산자의-단점을-해결할-수-있는-방법은-무엇인가)
    - [리액트 사용시에 부수효과로 인해 생기는 문제점이 있다면](#리액트-사용시에-부수효과로-인해-생기는-문제점이-있다면)
      - [부수 효과를 일으키는 함수 (불순 함수)](#부수-효과를-일으키는-함수-불순-함수)
      - [부수 효과를 일으키지 않는 함수 (순수 함수)](#부수-효과를-일으키지-않는-함수-순수-함수)
      - [요약](#요약)
    - [컴포넌트의 라이프 사이클 메서드](#컴포넌트의-라이프-사이클-메서드)
    - [Hooks의 종류](#hooks의-종류)
    - [useMemo와 useCallback의 차이를 아나요](#usememo와-usecallback의-차이를-아나요)
    - [리액트에서 setState는 비동기 동작인가요 동기 동작인가요](#리액트에서-setstate는-비동기-동작인가요-동기-동작인가요)
    - [setState가 비동기 동작을 취했을 때 얻을 수 있는 이점은 무엇인가요](#setstate가-비동기-동작을-취했을-때-얻을-수-있는-이점은-무엇인가요)
    - [useLayoutEffect를 사용해보신 적 있나요](#uselayouteffect를-사용해보신-적-있나요)
    - [리액트의 성능개선 방법에 대해서 설명해주세요](#리액트의-성능개선-방법에-대해서-설명해주세요)
    - [컴포넌트에서 이벤트를 실행시키기 위해서는 어떻게 핸들링해야 하나요](#컴포넌트에서-이벤트를-실행시키기-위해서는-어떻게-핸들링해야-하나요)
    - [SPA가 뭔가요](#spa가-뭔가요)
      - [SPA의 단점](#spa의-단점)
    - [SSR이 뭔가요](#ssr이-뭔가요)
    - [SEO가 뭔가요](#seo가-뭔가요)
      - [TTV TTI](#ttv-tti)
    - [하이드레이션에 대해 알고 있나요](#하이드레이션에-대해-알고-있나요)
    - [Next의 렌더링 수행 방식](#next의-렌더링-수행-방식)
    - [Next를 쓴 이유가 있나요](#next를-쓴-이유가-있나요)
    - [Next를 구성하는 기본 설정 파일에 대해서 알고 있나요](#next를-구성하는-기본-설정-파일에-대해서-알고-있나요)
    - [사전 렌더링을 위해 사용해 본 함수가 있나요](#사전-렌더링을-위해-사용해-본-함수가-있나요)
  - [Suspense](#suspense)


<hr>

## React 시작

### 리액트는 라이브러리인가요 프레임워크인가요
- 라이브러리와 프레임워크의 가장 큰 차이는 제어 흐름의 권한을 누가 제어하느냐입니다. 따라서 리액트는 UI를 빌드할 때 가져다가 사용가능한 자바스크립트 라이브러리입니다.

### 리액트를 사용하는 이유
- 컴포넌트를 사용하기에 유지보수가 용이하며, 가상돔을 활용하여 변경된 부분만 실제 DOM에 적용하기에 재조정 과정이 효율적입니다. 그리고 SPA기에 전체 페이지를 하나의 페이지에 담아 동적으로 화면을 바꾸며 표현하기에 더 나은 사용자 경험을 제공합니다.

### virtual DOM에 대해서 아나요
- 리액트의 가상돔은 실제 DOM과 같은 내용을 담고 있는 복사본입니다. 변경된 내용이 화면에 새롭게 그려질 때, 리액트는 두 개의 가상돔을 비교하여 바뀐 부분만 파악하고 실제 DOM에 한번에 적용시키므로 효율적입니다.

### React에서 함수 컴포넌트와 클래스 컴포넌트의 차이
- 클래스형 컴포넌트는 로직과 상태를 컴포넌트 내에서 구현하기 때문에 상대적으로 복잡한 UI 로직을 가지고 있으며, state와 lifeCycle 관련 기능사용이 가능합니다. 반면 함수형 컴포넌트는 state를 사용하지 않고 단순하게 데이터를 받아서(props) UI에 뿌려주기 때문에 메모리를 덜 사용합니다.
- 이거 뭔가 정리가 뭔가 안깔끔함.. 오늘 다시보기

### 리액트에서 함수형 컴포넌트라고 부르지 않고 함수 컴포넌트라고 부르는 이유가 무엇인가요
- 함수형이라고 표현하는 것은 함수형 프로그래밍을 연상시켜 `'함수형 컴포넌트를 사용하면 함수형 프로그래밍이 가능해진다'`와 같은 혼란을 느낄 수 있었기 때문입니다. 

### props와 state의 차이
- props는 부모로부터 전달되는 불변의 데이터이고, state는 구성 요소에 의해 유지되는 가변 데이터이다. State는 내부 (컴포넌트)에서 생성하고 활동하고, 데이터를 변경할 수 있음. Props는 외부(부모 컴포넌트)에서 상속 받는 데이터이며, 데이터를 변경할 수 없음.

### props가 컴포넌트간에 전달받는 것이라고 했는데 자식에서 부모로도 전달할 수 있는가
- 통상적으론 부모에서 자식으로만 데이터를 줄 수 있지만 함수를 이용하면 가능합니다. 부모가 함수를 넣어 props로 자식에게 넘겨주면, 자식이 데이터를 파라미터로 넣어 호출하는 방식으로 동작한다. 즉, 부모가 props로 함수를 넣어주면 자식이 그 함수를 이용해 값을 건네주는 방식이다.

### FLUX에 대해서 아나요
- Flux는 단방향 데이터 흐름이기에 MVC의 복잡성이나 버그 문제를 해결가능한 애플리케이션 아키텍쳐입니다. 

### 리덕스에 대해서 아나요
- 리덕스는 자바스크립트 앱을 위한 예측 가능한 상태관리 라이브러리입니다. Store(스토어)라는 변수를 이용하여 전역 상태관리를 하기 때문에 상태관리가 용이하고, 테스트하기 쉬운 앱을 작성하도록 도와줍니다.

### 리덕스의 기본 원칙은
1. 애플리케이션의 모든 상태는 하나의 저장소 안에 하나의 객체 트리 구조로 저장됩니다.
2. 상태(state)는 읽기 전용입니다.
3. 순수 함수에 의해서 변경되어야 합니다.

### React에서 state의 불변성을 유지하라는 말이 있는데 이에 대해 설명해달라
- 리액트에서는 데이터를 저장할 때, 원본 배열의 값을 수정하지 않으면서 새로운 값을 만들어내는 것을 의미합니다. 

### 리듀서 내부에서 불변성을 지키는 이유는? 전개 연산자의 단점을 해결할 수 있는 방법은 무엇인가
- 얕은 비교를 수행해 효율적으로 상태를 업데이트하고, 원본데이터가 변경될 경우의 예기치 못한 오류를 방지하며 프로그램밍 구조를 단순화할 수 있기 때문입니다. 
- immer 라는 라이브러리를 사용하면 불변성을 유지하며 불필요한 부수효과도 막아줍니다.

### 리액트 사용시에 부수효과로 인해 생기는 문제점이 있다면
- 부수효과란 함수가 만들어진 목적과는 다른 효과 또는 부작용입니다.

#### 부수 효과를 일으키는 함수 (불순 함수)
- 불순 함수는 함수의 안팎에서 예기치 않은 일이 생길 가능성이 있는 함수입니다. 즉, 매개변수로 들어온 값을 직접 변경하거나 비동기 http 요청이 불순함수입니다.

#### 부수 효과를 일으키지 않는 함수 (순수 함수)
- 함수의 매개변수로 들어온 값을 직접 변경하는 것을 피하기만 해도, 순수함수를 만들 수 있습니다. 순수함수가 많아지고, 선언된 변수들을 직접 조작하지 않을수록 코드의 예측가능성이 높아집니다.

#### 요약
- React state는 직접 조작을 피하는 방식으로 부수효과를 방지합니다.(state, props가 변경될 때 리렌더링이 되기 때문에 의도치 않게 부수효과를 가진 함수들로 인해 불필요한 리렌더링이 잦아질 수 있다) Redux의 reducer는 순수함수여야만 하는데, store값을 변경하는 함수가 부수효과가 없어야 store 내부의 값들이 안전하게 보호될 수 있으며, 테스트가 쉬워지기 때문입니다. 

### 컴포넌트의 라이프 사이클 메서드
- 
라이프사이클 메서드의 종류는 총 아홉 가지입니다.

- will 접두사가 붙은 메서드는 어떤 작업을 작동하기 전에 실행되는 메서드입니다.
- Did 접두사가 붙은 메서드는 어떤 작업을 작동한 후에 실행되는 메서드입니다.

이 메서드들은 우리가 컴포넌트 클래스에서 덮어 써 선언함으로써 사용할 수 있습니다. 라이프사이클은 총 세 가지, 즉 마운트, 업데이트, 언마운트 카테고리로 나눕니다.

<img src="https://github.com/junh0328/TIL/raw/master/React/images/lifeCycle.png" alt="컴포넌트 라이프 사이클 메서드"/>

1. 마운트

- DOM이 생성되고 웹 브라우저상에 나타나는 것을 마운트라고 한다.

- componentDidMount : 컴포넌트가 웹 브라우저상에 나타난 후 호출하는 메서드이다.

<br/>

2. 업데이트

**컴포넌트는 다음과 같은 총 네 가지 경우에 업데이트합니다.**

- Props가 바뀔 때
- state가 바뀔 때
- 부모 컴포넌트가 리렌더링될 때
- this.forceUpdate로 강제로 렌더링을 트리거할 때

- componentDidUpdate : 컴포넌트의 업데이트(리렌더링) 작업이 끝난 후 호출하는 메서드입니다.

<br/>

3. 언마운트

- 마운트의 반대 과정, 즉 컴포넌트를 DOM에서 제거하는 것을 말한다.

- componentWillUnmount : 컴포넌트가 웹 브라우저사에서 사라지기 전에 호출하는 메서드이다.

<img src="https://github.com/junh0328/TIL/raw/master/React/images/lifeCycleFlow.png" alt="라이프사이클 메서드">

<br/>

### Hooks의 종류

**Hooks는 리액트 버전 16.8에 새로 도입된 기능으로 함수 컴포넌트에서도 상태 관리를 할 수 있는 useState 렌더링 직후 작업을 설정하는 useEffect 등의 기능을 제공하여 기존의 함수 컴포넌트에서 할 수 없었던 다양한 작업을 할 수 있게 해준다**

1. useState

- 가장 기본적인 Hook이다. 첫 번째 원소는 상태 값, 두 번째 원소는 상태를 설정하는 함수이다.
- 이 함수에 파라미터를 넣어서 호출하면 전달받은 파라미터로 값이 바뀌고 컴포넌트가 정상적으로 리렌더링 됩니다

```jsx
import { useState } from "react";

const [value, setValue] = useState(0);
```

<br/>

2. useEffect

- 리액트 컴포넌트가 렌더링될 때마다 특정 작업을 수행하도록 설정할 수 있는 Hook 입니다. 클래스형 컴포넌트의 componontDidMount와 componentDidUpdate를 합친 형태로 보아도 무방합니다

`마운트만 실행시키고 싶을 경우` : 두 번째 파라미터로 비어있는 배열을 넣어주면 된다

```jsx
useEffect(() => {
  console.log("마운트될 때만 실행됩니다.");
}, []);
```

`특정 값이 업데이트될 때만 실행하고 싶을 경우` : 두 번째 파라미터로 전달되는 배열 안에 검사하고 싶은 값을 넣어주면 된다

```jsx
useEffect(() => {
  console.log(name);
}, [name]);
```

`뒷 정리 하기`:

- 정리 : useEffect는 기본적으로 렌더링되고 난 직후마다 실행되며 두 번째 파라미터 배열에 무엇을 넣는지에 따라 실행되는 조건이 달라집니다

useEffect는 기본적으로 렌더링되고 난 직후마다 실행되며, 두 번째 파라미터 배열에 무엇을 넣는지에 따라 실행되는 조건이 달라집니다.

컴포넌트가 언마운트되기 전이나 업데이트되기 직전에 어떠한 작업을 수행하고 싶다면 useEffect에서 뒷정리(cleanup) 함수를 반환해 주어야 합니다.

언마운트 시에 작업할 코드를 넣어준다고 생각하면 됩니다.

```jsx
useEffect(() => {
    console.log("렌더링이 완료되었습니다!");
    console.log("none clean up: ", { name, nickname });
    return () => {
      console.log("clean up!");
      console.log("clean up name: ", { name });
    };
  }
```

<img src="https://github.com/junh0328/TIL/raw/master/React/images/cleanup.gif" alt="뒷정리함수">

<br/>

3. useReducer

- useReducer는 useState보다 더 다양한 컴포넌트 상황에 따라 다양한 상태를 다른 값으로 업데이트해 주고 싶을 때 사용하는 Hook입니다. 리듀서는 현재 상태, 그리고 업데이트를 위해 필요한 정보를 담은 액션 값을 전달받아 새로운 상태에 반환하는 함수입니다. 리듀서 함수에서 새로운 상태를 만들 때는 반드시 불변성을 지켜주어야 합니다.

<br/>

4. useMemo

useMemo를 사용하면 함수 컴포넌트 내부에서 발생하는 연산을 최적화할 수 있습니다. 먼저 리스트에 숫자를 추가하면 추가된 숫자들의 평균을 보여 주는 함수 컴포넌트를 작성해 봅시다.

그런데 숫자를 등록할 때뿐만 아니라 인풋 내용이 수정될 때도 우리가 만든 getAverage 함수가 호출되는 것을 확인할 수 있습니다. 인풋 내용이 바뀔 때는 평균값을 다시 계산할 필요가 없는데, 이렇게 렌더링할 때마다 계산하는 것은 낭비겠지요?

useMemo Hook을 사용하면 이러한 작업을 최적화할 수 있습니다. 렌더링하는 과정에서 특정 값이 바뀌었을 때만 연산을 실행하고, 원하는 값이 바뀌지 않았다면 이전에 연산했던 결과를 다시 사용하는 방식입니다.

<img src="https://github.com/junh0328/TIL/raw/master/React/images/usememo.png" alt="memo"/>

<details>
<summary>코드 보기</summary>

```jsx
import React, { useCallback, useMemo, useRef, useState } from "react";

const getAverage = (numbers) => {
  console.log("평균값 계산 중..");
  if (numbers.length === 0) return 0;
  const sum = numbers.reduce((a, b) => a + b);
  return sum / numbers.length;
};

const Average = () => {
  const [list, setList] = useState([]);
  const [number, setNumber] = useState("");
  const inputEl = useRef();

  const onChange = useCallback((e) => {
    setNumber(e.target.value);
  }, []); // 컴포넌트가 처음 렌더링될 때만 함수 생성

  const onInsert = useCallback(
    (e) => {
      const nextList = list.concat(parseInt(number));
      setList(nextList);
      setNumber("");
      inputEl.current.focus();
    },
    [number, list] // number 혹은 list가 바뀌었을 때만 함수 생성
  );

  const avg = useMemo(() => getAverage(list), [list]);

  return (
    <div>
      <input value={number} onChange={onChange} ref={inputEl} />
      <button onClick={onInsert}>등록</button>
      <ul>
        {list.map((value, index) => (
          <li key={index}>{value}</li>
        ))}
      </ul>
      <div>
        <b>평균값:</b> {avg}
      </div>
    </div>
  );
};

export default Average;
```

</details>

<br/>

5. useCallback

- useMemo와 상당히 비슷한 함수이다. 주로 렌더링 성능을 최적화 해야하는 상황에서 사용한다. 이 Hook을 사용하면 **만들어놨던 함수를 재사용할 수 있다.** useCallback의 첫 번째 파라미터에는 생성하고 싶은 함수를 넣고, 두 번째 파라미터에는 배열을 넣으면 된다. 이 배열에는 어떤 값이 바뀌었을 때 함수를 새로 생성해야 하는지 명시해야 한다.

<details>

```jsx
const onChange = useCallback((e) => {
  setNumber(e.target.value);
}, []); // 컴포넌트가 처음 렌더링될 때만 함수 생성


const onInsert = useCallback(
  (e) => {
    const nextList = list.concat(parseInt(number));
    setList(nextList);
    setNumber("");
  },
  [number, list] // number 혹은 list가 바뀌었을 때만 함수 생성
);


useMemo(() => {
  const fn = () => {
    console.log(‘hello world!‘);
  };
  return fn;
}, [])
```

onChange처럼 비어 있는 배열을 넣게 되면 컴포넌트가 렌더링될 때 단 한 번만 함수가 생성되며, onInsert처럼 배열 안에 number와 list를 넣게 되면 인풋 내용이 바뀌거나 새로운 항목이 추가될 때마다 함수가 생성됩니다.

함수 내부에서 상태 값에 의존해야 할 때는 그 값을 반드시 두 번째 파라미터 안에 포함시켜 주어야 합니다. 예를 들어 onChange의 경우 기존의 값을 조회하지 않고 바로 설정만 하기 때문에 배열이 비어 있어도 상관없지만, onInsert는 기존의 number와 list를 조회해서 nextList를 생성하기 때문에 배열 안에 number와 list를 꼭 넣어 주어야 합니다.

참고로 다음 두 코드는 완전히 똑같은 코드입니다.

```jsx
useCallback(() => {
  console.log("hello world!");
}, []);

useMemo(() => {
  const fn = () => {
    console.log("hello world!");
  };
  return fn;
}, []);
```

</details>

6. useRef

- 바닐라 자바스크립트에서 DOM 요소를 조작하기 위해 querySelector나 getElementById 등을 사용했다면, 리액트에서는 useRef 훅 함수를 사용합니다.
- useRef는 `.current` 프로퍼티에 변경가능한 값을 담고있는 객체입니다
- `.current`프로퍼티를 변경하더라도 리렌더링을 유발하지 않습니다. ref 객체 안의 값은 리액트 생명주기에 독립적이기 때문입니다

```jsx
import React, { useRef, Component } from "react";

class RefSample extends Component {
  input = useRef();

  handleFocus = () => {
    this.input.current.focus();
  };

  render() {
    return (
      <div>
        <input ref={input} />
      </div>
    );
  }
}

export default RefSample;
```

<br/>

### useMemo와 useCallback의 차이를 아나요

- useMemo 함수는 메모이제이션된 `값`을 반환한다
- useCallback 함수는 메모이제이션 된 `함수`를 반환한다

```
Memoization(메모이제이션)

프로그램 실행 시 이전에 계산한 값을 저장한다
원하는 값이 바뀌지 않았다면 이전에 연산했던 결과를 다시 사용하는 방식입니다.
```

리액트에서 사용하는 컴포넌트는 다음과 같은 경우에 리렌더링됩니다

- props가 바뀔 때
- state가 바뀔 때
- 부모 컴포넌트가 리렌더링될 때

컴포넌트는 state와 부모로부터 전달받은 props 등 다양한 조건에 의해 쉽게 리렌더링이 될 수 있습니다.

불필요한 리렌더링을 내가 만든 서비스의 성능 저하에 가장 큰 원인이 되기도 합니다.

이렇게 특정 상황 (값, 또는 함수가 변경될 때)에 맞게 리렌더링이 될 수 있도록 useMemo와 useCallback 함수를 사용합니다.

의존성 배열로 어떤 값에 의해 바뀌는 지 확인하기 위해서는 해당 함수의 두 번째 콜백인 `[]` 배열 내부의 값을 보면 됩니다.

```jsx
// useMemo
const avg = useMemo(() => getAverage(list), [list]); // list 라는 값이 변결될 때'만' getAverage 함수를 재 호출하는 용도입니다

// useCallback
const onInsert = useCallback(
  (e) => {
    const nextList = list.concat(parseInt(number));
    setList(nextList);
    setNumber("");
  },
  [number, list] // number 혹은 list가 바뀌었을 때만 onInsert 함수 생성
);
```

```jsx
// useMemo

<div>
  <b>평균값:</b> {avg}
</div>
```

```jsx
// useCallback

<button onClick={onInsert}>등록</button>
```

<br/>

### 리액트에서 setState는 비동기 동작인가요 동기 동작인가요

[참고자료](https://velog.io/@jinsunee/setState%EA%B0%80-%EB%B9%84%EB%8F%99%EA%B8%B0%ED%95%A8%EC%88%98%EC%9D%B8-%EC%9D%B4%EC%9C%A0)

```jsx
function Example() {
  const [count, setCount] = React.useState(0);

  useEffect(()=>{
    console.log('in useEffect:', count)
  },[count])

  const onClickButton = () => {
    console.log("before", count);

    setCount(count + 1);
    // setCount(prev => prev+1);

    console.log("after", count);
  };

  return <button onClick={onClickButton}>{count}</button>;
}

>>>
/*
  before 0
  after 0
  in useEffect 1
*/
```

state 값을 갱신하는 함수인 `setState` 는 비동기로 동작하는 훅 함수입니다

React는 앞서 언급했듯 state, props 값에 따라 re-rendering이 일어나죠.

그런데 만약에 한 컴포넌트 안에서 여러 state 값을 연속으로 바꿔주는 일이 생긴다면 여러번 비교하고 다시 그리는 알고리즘이 실행됩니다.

너무 비효율적이고 성능이 당연히 안좋을 것 입니다. 또 이중에 바뀌지 않아도 되는 불필요한 리렌더링 다수 발생할 것으로도 예상이 됩니다

이에 대비하여 리액트 라이브러리는 state를 다시 설정하는 함수인 setState를 비동기 함수로 처리해서 컴포넌트 내의 비동기 함수를 처리하는 콜백큐가 다 비워지면 리렌더링하도록 설계했습니다.

그 말인 즉, 해당 함수 내에서 동기적으로 실행되는 함수가 모두 실행된 뒤에 마지막에 setState를 처리한다는 이야기겠죠?

```jsx
const onClickButton = () => {
  console.log("before", count); // ----> 동기함수

  setCount(count + 1); // ---->  비동기함수

  console.log("after", count); // ---->  동기함수
};
```

<br/>

### setState가 비동기 동작을 취했을 때 얻을 수 있는 이점은 무엇인가요

앞서 말했지만, setState가 비동기 동작을 취함으로써 자바스크립트 내의 실행컨텍스트 스택이 돌아갈 때 동기적으로 실행되는 함수들을 모두 동작한 뒤에 큐에 존재하는 비동기적인 함수들을 이벤트 루프에 의해 꺼내와서 실행시킵니다.

setState가 동기적으로 실행된다면, 한 컴포넌트 내부에 존재하는 함수에 의해 state 값이 연속적으로 변경될 경우 리액트의 컴포넌트 리렌더링 조건에 의해 지속적으로 리렌더링이 될 것입니다.

<br/>

### useLayoutEffect를 사용해보신 적 있나요

[참고자료](https://merrily-code.tistory.com/46)

**리액트 훅 함수를 바탕으로 한 생명주기는 다음과 같습니다**

<img src="https://raw.githubusercontent.com/donavon/hook-flow/master/hook-flow.png" width="500" alt="hookflow">

브라우저가 렌더링될 때 `.js` 파일은 브라우저에서 자바스크립트 엔진으로 권한을 넘겨 `.js` 해당 파일을 파싱되고 그리게 됩니다.

위 그림의 훅 라이프 사이클을 보시다시피 브라우저가 스크린에 페인팅 작업이 완료된 이후에 우리는 `useEffect` 를 실행하는 구조를 가졌었습니다.

따라서 다음과 같이 렌더링할 때 `useState(0)`과 같은 초기 useState의 값이 빈 값이라면, 0을 출력했다가 useEffect를 통해 값이 채워지는 구조를 가졌었습니다.

```jsx
// 코드 참고: https://merrily-code.tistory.com/46

import { useEffect, useState } from "react";

function App() {
  const [age, setAge] = useState(0);
  const [name, setName] = useState("");

  useEffect(() => {
    setAge(25);
    setName("찬민");
  }, []);

  return (
    <>
      <div className="App">{`그의 이름은 ${name} 이며, 나이는 ${age}살 입니다.`}</div>
    </>
  );
}

export default App;
```

<img src="https://blog.kakaocdn.net/dn/eFC5OT/btqXwdg7gIx/RrXfz887pljat4sRFebgr0/img.gif" width="500" alt="useEffect"/>

**useLayoutEffect 훅은 바로 이런 문제를 해결하기 위해 등장한 훅입니다.**

`useLayoutEffect`는 브라우저가 화면에 DOM을 그리기 전에 이펙트를 수행합니다 .

따라서 위 코드의 실행 순서도 달라지게 됩니다.

1. 레이아웃 이펙트 내부의 setNumber, setName 호출

2. `<div>그의 이름은 찬민이며, 나이는 25살 입니다.</div>` 를 페인트

```jsx
// 코드 참고: https://merrily-code.tistory.com/46

import { useLayoutEffect, useState } from "react";

function App() {
  const [age, setAge] = useState(0);
  const [name, setName] = useState("");

  useLayoutEffect(() => {
    setAge(25);
    setName("찬민");
  }, []);

  return (
    <>
      <div className="App">{`그의 이름은 ${name} 이며, 나이는 ${age}살 입니다.`}</div>
    </>
  );
}

export default App;
```

<img src="https://blog.kakaocdn.net/dn/o7cjk/btqXu54HI2S/YQPWUG8kK8ns0sL62VFtpK/img.gif" width="500" alt="useLayoutEffect"/>

<br/>

### 리액트의 성능개선 방법에 대해서 설명해주세요

제가 사용해 본 성능 개선 방법은 다음과 같습니다.

- hook 함수 사용 (useMemo, useCallback)
- 코드 스플리팅 (react.lazy(), Next.js 프레임워크 사용 등)

<br/>

### 컴포넌트에서 이벤트를 실행시키기 위해서는 어떻게 핸들링해야 하나요

**이벤트로 설정할 함수를 호출하는 것이 아닌 직접 넣어 줄 때는 화살표 함수 문법을 사용하여 넣어 주어야 합니다**

```jsx
case 1: 작동하지 않는 문법
<button onClick={this.setState({ number: number + 1})}>  (x)

case 2: 작동하는 문법
<button onClick={()=> this.setState({ number: number + 1}; )}>  (o)

or
case 3: 아예 함수로 빼주고 해당 함수를 불러 사용한다.

const plusNum = (number) => {
  setState(number : number + 1);
}
...

<button onClick={plusNum}>+ 1 </button>
```

<br/>

### SPA가 뭔가요

<p>SPA는 Single Page Application(싱글 페이지 애플리케이션)의 약어입니다. 말 그대로 한 개의 페이지로 이루어진 애플리케이션이라는 의미입니다. 전통적인 웹 페이지는 다음과 같이 여러 페이지로 구성되어 있습니다.</p>

<img src="https://github.com/junh0328/TIL/raw/master/React/images/MPA.png" alt="MPA"/>

<p>기존에는 사용자가 다른 페이지로 이동할 때마다 새로운 html을 받아 오고, 페이지를 로딩할 때마다 서버에서 리소스를 전달받아 해석한 뒤 화면에 보여 주었습니다. 이렇게 사용자에게 보이는 화면은 서버 측에서 준비했습니다. 사전에 html 파일을 만들어서 제공하거나, 데이터에 따라 유동적인 html을 생성해주는 템플릿 엔진을 사용하기도 했죠.</p>

<p>요즘에는 웹에서 제공되는 정보가 정말 많기 때문에 새로운 화면을 보여 주어야 할 때마다 서버 측에서 모든 뷰를 준비한다면 성능상의 문제가 발생할 수 있습니다. 예를 들어 트래픽이 너무 많이 나올 수도 있고, 사용자가 몰려 서버에 높은 부하가 쉽게 걸릴 수도 있습니다. 그래서 리액트 같은 라이브러리 혹은 프레임워크를 사용하여 뷰(View) 렌더링을 사용자의 브라우저가 담당하도록 하고, 우선 애플리케이션을 브라우저에 불러와서 실행시킨 후에 사용자와의 인터랙션이 발생하면 <b>필요한 부분만 자바스크립트를 사용하여 업데이트해 줍니다.</b> 만약 새로운 데이터가 필요하다면 서버 API를 호출하여 필요한 데이터만 새로 불러와 애플리케이션에서 사용할 수도 있습니다.</p>

<img src="https://github.com/junh0328/TIL/raw/master/React/images/SPA.png" alt="SPA"/>

> 사용자와의 인터렉션이 발생하면 필요한 부분만 자바스크립트를 사용하여 업데이트 (JSON 형식으로 요청함)

<img src="https://github.com/junh0328/TIL/raw/master/React/images/SPAVSMPA.png" alt="SPAVSMPA"/>

[출처 : https://babytiger.netlify.app/posts/SPA/]

<p>싱글 페이지라고 해서 화면이 한 종류인 것은 아닙니다. SPA의 경우 서버에서 사용자에게 제공하는 페이지는 한 종류이지만, 해당 페이지에서 로딩된 자바스크립트와 현재 사용자 브라우저의 주소 상태에 따라 다양한 화면을 보여 줄 수 있습니다.</p>

<p>다른 주소에 다른 화면을 보여 주는 것을 라우팅이라고 합니다. 리액트 라이브러리 자체에 이 기능이 내장되어 있지 않기 때문에, 브라우저의 API를 직접 사용하여 이를 관리하거나, 라이브러리를 사용하여 이 작업을 더욱 쉽게 구현할 수 있습니다.</p>

<p>리액트 라우팅 라이브러리는 리액트 라우터(react-router), 리치 라우터(reach-router), Next.js 등 여러 가지가 있습니다. 이러한 리액트 라우팅 라이브러리는 클라이언트 사이드에서 이루어지는 라우팅을 아주 간단하게 구현할 수 있도록 해 줍니다. 더 나아가 나중에 서버 사이드 렌더링을 할 때도 라우팅을 도와주는 컴포넌트들을 제공해 줍니다.</p>

<br/>

#### SPA의 단점

<p>SPA의 단점은 앱의 규모가 커지면 자바스크립트 파일이 너무 커진다는 것입니다. 페이지 로딩 시 사용자가 실제로 방문하지 않을 수도 있는 페이지의 스크립트도 불러오기 때문이죠. 하지만 후에 배울 코드 스플리팅(code splitting)을 사용하면 라우트별로 파일들을 나누어서 트래픽과 로딩 속도를 개선할 수 있습니다.</p>

<p>리액트 라우터처럼 브라우저에서 자바스크립트를 사용하여 라우팅을 관리하는 것은 자바스크립트를 실행하지 않는 일반 크롤러에서는 페이지의 정보를 제대로 수집해 가지 못한다는 잠재적인 단점이 따릅니다. 그렇기 때문에 구글, 네이버, 다음과 같은 검색 엔진의 검색 결과에 페이지가 잘 나타나지 않을 수도 있습니다. 또한, 자바스크립트가 실행될 때까지 페이지가 비어 있기 때문에 자바스크립트 파일이 로딩되어 실행되는 짧은 시간 동안 흰 페이지가 나타날 수 있다는 단점도 있습니다. 하지만 이런 문제점들은 다행히 나중에 배우게 될 서버 사이드 렌더링(server-side-rendering)을 통해 모두 해결할 수 있습니다.</p>

<br/>

### SSR이 뭔가요

<p>리액트는 대표적인 CSR(client side rendering)입니다. 이러한 리액트의 CSR적인 부분에서 SSR 적으로 바꿔 주기 위해서 next.js와 같은 라이브러리를 사용합니다.</p>

<p>SSR을 사용하는 가장 큰 이유는 효율적인 SEO를 위해서 입니다. 아래 문단에서 다루겠지만, SEO는 google, naver와 같은 검색 엔진들이 우리의 웹사이트에서 html 태그안의 내용을(title, meta-data 등등,,,) 분석하여 사용자가 입력한 정보를 바탕으로 알맞은(사용자가 원하는) 정보를 찾을 수 있게 하는 기능입니다. 리액트는 CSR으로 작동되는데, 사용자가 우리의 해당 도메인에 접속하면, 클라이언트 서버(사용자의 컴퓨터)가 html과 js 등의 파일을 다운받아 보여주는 형식입니다. CSR 상태에서는 사전에 html을 가지고 있지 않기 때문에 검색 엔진에 노출되는 빈도가 현저히 적거나, 브라우저에 따라 검색 엔진에 해당 정보가 노출되지 않아 검색을 해도 나오지 않을 수 있습니다.(도메인을 통해 접속하는 것은 가능해지는 정도, 해당 사이트에 관련된 정보를 검색 엔진이 크롤링하지 못할 수 있음)그래서 SSR을 통해 서버가 사전에 html과 일부 js 파일을 넘겨주게 되면, 검색 엔진에서 이를 캐치하여 사용자가 원하는 정보가 담긴 우리 사이트를 보여줄 수 있을 것입니다.</p>

<br/>

### SEO가 뭔가요

<p>SEO란, Search Engine Optimization의 약자로, SEO는 구글, 네이버와 같은 검색 엔진들이 서버에 등록된 웹사이트를 하나하나씩 돌아 다니면서 웹사이트의 HTML 문서를 분석해줍니다. 이때 HTML에 사용된 태그를 바탕으로 사용자가 검색할 때, 웹사이트를 빠르게 검색할 수 있게 도와줍니다. 하지만, CSR에서 사용되고있는 HTML의 body는 텅텅 비어 있다가(div id="root"의 리액트 특성), 사용자가 해당 도메인을 가진 페이지에 접근하면, 클라이언트 서버에서 js 밑 html 태그를 불러오는 형식이기 때문에 사전에 html 정보를 가지고 있지 않습니다. 그래서 검색 엔진이 해당 도메인에 접근할 때 어려움이 있습니다. (우리 사이트를 검색 엔진을 통해 다양한 키워드를 통해 유입되는 것이 힘들다 why? 검색 엔진이 우리 html 파일을 분석할 수 없기 때문에 why? CSR 형식은 사용자가 접근해야 html, js 등의 파일을 불러오기 때문에) 따라서, 검색 엔진을 통해 사용자가 입력하여 얻고자하는 정보를 입력했을때, 검색 엔진이 우리의 웹 사이트에서 해당 내용을 캐치하는데 어려움이 있습니다.</p>

<p>따라서 우리는 SEO 즉, 검색 엔진 최적화를 해주기 위해, SSR을 사용하여 사전에 html 문서를 검색 엔진이 찾을 수 있도록 제공하여 SEO를 향상시킬 수 있게 됩니다. SSR은 서버에서 필요한 데이터를 가져와 사전에 html 파일을 만들게 되고 이렇게 만들어진 HTML 파일을 일부 초기 세팅에 필요한 js와 함께 클라이언트 서버에 보내주게 됩니다. 그러면 클라이언트 측에서는 서버에서 만들어준 문서를 받아 와서 바로 사용자에게 보여줄 수 있게 되는 거죠. 이렇게 SSR을 사용하게 되면 사전에 HTML 문서를 클라이언트 측으로 전달했기 때문에, 페이지 로딩이 빨라지고, 검색 엔진이 사용자의 요청에 따라 검색어를 찾을 때(데이터를 크롤링할 때), 우리의 웹사이트에 해당 검색어가 포함되어 있다면 우리 페이지를 보여주는 효율적인 SEO가 될 수 있습니다.</p>

<p>하지만 SSR이 CSR의 모든 문제점에 해결책이 되지는 않습니다. 서버에서 데이터를 사전에 받아오는 것이기 때문에 첫 번째로 blinking issue가 여전히 존재하고(페이지가 넘어갈 때마다 깜빡임 why? html 및 js 파일을 새로 받아오기 때문에), 두 번째로 사용자가 증가함에 따라 서버는 사용자의 요청에 의해 더 많은 데이터를 가지고 와서 HTML을 만들어야 하므로 과부화가 올 수 있습니다. 마지막으로 가장 큰 문제는 사용자가 빠르게 웹사이트를 확인할 수는 있지만, SSR시 모든 js파일을 다운 받은 상태가 아니기 때문에, js파일이 완전히 다운로드 되지 않은 상태에서 페이지의 여러 부분을 클릭하면, 작동이 되지 않는 부분이 존재할 수 있습니다.</p>

#### TTV TTI

> TTV는 보여지는 시점 (Time To View), TTI는 인터렉션 사용자와의 통신이 가능해지는 시점 (Time To Interact)입니다

<p>CSR은 사용자에게 보여짐과 동시에 모든 html과 js를 불러온 상태이기 때문에, TTV과 됨과 동시에 TTI 모든 동적인 행동을 할 수 있게 됩니다.</p>

<p>하지만, SSR은 html과 일부 js파일은 서버로부터 사전에 받아 놓았기 때문에 TTV 상태에서도 TTI가 전부 활성화되어 있지는 않습니다</p>

<p>최종적으로 CSR을 많이 사용한다면, 우리가 최종적으로 번들링하여 사용자게에 보내주는 js 파일을 어떻게 하면 효율적으로 많이 분할하여 첫 번째로 사용자가 보기 위해서 필요한 정말 필수적인 html 요소만 보낼 수 있을지 고민해봐야 하고, SSR의 경우 사용자가 보고, 인터렉션(TTI)하는 이 시간의 단차를 줄이기 위해서 어떤 노력을 할 수 있을지 고민해봐야 합니다. 예를 들면 어떻게 하면 조금 더 매끄러운 UI와 UX를 제공할 수 있을지에 대한 고민들이 포함됩니다.</p>

<p>요즘에는 SSR, CSR 뿐만 아니라 SSG(Static Site Generation)또한 렌더링 방법으로 등장하였습니다. SSG는 리액트를 예로 들면 'Gatsby' 또는 'Next'와 같은 라이브러리를 추가적으로 사용하여 렌더링을 하는 것인데, 웹페이지를 정적으로 미리 생성해두고, 서버에 배포해놓는 것입니다. SSG에서도 자바스크립트 파일을 html 파일과 함께 가지고 있을 수 있기 때문에, 동적인 요소도 충분히 추가할 수 있습니다. Next에서는 SSR뿐만 아니라, static generation, no pre-rendering, pre-rendering상태를 모두 지원하기 때문에 리액트로 작업을 계속한다면 next.js를 배워보는 것도 매우 효과적일 겁니다.</p>

<p>어떤 것이 최고다, 제일 낫다라는 판단 보다는 우리가 만들어야 하는 웹사이트 특성에 맞게 다양한 방식의 렌더링을 활용하여 페이지를 구성한다면 최선의 선택이 될 것입니다.</p>

### 하이드레이션에 대해 알고 있나요

[참고 자료 1 🔥](https://simsimjae.tistory.com/389)
[참고 자료 2 🔥](https://fourwingsy.medium.com/next-js-hydration-%EC%8A%A4%ED%83%80%EC%9D%BC-%EC%9D%B4%EC%8A%88-%ED%94%BC%ED%95%B4%EA%B0%80%EA%B8%B0-988ce0d939e7)

```
hydration = 수화 = 우리 몸에 수분을 보충하는 행위
```

하이드레이션이란, **리액트에서 서버사이드 렌더링 혹은 SSG(스태틱 사이트 제네레이션)을 실행한 HTML 결과물을 받아온 뒤, 브라우저에서 이것을 다시 리액트 트리에 맞게 파싱하는 행위이다**.

<img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FQ46M7%2FbtqCRzEosOt%2F2JxdfPQP3OuPcsUjFbpOok%2Fimg.png" alt="hydration">

출처 (https://simsimjae.tistory.com/389)

서버가 완성된 HTML을 내려준다. 이때 Dehydrate는 수분을 없앤다는 뜻이다. 다시 말해서 동적인것을 정적으로 만드는 행위를 Dehydrate라고 표현했다. 그리고 나서 JS가 실행되면서 리액트가 정적인 HTML과 store를 동적인 리액트 컴포넌트 트리와 store로 변환하는 과정이 일어나는데, 이걸 (Re)hydrate라고 한다. 마치 수분기 없는 정적인 상태에서 수분 넘치는 동적인 상태로 변화한것이다. 문제는 이렇게 rehydrate가 일어나면서 쓸데없이 화면이 한번더 그려지는 현상이 발생한다는것이다. 왜냐면 리액트는 서버에서 완성된 HTML이 내려와서 이미 화면에 제대로 렌더링이 됬는지 안됬는지 모르고 자신이 할일을 그냥 했을 뿐이다. 그래서 SSR을 하는 경우에는 ReactDom의 render메소드가 아니라 hydrate 메소드를 사용해야 한다고 말했었다.

이 hydrate 단계에서,

- 렌더링한 결과물이 어떤 컴포넌트인지 확인한다
- 각 컴포넌트에 걸린 이벤트 들을 실제 DOM에 걸어주는 동작을 하게 된다

하이드레이션이 잘못되었을 때, 우리가 마주하는 문제들은 거의 1번 과정이 잘못되어서 일어난다.

Next.JS에서 내부적으로 사용하는 ReactDOM.hydrate 함수는 다음과 같은 일을 한다.

- 서버에서 받아온 DOM tree와 자체적으로 렌더링한 tree를 비교한다
- 두 tree 사이의 차이(diff, diffrence)를 얻어낸 뒤, 자체적으로(클라이언트사이드) 렌더링 한 tree에 맞춰 patch를 적용한다

`hydration이 되어야 진짜 리액트 컴포넌트`

서버에서 내려준 HTML로 렌더링 된 화면은 그냥 단순히 그림일 뿐이다. 리액트가 관리하지 않는 화면이다. SSR을 하더라도 컴포넌트를 리액트가 관리하게 하기 위해서는 hydration은 꼭 필요한 작업이다.

`결론`

리액트에서 hydration이라고 하는 용어를 사용하는 이유는 "서버사이드 렌더링으로 만들어진 수분이 없는 정적인 HTML과 State로부터 수분을 보충하는 과정(동적인 상태로 변화)인 hydrate가 일어나기 때문" 이라고 추측해본다.

<br/>

### Next의 렌더링 수행 방식

[참고 자료: Velog, Next.js 100% 활용하기](https://velog.io/@devstone/Next.js-100-%ED%99%9C%EC%9A%A9%ED%95%98%EA%B8%B0-feat.-initialProps-webpack-storybook)

1. SSR을 기반으로 서버에 사전에 저장된 렌더트리(render tree)의 HTML을 로드
2. ① 방식의 `사전 렌더링(pre-render)` 이후에는 CSR 사용
3. 페이지가 그려진 이후에 페이지 내부에서 동적인 데이터를 패치`(axios, fetch, XMLHttpRequest)`하는 과정은 `CSR` 방식을 따른다.
4. 만약 페이지가 로드될 때 함게 데이터가 패칭되어야 하는 상황이라면(pre-render)
5. next.js의 데이터 패칭 방식 (① getInitialProps/ ② getStaticProps / ③ getStaticPath / ④ getServerSideProps) 을 이용해 첫 렌더링 시에 HTML 파일 뿐만 아니라 데이터가 패칭될 수 있도록 처리해야 합니다.

<br/>

### Next를 쓴 이유가 있나요

[출처: 클론 코딩으로 시작하는 Next.js](https://bjpublic.tistory.com/391)

`1. 사전 렌더링 및 서버 사이드 렌더링`

- 서버 사이드 렌더링 기능을 제공하여 클라이언트 사이드 렌더링 환경보다 빠른 렌더링을 불러올 수 있습니다.

`2. Hot Code Reloading을 지원`

- Next 개발 환경에서는 코드 변경 사항이 저장되면 응용 프로그램을 자동으로 다시 로드합니다.

`3. 자동 코드 분할`

- 자동 코드 분할 기능 덕분에 코드의 모든 가져오기각 번들로 묶여 각 페이지와 함께 제공됩니다. 결과적으로, 불필요한 코드가 페이지에 로드되지 않게 됩니다.

`4. 설정이 필요없음`

- 넥스트는 기본적으로 웹팩과 바벨을 사용하고 있습니다. 이미 서버 사이드 렌더링 및 개발에 필요한 설정이 되어 있으므로 빠르게 개발을 시작할 수 있습니다.

- 사용하고 싶은 플러그인이 있다면 손쉽게 추가하여 사용할 수 있도록 지원을 하고 있습니다.

`5. 타입스크립트가 내장됨`

`6. 파일기반 내비게이션 기능`

- 리액트에서는 라우트를 위해서 'react-router'라는 라이브러리를 사용하여 라우팅 설정을 해주어야 합니다.

- 그로 인해 페이지의 경로에 대하여 직접 설정을 해주어야 하였습니다.

- 하지만 넥스트는 파일 시스템 기반 라우팅을 사용합니다.

- 폴더의 경로에 따라 페이지의 경로가 설정되어 구축이 빠르고 관리가 편리하다는 장점이 있습니다.

<br/>

### Next를 구성하는 기본 설정 파일에 대해서 알고 있나요

📁 pages 폴더 안에는 넥스트에서 중요한 역할을 하는 특별한 파일들이 있습니다.

- 📙_app.jsx (tsx)
- 📙_document.jsx (tsx)
- 📙_error.jsx (tsx)
- 📙404.jsx (tsx)

`📙_app.jsx`

App 컴포넌트는 모든 페이지의 공통 페이지 역할을 합니다.

App 컴포넌트를 이용하여 모든 페이지들을 초기화하여 다음과 같은 역할을 할 수 있습니다.

- 페이지들의 공통된 레이아웃
- 페이지를 탐색할 때 상태 유지
- 추가 데이터를 페이지에 주입
- 글로벌 CSS 추가

<details>

```jsx
📁 pages/_app.jsx

import Header from '../components/Header';

const MyApp = ({ Component, pageProps }) => {
  return (
    <>
      <Header />
      <Component {...pageProps} />
      <style jsx global>
        {`
          body {
            margin: 0;
          }
        `}
      </style>
    </>
  );
};

export default MyApp;

```

</details>

`📙_document.jsx`

사용자 정의 Document는 일반적으로 응용 프로그램 `<HTML>` 및 `<body>` 태그를 보강하는데 사용됩니다.

도큐먼트를 이용하여 `<title>`, `<description>`, `<meta>` 등 프로젝트의 정보를 제공하는 HTML 코드를 작성할 수 있고,

폰트나 외부 api, cdn 등을 불러오도록 할 수 있습니다.

또한 CSS-in-JS의 서버 사이드 렌더링을 위한 설정을 할 때 사용합니다.

Head 태그에 meta 태그를 추가하여 해당 프로젝트에 대한 정보를 추가할 수 있고, 구글 폰트 등에서 제공하는 폰트를 link 로 불러와 전역으로 적용시킬 수 있습니다.

<details>

```jsx
📁 pages/_document.jsx

import Document, { Html, Head, Main, NextScript } from 'next/document';

class MyDocument extends Document {
  render() {
    return (
      <Html lang="ko">
        <Head>
          <meta name="title" content="깃허브 레포지토리" />
          <meta name="description" content="깃허브 레퍼지토리 리스트입니다" />
          <link
            href="https://fonts.googleapis.com/css?family=Noto+Sans:400,700&display=swap"
            rel="stylesheet"
          />
          <link
            href="https://fonts.googleapis.com/css?family=Noto+Sans+KR:400,700&display=swap&subset=korean"
            rel="stylesheet"
          />
        </Head>
        <body>
          <Main />
          <NextScript />
        </body>
      </Html>
    );
  }
}

export default MyDocument;

```

</details>

`📙_error.jsx`

넥스트에서는 빌드 된 프로덕션 환경에서 에러가 발생한다면 에러 페이지로 넘어가게 됩니다.

따로 라우팅 경로를 설정하지 않더라도, 빌드 된 프로덕트 환경에서 에러가 발생한다면 에러 페이지로 자동적으로 넘어갑니다.

추가적으로 에러 상황에 따라서 500, 404 등도 추가할 수 있습니다

<details>

```jsx
📁 pages/_error.jsx

const Error = () => {
  return (
    <div>
      <p>에러가 발생했습니다</p>
    </div>
  );
};

export default Error;

```

</details>

<br/>

### 사전 렌더링을 위해 사용해 본 함수가 있나요

[참고자료](https://velog.io/@devstone/Next.js-100-%ED%99%9C%EC%9A%A9%ED%95%98%EA%B8%B0-feat.-initialProps-webpack-storybook)

- getInitialProps
- getStaticProps
- getStaticPath
- getServerSideProps

`getInitialProps`

Next 9.3 버전 이전엔 getInitialProps만으로 사전 렌더링 관련 문제를 전부 해결했지만, 9.3버전부터는 getInitialProps가 3가지로 분리되었습니다

- getStaticProps
- getStaticPath
- getServerSideProps

`getStaticProps`

- 빌드시 고정되는 값으로 빌드 이후에는 수정이 불가능합니다
- data를 빌드 시에 미리 땡겨와 정적으로(static 하게) 제공합니다
- 매 유저의 요청마다 fetch할 필요가 없는 데이터를 가진 페이지를 렌더링할 때 유리합니다
- 유저에 구애받지 않고 퍼블릭하게 캐시할 수 있는 데이터
- SEO 등의 이슈로 인해 빠르게 미리 렌더링해야만 하는 페이지

`getStaticPath`

- 동적 라우팅 + getStaticProps를 원할 때 사용
- 정의하지 않은 하위 경로는 접근해도 화면이 뜨지 않는다 (error 페이지로 라우팅)
- 동적 라우팅 시, 라우팅되는 경우의 수를 하나하나 넣어야 합니다

`getServerSideProps`

- 빌드와 상관없이, 매 페이지 요청마다 데이터를 서버로부터 가져옵니다

## Suspense

[참고, 리액트 코리아 - suspense](https://ko.reactjs.org/docs/concurrent-mode-suspense.html#what-is-suspense-exactly)

- `suspense가 뭔가요?`

suspense는 데이터 불러오기를 위한 라이브러리가 아닙니다.

suspense는 '**컴포넌트가 읽어들이고 있는 데이터가 아직 준비되지 않았다**'고 React에 알려줄 수 있는, **데이터 불러오기 라이브러리에서 사용할 수 있는 메커니즘** 입니다.

이후에 React는 데이터가 준비되기를 기다렸다가 UI를 갱신할 수 있습니다.

장기적인 관점으로는, **Suspense가 데이터 출처와 상관없이 컴포넌트로부터 비동기 데이터를 읽는 데에 사용되는 주된 방식으로 거듭나길** 바라고 있습니다.

<details>
<summary>예시 코드 보기</summary>

```jsx
const resource = fetchProfileData();

function ProfilePage() {
  return (
    <Suspense fallback={<h1>Loading profile...</h1>}>
      <ProfileDetails />
      <Suspense fallback={<h1>Loading posts...</h1>}>
        <ProfileTimeline />
      </Suspense>
    </Suspense>
  );
}

function ProfileDetails() {
  // 아직 로딩이 완료되지 않았더라도, 사용자 정보 읽기를 시도합니다
  const user = resource.user.read();
  return <h1>{user.name}</h1>;
}

function ProfileTimeline() {
  // 아직 로딩이 완료되지 않았더라도, 게시글 읽기를 시도합니다
  const posts = resource.posts.read();
  return (
    <ul>
      {posts.map((post) => (
        <li key={post.id}>{post.text}</li>
      ))}
    </ul>
  );
}
```

</details>

- `suspense로 가능한 것은 어떤 것들이 있나요?`

1. 데이터 불러오기 라이브러리들(axios, SWR, react-query)이 React와 깊게 결합할 수 있도록 해줍니다

2. 의도적으로 설계된 로딩 상태를 조정할 수 있도록 해줍니다. suspense는 데이터가 어떻게 불러져야 하는지를 정하지 않고, 앱의 시각적인 로딩 단계를 밀접하게 통제할 수 있도록 해줍니다

3. 경쟁 상태(Race Condition)를 피할 수 있도록 돕습니다. await를 사용하더라도 비동기 코드는 종종 오류가 발생하기 쉽습니다. suspense를 사용하면 데이터를 동기적으로 읽어오는 것처럼 느껴지게 해줍니다.
