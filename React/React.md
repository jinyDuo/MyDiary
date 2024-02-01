리엑트란?

메타(구페이스북에서) 만든 자바스크립트 라이브러리

리엑트 엘리먼트 생성과정

- 붕어빵틀(컴포넌트)

⇒ 붕어빵이 만들어지는과정(엘리먼트생성-랜더링)

⇒ 붕어빵완성 - 엘리먼트생성완료

완성된 붕어빵은 변경할 수 없다.

변경을 원하면 새로운 붕어빵을 만들어야함(신규 엘리먼트를 다시생성)

- 리엑트는 이 신규엘리먼트를 기존 엘리먼트와 바꿔치기함.

컴포넌트

- 역할 : 어떠한속성들을 입력으로 받아서 그에 맞는 리액트 엘리먼트를 생성하여 리턴해주는것.
- 엘리먼트 생성과정은 붕어빵 굽는 과정과 비슷
- 컴포넌트이름의 시작은 “대문자”로 시작해야함
    - 대문자로 시작하지않으면 엘리먼트로인식
        
        `ex) const element = <div />; - html 태그로인식`
        
        `ex) const eleement = <Welcome name=”인제" />;`
        

props

- 붕어빵틀에들어갈 재료
- 컴포넌트에 들어갈 입력값
- 같은 porps에 대해서는 항상 같은 결과를 보여줘야함.

state 

- 사용이유 : html 에서 일반변수 데이터는 변경되지않고 state로 사용하면 재랜더링되며 변경됨
- 리액트 컴포넌트의 변경 가능한데이터
- 렌더링과 데이터 흐름에 사용되는값만 state에 포함
- state변경함수 특징
    - … 문법 새 state로변경해주세요.
    - state 수정시에는 원본데이터를 유지한상태에서 카피데이터 생성(shallow copy) 후 사용

생명주기

Mounting(출생) → updating(인생) → unmounting(사망) - 상위 컴포넌트에서 현재 컴포넌트를 더 이상 화면에 표시하지 않게 될 때 언마운트된다.

componentDidMount → componentDidUpdate → componentWillUnmount

Hook

- 최상위레벨에서만 호출
- 반복문이나 조건문 또는 중첩된 함수들 안에서 훅을 호출하면 안됨
- 훅은 컴포넌트가 렌더링 될때마다 매번 같은 순서로 호출되어야함.

useState

- 클래스 컴포넌트에서는 setState 함수 하나를 사용해 모든 state값 변경가능
- useState는 변수각각에 대해 set함수가 따로 존재해서 사용해야변경가능

useEffect

- side effect를 수행하기위한 훅
- 리엑트에서 말하는 사이드이펙트는 단순효과 혹은 영향을 뜻하는 effect와 가깝다
    
    ex) 서버에서 데이터를 받아오거나 수동으로 DOM을 변경하는 작업 의미
    
- useEffect는 클래스 컴포넌트에서 제공해주는 함수인 compnentDidMount(), componentDidUpdate(), componentWillUnmount()와 동일한 기능을 하나로 통합해서 제공

useMemo

- 렌더링이 일어나는 동안 실행됨
- **데이터변경이나 수동 DOM 변경시에는 사용하면 안됨 X**

useCallback

- 콜백함수 순차적으로 실행하고싶을때 콜백함수를 사용함.
- 값이 아닌 함수를 반환함

useRef

- 특정 컴포넌트에 접근 할 수 있는 객체

redux

- 유선형으로 연결된 컴포넌트 구조를 특정 연관된 컴포넌트 state 변경
- 사용이유는 스토어에 저장하여 props 사용없이 state 값 각 상위컴포넌트부터 하위컴포넌트까지 직접전달가능함
- 리덕스를 사용하지않으면 상위부터 하위까지 순차적으로 state 전달해야함
- 연속된 props전달이없으므로 코드가 줄어듬.
- 스토어 데이터 변동데이터저장.
- **state변경된 하위컴포넌트에서는 한 특정 state값만 변경했을때 전체 재랜더링이아니라**
    
    **해당되는 그 하나의 컴포넌트의 state만 랜더링됨.**
    

redux - reducer

- 리덕스에 저장된 state가 변경하고싶다면 변경방법을 미리 정하여 정리해둠

redux - provider

- store에 있는 state를 어떤컴포넌트에 제공할것인가를 정하는울타리

redux - dispatch

- 컴포넌트에서 state 수정요청을하려고할때 사용하는 함수(state 변경)

redux - useSelector

- store에 저장된 state를 가져다 사용가능함
- arrow function으로 지정 ⇒
    
    ex) useSelector((state) ⇒ state.number) 
    

redux-thunk

- 동기 - reducers
- 비동 - extraReducers
- createAsyncThunk는 비동기함수를 처리하는 action을 만들어준다.
- 비동기작업 처리 위해사용
    - 비동기 작업시 3가지 상태
    
    1) asyncUpFetch.pending
    
    - 비동기작업 시작시 상태
    
    2) asyncUpFetch.fulfiled
    
    - 비동기작업 종료되었을때(데이터 response 받았을때)
    
    3) asyncUpFetch.rejected
    
    - 오류가 났을때

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/8dad2c69-2090-49a5-8fe5-a9e26630dffa/Untitled.png)

redux - thunk

- 비동기 작업처리 위해사용

react-query

- 단점 : api 요청코드가 훅 그리고 소스에 분산되어있어서 관리가 불편함
