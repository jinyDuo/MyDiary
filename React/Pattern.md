<h1>React design Pattern</h1>
CCP - Container

1. Container-Component Pattern
-> 컨테이너 컴포넌트와 프레젠테이션 컴포넌트를 분리하여 복잡한 로직을 처리하고 가독성을 높입니다. </br>

HOC - Higher

2. Higher-Order Component (HOC) Pattern
-> 컴포넌트를 함수로 감싸 새로운 기능을 추가합니다. 코드 재사용성을 높이고 데코레이터 패턴과 유사합니다.

RPP - Render

3. Render Prop Pattern
-> 컴포넌트 내부에서 렌더링을 담당하는 함수를 props로 전달하여 재사용성을 높입니다. 컴포넌트 구조가 단순해지고, 다양한 상황에서 유연하게 대응할 수 있습니다.

CCP - Compound

4. Compound Component Pattern
-> 여러 개의 컴포넌트를 하나의 논리적인 그룹으로 묶어 캡슐화합니다. 다른 컴포넌트와 결합하여 사용하므로 다양한 상황에 적용할 수 있습니다.

CCP - Controlled

5. Controlled Components Pattern
->  상태를 외부에서 관리하도록 하여 입력 폼 등의 상태를 다룹니다. 이를 통해 상태 관리가 용이하고, 보안상의 이유로 민감한 정보를 보호할 수 있습니다.
