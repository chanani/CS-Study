# Checked Exception과 Unchecked Exception

Checked Exception은 `컴파일 시점`에 확인되며, 반드시 처리해야하는 예외입니다.
자바에서는 `IOException`, `SQLException` 등이 이에 속합니다.
Checked Exception을 유발하는 메서드를 호출하는 경우, 메서드 시그니처에 
`throws`를 사용하여 호출자에게 예외를 위임하거나 메서드 내에서 `try-catch`를 사용하여 해당 예외를 반드시 처리해야합니다.

Unchecked Exception은 `런타임 시점`에 발생하는 예외로, 컴파일러가 처리 여부를 강제하지 않습니다.
자바에서는 `RuntimeException을` 상속한 예외들이 해당됩니다.
일반적으로 프로그래서의 실수나 코드 오류로 인해 발생합니다.


## 그럼 언제 사용해야 할까요 ? 🧐
Checked Exception은 외부 환경과의 상호작용에서 발생할 가능성이 높은 예외에 적합합니다. 
예를 들어, 파일 입출력, 네트워크 통신 등에서 발생할 수 있는 예외는 Checked Exception으로 처리하는 것이 좋습니다. 
이러한 예외는 예측 가능하며, 호출하는 쪽에서 적절히 처리할 수 있는 여지가 있습니다.

Uncheked Exception은 코드 오류, 논리적 결함 등 프로그래머의 실수로 인해 발생할 수 있는 예외에 적합합니다. 
예를 들어, null 참조 또는 잘못된 인덱스 접근 등은 호출자가 미리 예측하거나 처리할 수 없기 때문에 Unchecked Exception으로 두는 것이 좋습니다.

## 면접 질문 답변 정리 😋

### Q: Checked Exception과 Unchecked Exception의 차이점을 설명해주세요.

첫 번째, 확인 시점의 차이입니다.
Checked Exception은 컴파일 시점에 확인되며, 컴파일러가 반드시 처리하도록 강제합니다.
반면 Unchecked Exception은 런타임 시점에 발생하며, 컴파일러가 처리를 강제하지 않습니다.

두 번째, 처리 방법의 차이입니다.
Checked Exception은 throws 키워드로 호출자에게 예외를 위임하거나, try-catch 블록으로 반드시 처리해야 합니다. 
그렇지 않으면 컴파일 에러가 발생합니다. 하지만 Unchecked Exception은 처리하지 않아도 컴파일이 가능합니다.

세 번째, 상속 관계의 차이입니다.
Checked Exception은 Exception 클래스를 직접 상속받습니다. 
반면 Unchecked Exception은 RuntimeException을 상속받습니다.