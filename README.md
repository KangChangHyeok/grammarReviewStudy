# 앨런 문법 복습 스터디
> 앨런 문법 복습 스터디  https://www.notion.so/2022-323691abb89a46138820c4f740c1a085

## 11월 10일 ~ 12월 2일(문법 복습)

### 진행방식
-  주당 앨런 강의 7-8파트씩 진행 (강의 27파트 + CS101 두 파트 = 총 29파트를 4주로 나눈 내용)
-   개인별로 1-2파트씩 담당해 파트당 3문제 만들어 공유
-   모집 인원별 담당 파트 수 변동 가능
-   본인이 맡은 파트의 중요도에 따라 문제 수 조정 가능
-   문제는 앨런의 주차저녁세션 테스트 중 문법 서술형 방식 (코드구현 x)  

### 진행내용
<details>
<summary>1주차(11월 10일)</summary>

## Kyle(나)
<details>
<summary> swift 메모리 구조의 코드, 데이터, 힙, 스택에 대해 각각 설명하시오. </summary>

#### 코드 
프로젝트에서 우리가 작성하는 소스 코드가 기계어 형태로 저장.  
컴파일 타임에 저장되고, 중간에 코드가 변경되지 않도록 Read-Only 형태로 저장.
#### 데이터 
전역변수, static 변수가 저장된다. 프로그램 시작과 동시에 할당되고, 프로그램 종료시 메모리에서 해제된다.  
실행 도중 변수 값이 변경될 수 있으니 Read-Write로 지정된다.
#### 힙 
프로그래머가 할당/해제 하는 메모리 영역 사용하고 난 후 반드시 메모리 해제 필수! -> 안할 경우 메모리 누수가 발생.
#### 스택 
함수 호출 시 함수의 지역변수, 매개변수, 리턴 값 등등이 저장되고, 함수 종료시 저장된 메모리도 해제.
</details>
<details>
<summary> swift의 기본 데이터 타입에 대해 설명하시오. (Int, Float/Double, String/Character, Float/Double) </summary>

모든 데이터 타입의 이름은 첫 글자를 대문자로 입력한다. 또한 Struct를 기반으로 구현되어 있다.
#### Int(정수형 데이터 타입) 
정수 타입, 현재는 기본적으로 64비트 정수형.
#### Float / Double(실수형 데이터 타입) 
##### Float
실수 타입/ 부동 소수 타입  
소수점 표현 가능(6자리까지) / 4바이트 
##### Double
실수 타입(Float 타입에 비해 2배의 공간)  
소수점 표현 가능(15자리까지)
#### String / Charater (문자형 데이터 타입) 
##### String
문자열을 저장, 큰따옴표("")사용 
##### Charater
문자(한글자)를 저장, 큰따옴표("")사용
#### Bool(참과 거짓을 다루는 데이터 타입)
true 또는 false를 저장.  
프로그래밍의 다양한 상황에서 사용
</details>
<details>
<summary> swift의 타입 관련 기본 문법 3가지에 대해 설명하시오(타입 주석, 타입 추론, 타입 안전성) </summary>

#### 타입 주석
변수를 선언하면서, 타입도 명확하게 지정하는 방식
#### 타입 추론
타입을 지정하지 않아도, 컴파일러가 타입을 유추해 저장하는 방식
#### 타입 안정성
스위프트는 데이터 타입을 명확하게 구분하여 사용한다.
</details>

## Jess

<details>
<summary> if문과 switch문의 차이점을 비교하고, 특징을 간단히 서술하세요.</summary>

- if문 
  - 조건 2개도 사용 가능, 응용 범위가 넓습니다. 즉 모든 조건에 대한 처리가 가능합니다.
- switch문 
	- if문보다 가독성이 좋습니다. 실제 앱 등의 분기처리에 많이 사용합니다.
</details>
<details>
<summary>swift에서 switch구문의 case를 연속 실행하려면 어떤 키워드를 사용해야 하고, 예시를 간단히 서술하세요.</summary>

**fallthough 키워드를 사용합니다**
```swift
switch 입력 값 { 
case 비교 값 1: 
     	실행구문 
case 비교 값 2: 
       	fallthrough 
case 비교값 3: 
       	실행구문 
default: 
      	실행구문 
}
```
</details>
<details>
<summary>튜플의 개념을 설명하고, 간단한 예시를 들어보세요.</summary>

튜플은 타입의 이름이 따로 지정되지 않은, 프로그래머 마음대로 만드는 타입입니다.  
ex) var person: (String, Int, Double) = (”Jess”, 123, 12.3)
</details>

## haha

<details>
<summary>inout은 언제 사용하면 좋을까요?</summary>

inout 파라미터를 사용하면 값 타입 변수가 저장된 주소의 값을 함수 안과 밖에서 동일하게 사용하게 됩니다.  
따라서 함수가 입력과 동일한 출력을 제공하고, 함수 내에서 적용된 변경사항이 함수 외부에서도 동일하게 적용되어야할 때 사용할 수 있습니다.  
Swap을 직접 구현하고자 한다면 inout이 좋은 선택이 될 수 있습니다.
```swift
func swap<T>(a: inout T, b: inout T) {
	(a, b) = (b, a)
}
var a = 0, b = 1
print(a, b) // 0 1
swap(a: &a, b: &b)
print(a, b) // 1 0
```
</details>
<details>
<summary>제어전송문 4가지를 각각 쓰이는 경우와 어떻게 사용되는지 간단하게 설명하세요.</summary>

- break
	- switch문에서 break - case에서 어떤 문장의 실행도 없을 때 입력하는 약속
	- 반복문(for/while)에서 break - (가장 가까운) 반복문을 완전히 종료
- fallthrough
	- switch문에서 어떤 해당 case를 해당한 후, 다음 case의 해당 여부를 따지지 않고, 다음 case 내부의 문장을 실행
- continue
	- 반복문에서 (가장 가까운) 반복의 이번 주기를 끝내고 다음 주기로 바로 넘어가서, 다음 주기를 실행
- return
	- 리턴 타입이 있는 함수
		- 임시값을 저장할 메모리 공간을 생성한다.
		- 해당 임시값을 반환하고 스택 영역에서 함수의 스택 프레임을 해제시킨다.
		- 함수의 결과를 값으로 가진다.
	- 리턴 타입이 없는 함수
		- 임시값을 저장하는 메모리 공간이 따로 없다.
		- 함수의 실행을 중단 시킨다. 그 즉시, 스택 영역에서 함수의 스택 프레임을 해제시킨다.
		- 함수의 결과로 값을 가지지 않고 단순히 동작만 수행
</details>
<details>
<summary>1..<3은 어떻게 for in 순환문으로 반복 순회가 가능할까요?</summary>

1..<3은 범위를 나타내는 Range 객체입니다.
Generic으로 구현되어 다양한 타입의 범위를 표현할 수 있게 [lowerBound, upperBound) 방식으로 표현됩니다.  
Range의 내부 코드를 살펴보면 Range는 Sequence protocol을 채택하고 있습니다.  
```swift
extension Range: Sequence
		where Bound: Strideable, Bound.Stride: SignedInteger {
  public typealias Element = Bound
  public typealias Iterator = IndexingIterator<Range<Bound>>
}
```
Sequence 프로토콜에 부합하는 타입은 for…in 순환문으로 반복 순회할 수 있습니다. 내부적으로는
```swift
public protocol Sequence {
    associatedtype Iterator: IteratorProtocol
    public func makeIterator() -> Self.Iterator
}
```
이렇게 구현되어 있는데 런타임시에 for in 순환문을 돌면서 makeIterator() 메소드가 자동으로 호출됩니다.  
Iterator는 는 IteratorProtocol 에 부합하는 범용 타입으로 IteratorProtocol 의 목적은 컬렉션을 반복 순회하는 next() 메소드를 통해 컬렉션의 반복 상태를 캡슐화 하는 것입니다.  
그렇기 때문에 for in 순환문을 통해서 makeIterator() 메소드가 자동으로 호출되고 Iterator를 반환하는 것입니다.  
Iterator 에는 next()라는 메소드가 있는데 Sequence에 있는 다음 요소를 반환하거나, Sequence의 마지막인 경우 nil 을 반환합니다.  
아마 for in 순환문 내부적으로 이러한 처리가 되어있을 거라 생각됩니다. 그래서 반복 순회가 가능하다고 생각합니다.
</details>

## John
<details>
<summary>swift에서 nil이란? 다른 언어의 null과 차이점은?</summary>

다른 언어의 null은 보통 실제로 값이 없는 것   
스위프트에서 nil은 실제 값이 없다기보다, 값이 없음을 ‘표현’하기 위해 임시적으로 감싸진 키워드.  
#### 값이 없는 것과 값이 없음을 표현하는 것은 어떻게 다른가?
메모리 구조의 차이로 보면 이해 가능.  
#### 스위프트의 옵셔널
즉, 스위프트의 옵셔널은 값이 있는 케이스와 값이 없는 케이스를 감싸는 enum.  
enum 안 case 각각은 .some →optional(값), .none→nil로 나누어진다.  
즉 nil의 메모리에는 enum case 중 .none이 있다.  
옵셔널 타입의 변수 등에 값이 없을 경우 자동으로 nil이 할당된다.  
실제 값이 없는 경우는 nil을 벗겨야 함. (null 과 같은 키워드는 따로 없음)
</details>
<details>
<summary>딕셔너리의 키 값은 중복이 불가하고 Hashable 해야 한다. 여기서 Hashable이란 무엇인가?</summary>

유일성을 보장하는 것.  
기본적으로 Hash함수에 input으로 쓰일 수 있는 타입을 Hashable 하다고 한다.  
#### 해시 함수란?
어떤 숫자나 글자를 input으로 사용하면, 고정된 길이의 숫자나 글자이면서 유일한 값으로 output을 반환해 준다.  
해셔블한 타입은 값의 유일성을 보장하고, 검색 속도가 빠르다.(시간 복잡도 O(1)).  
스위프트의 기본 타입은 모두 Hashable.
#### 해시 함수 추가 설명
```
똑같은 값이 올 때마다 똑같이 분류되어야 하는 규칙성으로 값을 변환한다.
비밀번호 보안 시스템을 생각하면 이해 도움. 
우리가 비밀번호를 입력하면, 그 값 그대로를 오픈하지 않고 해쉬함수를 사용해 해쉬값으로 반환해서 이용한다. 
이렇게 바뀐 해쉬값(아웃풋)은 다시 해당 글자에 대해 유일하고, 대신 반대 방향으로(해쉬값인 아웃풋에서 우리가 입력한 인풋으로) 전환이 불가능하다. 
즉 암호화가 된 것. 해셔블이란 해쉬 함수의 인풋으로 사용될 수 있는 값을 의미한다. 
해쉬 함수란 유일한 값에 대응되는 것으로, 대표적으로 비밀번호를 받을 때 우리의 비밀번호 리터럴 값은 해셔블하게 저장된다. 
이렇게 해셔블한 값은 유일하기에 검색속도가 기존 O(n)에 비해 O1로 빠르다.
```
</details>
<details>
<summary>array, dictionary, set의 문서에 공통적으로 등장하는 sequence는 어떤 개념인가?</summary>

- 차례를 만들어주는 프로토콜 타입
- 딕셔너리나 셋은 순서가 없다고 했지만, 그럼에도 for 구문이나 .contains 등의 메서드를 사용하기 위해선 전체를 반복해서 순환할 필요가 있다.
- 스위프트 컬렉션 타입은 이러한 검색을 가능하게 하는 프로토콜을 자동으로 채택하고 있다.  
이러한 컬렉션 타입이 시퀀스 프로토콜을 채택하고 있다는 것은 차례가 있다는 의미이다.  
물론 딕셔너리나 셋은 순서가 없지만, for 문 등의 검색을 위해선 전체를 순회할 필요가 있기 때문에 차례가 존재한다.  
array, set의 .contains 메서드 등이 이러한 시퀀스 프로토콜을 이용해 실행된다.
</details>

## Review
**array, dictionary, set의 문서에 공통적으로 등장하는 sequence는 어떤 개념인가?**  
해당 질문에 대해 제대로 답하지 못했음. 다시 공부하고 해당내용 정리하기.  

**몸에 체화되어 확실하게 정리하도록 할것**  
실제로 문제를 풀어보니 머리로 알고있는 것과 실제로 내가 작성하는것과는 정말 달랐음.  
확실하게 내용을 정리해서 면접때 확실하게 답변할 수 있도록 준비하기	

</details>
<details>
<summary>2주차(11월 18일)</summary>

## Kyle(나)
<details>
<summary>클래스와 구조체에서 초기화의 의미에 대해 간단히 서술하시오.</summary>

초기화란 생성자 메서드를 실행하여 클래스나 구조체의 모든 저장 속성의 값 설정을 완료하고, 인스턴스를 생성하는것을 말한다.
</details>
<details>
<summary>클래스와 구조체의 메모리 저장 방식에 따른 차이점을 서술하시오.</summary>

- 구조체
    1. 값 형식
    2. 인스턴스 데이터를 모두 스택에 저장한다.
    3. 값을 전달할때 마다 복사본을 생성하여 전달한다.(다른 메모리 공간을 생성)
    4. 스택에 저장되고, 스택 프레임 종료시 메모리에서 자동 제거
- 클래스
    1. 참조 형식
    2. 인스턴스 데이터가 힙에 저장, 해당 힙을 가르키는 변수를 스택에 저장하고 메모리 주소값이 힙을 가르킨다.
    3. 값 전달시 저장된 주소를 전달한다.
    4. ARC를 통해 메모리를 관리한다.
</details>
<details>
<summary>객체지향의 4대 특징에 대해 간단하게 서술하시오</summary>

- 추상화  
실체들의 공통적 특성을 뽑아내서 클래스로 정의하는 것을 말한다.  
- 캡슐화  
연관이 있는 속성과 메서드를 하나의 클래스로 묶어서 활용한다는 개념
	- 은닉화: 캡슐화를 하면 접근제어자를 통해 객체 외부에서 내부 데이터의 접근 통제가 가능해짐.

- 상속성  
부모클래스의 속성과 메서드를 자식클래스에서 그대로 물려받는 개념.  
상속을 활용해 코드가 재활용되기 때문에 생산성이 높아짐  
클래스가 타른 타입과 구별되는 결정적인 이유
- 다형성  
하나의 객체가 여러가지 타입의 형태로 저장 가능하다.  
하나의 객체는 다양한 방식으로 동작 가능하다.
</details>

## John
<details>
<summary>저장 속성과 계산 속성의 차이를, 계산 속성을 사용하는 이유를 통해 설명하시오.</summary>

저장속성은 인스턴스 내에 실제 데이터 값을 저장할 수 있는 데이터 저장공간이며,  
계산속성은 속성의 형태를 가진 실질적인 메서드입니다. 실제 데이터 값은 없습니다.

계산 속성을 사용하는 이유는 메서드가 프로퍼티가 훨씬 더 간편하고 직관적이기 때문입니다.  
인스턴스 외부에서 메서드를 통해 내부 값에 접근하려면 메서드를 두 개 구현해야 하기 때문에 코드의 가독성이 나빠집니다.
</details>
<details>
<summary>타입 속성의 뜻과 그 키워드인 static과 class의 차이는?</summary>

각각의 인스턴스가 아닌 타입 자체에 속하는 프로퍼티를 뜻합니다.  
static은 상속해서 재정의가 불가하고, class는 상속해서 재정의가 가능합니다. 
</details>
<details>
<summary>클래스를 상속받았을 때, 저장 프로퍼티는 재정의가 불가한데 계산 프로퍼티는 재정의가 가능한 이유는?</summary>

데이터 영역에서 프로퍼티는 상위 클래스의 메모리 구조에 관여할 수 없으므로 재정의가 불가합니다.  
그러나 계산 프로퍼티는 메모리 구조의 프로퍼티를 수정하는 것이 아닌, 기능을 추가하는 방식이기 때문에 재정의가 가능합니다.
</details>
<details>
<summary>String은 왜 subscript로 접근이 안되는지 설명하시오.</summary>

String.index로 접근해야 한다. String의 유니코드 크기가 가변적이기 때문이다.
</details>
## Haha
<details>
<summary>Class 타입의 초기화 위임 규칙에 대해 설명해주세요.</summary>

1. 자식 클래스의 지정 생성자는 부모클래스의 지정생성자를 반드시 호출하여야 합니다.
2. 편의생성자는 자신을 정의한 클래스의 다른 생성자를 반드시 호출하여야 합니다.
3. 편의생성자는 지정생성자를 반드시 호출하여야 합니다.
</details>
<details>
<summary>required 키워드에 대해서 설명해보세요.</summary>

클래스의 생성자 앞에 required 키워드를 붙이면 하위 클래스에서 반드시 해당 생성자를 구현해야합니다.  
다른 지정 생성자를 구현하지 않으면 자동으로 필수 생성자가 상속됩니다. 
</details>
<details>
<summary>init?()은 어떤 특징을 가지고 있고, init()과 어떤 차이가 있나요?</summary>

init?()은 인스턴스 생성 시 실패가능성을 가진 생성자입니다.  
실패가 불가능하게 만들어서 아예 에러가 나고 앱이 완전히 꺼지는 가능성보다는 실패가능 생성자를 정의하고,  
그에 맞는 예외 처리를 하는 것이 더 올바른 방법입니다.  
인스턴스 생성 실패 시 nil을 리턴합니다. 또한, init?()은 재정의가 불가합니다.
</details>
## Jess
<details>
<summary>Any와 AnyObject에 대하여 간단히 서술하세요.</summary>
특정 타입을 지정하지 않고 여러 타입의 값을 할당할 수 있는 타입입니다.  
타입 캐스팅을 수행할 때 일반적으로 상속 관계에 있는 클래스끼리만 캐스팅이 가능하지만,  
이를 사용할 경우 상속 관계에 있지 않아도 타입 캐스팅을 할 수 있습니다.  
**Any**는 함수 타입을 포함한 모든 타입을 뜻하고, **AnyObjects**는 클래스 타입만을 뜻합니다.
</details>
<details>
<summary>확장의 개념과 유의점, 사용하고자 하는 경우 등을 간단하게 서술하세요.</summary>

클래스나 구조체, 열거형 등의 객체에 새로운 기능을 추가하여 확장해주는 구문입니다.  
메서드를 추가하는 것만 가능하며, 저장 속성은 추가할 수 없습니다.  
클래스에서 생성자를 구현하려는 경우, 편의생성자 형태만 추가 가능합니다.  
확장은 외부에서 가져온 타입에 내가 원하는 기능을 추가하고자 할 때 사용합니다.  
따라서 따로 상속을 받지 않아도 되며, 구조체와 열거형에도 기능을 추가할 수 있으므로 매우 편리합니다.
</details>
<details>
<summary>클래스의 상속과 확장의 차이점을 간단히 서술하세요.</summary>

클래스나 구조체, 열거형 등의 객체에 새로운 기능을 추가하여 확장해주는 구문입니다.  
클래스의 상속은 특정 타입을 물려받아 하나의 새로운 타입을 정의하고,  
추가 기능을 구현하는 수직확장의 형태입니다.  
반면 확장은 기존의 타입에 기능을 추가하는 수평확장의 형태입니다.  
상속을 받으면 기존 기능을 재정의할 수 있지만, 확장은 재정의 할 수 없습니다. 
</details>

## Review
John이 말해준 **WMO 키워드** 찾아서 보고 공부해서 2주차 Review 파일에 정리하기.  
**class의 성능을 향상 시킬수 있는 방법**에 대해 공부하기.  
</details>
<details>
<summary>3주차(11월 25일)</summary>

## John
<details>
<summary>프로토콜이란 무엇이며, 프로토콜을 사용하는 이유는 무엇인가?</summary>

프로토콜은 일종의 규약을 채택하는 것과 같다. 흔히 자격증을 채택하는 것으로 많이 비교한다.  
프로토콜 지향 프로그래밍은 스위프트의 큰 언어적 특징 중 하나인데, 객체지향 프로그래밍의 단점을 보완할 수 있다.  
객체지향 프로그래밍을 클래스로 대표해서 말해보면, **세 가지 단점**을 들 수 있다.  

1. 우선 클래스에서만 상속이 가능.  
2. 하나의 클래스만 상속(다중 상속 지원 x)
3. 상속시 필수적으로 상위 메모리 구조를 따라가기 때문에 불필요한 메서드와 프로퍼티를 강제적으로 갖게 된다.  

반면, **프로토콜**은 값타입에서도 사용 가능하며, 여러개의 프로토콜을 채택 가능하고,  
객체를 생성하지 않기 때문에 메모리와 상관이 없다.  
또한 추가적으로, 애플의 기본 데이터타입에도 사용 가능하고, 타입으로도 사용 가능하다.
</details>
<details>
<summary>스위프트가 프로토콜을 일급 객체로 취급한다는 것은 무슨 의미인가?</summary>
일급 객체로 사용 가능하다는 말은, 하나의 타입으로 사용 가능하다는 뜻이다.  
즉, **변수에 할당**할 수 있고, **메서드의 파라미터로 전달받거나 리턴값으로 반환**할 수 있다.
</details>
<details>
<summary>mutating 키워드가 무엇인지와 그 원리를 설명하세요.</summary>

값 타입인 구조체가 프로토콜을 채택하고 그 메서드가 변수를 사용할 때 mutating 키워드가 필요하다.
</details>
## Jess
<details>
<summary>Method Dispatch가 무엇인가요? 또한,  Method Dispatch의 대표적인 두가지 타입의 특징을 간략히 설명하세요.</summary>

현재 메모리에서 어떻게 각 메서드를 실행시키고, 어떠한 메서드를 구현해야하는지를 결정하는 것입니다.  
두 가지의 타입으로 나뉘는데, **정적 디스패치(Static Dispatch)**와 **동적 디스패치 (Dynamic Dispatch)**로 나뉩니다.  
**정적 디스패치**는 컴파일 타임에 어떤 메서드를 실행할 지 주소값을 알고 있기 때문에 함수의 메모리 주소로 바로 이동합니다.  
이는 성능을 향상시키고 컴파일러가 최적화를 가능하게 합니다.  
**동적 디스패치**는 참조 타입에서만 지원합니다. 정적 디스패치에 비하여 오버헤드가 더 들지만, OOP의 언어들은 다형성을 위하여 동적 디스패치를 지원합니다. (하나의 객체가 다양한 방식으로 동작 가능할 수 있도록) 
</details>
<details>
<summary>중첩타입이 무엇인지, 어떻게 사용하는지 간략히 설명하세요.</summary>

swift에서는 타입 내부에 타입을 정의하고 구현할 수 있는데, 이것을 중첩타입이라고 합니다.  
타입 내부에 새로운 타입을 정의하고 싶다면 자신의 정의 내부에 새로운 타입을 정의하고 구현해주면 됩니다.  
중첩타입을 참조하려면 자신이 속해있는 타입의 이름을 자신보다 앞에 적어주어야 합니다.  
ex) Person 클래스 내부에 정의한 Job 타입을 나타낼 때 Person.Job 이라고 표현
</details>
<details>
<summary>self와 Self의 차이를 설명하세요.</summary>

**Self** - 프로토콜을 준수하는 타입  
**self** - 해당 타입의 내부의 값
</details>
## Kyle
<details>
<summary>클로저의 캡처현상에 대해 간단히 설명하시오</summary>

클로저는 클로저의 주기동안 사용이 필요 없어질때까지 힙의 영역에 존재해야 하고, 클로저 내부에서 외부에 존재하는 변수를 계속 사용해야 하기 때문에 캡처 현상이 발생한다.
</details>
<details>
<summary>강한 참조 사이클에 대해 설명해주세요</summary>

두 인스턴스가 서로를 참조할 경우 강한 참조 사이클이 발생하고, 인스턴스가 메모리에서 정상적으로 헤제되지 않는 것을 의미한다.
</details>
## Haha
<details>
<summary>고차함수 중 flatMap과 compactMap의 차이를 설명해보세요.</summary>

- `compactMap`은 1차원 배열에서 각 요소에 대해 `nil을 제거`하고 `옵셔널 바인딩`을 한 결과를 배열로 만들어 반환합니다.
- `flatMap`은 배열의 요소 타입이 옵셔널이라면, `nil을 제거`하고 `옵셔널 바인딩`을 한 결과를 배열로 만들어 반환합니다.
- `flatMap`은 2차원 배열이면서 요소 타입이 옵셔널이 아니라면, 배열의 요소들을 `1차원으로 합친 배열`을 반환하고 nil의 제거와 옵셔널 바인딩은 하지 않습니다.
</details>
<details>
<summary>함수형 프로그래밍은 무엇인가요? Swift는 함수형 프로그래밍 언어인가요?</summary>

- 함수형 프로그램밍은 `순수 함수`를 기반으로 하는 프로그래밍 패러다임입니다. 순수 함수는 어떤 입력에 대해 `항상 같은 출력`을 만드는 함수를 의미합니다. 즉, 외부에 영향을 주거나 받는 `side effect`가 없습니다.
- 스위프트는 함수형 프로그래밍 언어이면서 동시에 객체 지향 프로그램밍 언어의 특징인 상속, 은닉, 캡슈화, 추상화 등을 제공하는 멀티 패터다임 언어입니다.
</details>
<details>
<summary>High Order Function에 대해서 설명해보세요.</summary>

고차함수는 함수를 인자로 받거나 함수를 결과로 반환할 수 있는 함수입니다.
</details>

## Review
**추가로 공부해볼 내용: Delegate**  
* 델리게이트 패턴을 활용하는 경우의 예시.  
* Delegate와 Notification 방식의 차이점.  
* KVO 동작 방식.
</details>
<details>
<summary>4주차(12월 2일)</summary>

## Kyle
<details>
<summary>강한 참조 사이클에 대해 간단히 설명하시오.</summary>

두 가지 이상의 객체가 서로에 대한 강한 참조 상태를 가지고 있을때 발생하며,  
발생하게 될 경우 서로에 대한 참조가 해제되지 않아 메모리에서 유지되어 메모리 누수가 발생하게 된다.
</details>
<details>
<summary>강한 참조 사이클로 인한 메모리 누수 해결방안인 weak, unowned 키워드의 차이점에 대해 설명하시오.</summary>

- **weak**  
가르키는 인스턴스가 메모리 해제될 경우 자동적으로 nil값을 할당받는다.
소유자에 비해 가르키는 인스턴스의 생명주기가 짧을때 주로 사용한다.

- **unowned**  
가르키는 인스턴스가 메모리 해제되어도 자동적으로 nil을 할당받지 못한다.
따라서 소유자에 비해 가르키는 인스턴스의 생명주기가 길때 주로 사용한다.
</details>
## Jess
<details>
<summary>defer란 무엇인지, 언제 사용하는지에 대하여 설명하세요.</summary>

작성된 위치와 상관없이 함수 종료 직전에 실행되는 구문입니다.  
함수를 종료하기 직전에 정리해야 하는 변수나 상수를 처리하는 용도입니다.
</details>
<details>
<summary>defer가 호출되는 순서는 어떻게 되고, defer가 호출되지 않는 경우를 설명하세요.</summary>

defer구분은 함수의 가장 마지막에 실행됩니다.  
하나의 함수에서 여러번 defer를 호출 가능하며, 실행 순서는 가장 마지막에 실행된 defer부터 역순입니다.  
중첩으로도 사용이 가능하며, 실행 순서는 가장 바깥쪽 defer부터 실행됩니다.  
defer가 호출되지 않는 경우는 defer를 읽기 전에 함수가 종료되는 경우입니다.  
throw를 이용해서 오류를 던져 함수가 종료될 경우, guard문을 사용하여 중간에 함수를 종료하는 경우 등이 있습니다.
</details>
<details>
<summary>generic이란 무엇인지,프로토콜에서의 generic 사용법에 대해 간단히 서술하세요.</summary>

타입(형식)에 관계없이 하나의 정의로 모든 타입을 처리할 수 있는 문법입니다.  
유지보수가 쉽고, 재사용성이 높은 함수,구조체,클래스,열거형 등을 일반화 가능한 코드로 작성할 수 있습니다.  generic이 없다면 타입마다 모든 경우를 다 정의해야 하기 때문에 유지보수 및 재사용성 관점에서 어렵습니다.  
프로토콜에서 generic을 사용하고 싶을 경우에는, 프로토콜 내부에 associatedtype을 쓰고, 프로토콜 내부에 사용할 범용 타입의 이름을 선언합니다.  
(메서드를 선언할 때에는 일반 제네릭처럼사용하는 것이 가능합니다.)
</details>
## John
<details>
<summary>Result 타입은 무엇인가요?</summary>

- 기존의 error타입에서 보다 진보된 형태.
- 함수 실행의 성공과 실패를 함께 담아 리턴하는 enum 타입.
- 에러가 발생할 시 따로 외부로 던지지 않고 enum case 내부에서 해결한다.
- 장점 :
    - 함수를 정의할 때 error타입을 명시적으로 선언할 수 있다.
    - error를 사용할 때 옵셔널바인딩이 불필요하다.
</details>
<details>
<summary>Result 타입을 활용할 수 있는 메서드 중 아는 것들을 간단하게 설명하세요.</summary>

- Result.get()은 성공을 throwing 한다.
- Result.map()은 성공을 원하는 조건으로 mapping해 반환한다.
- Result.failureMap()은 실패를 원하는 조건으로 mapping해 반환한다.
</details>
<details>
<summary>접근 제어의 5가지 종류는 무엇이 있나요?</summary>

- open : 다른 모듈에서 접근가능. 클래스에서 사용가능. 클래스의 가장 넓은 수준의 접근제어단계.
- public : 다른 모듈에서 접근가능. 구조체/열거형의 가장 넓은 수준의 접근제어단계. 기본 타입의 설정 수준. 상속/재정의 불가
- internal : 같은 모듈에서 접근가능. 기본 접근제어 설정.
    - 모듈: 프레임워크/라이브러리 등 import해서 사용하는 외부의 것
- fileprivate : 같은 파일 내에서 접근가능
- private : 같은 scope 내에서 접근가능
</details>
## Haha
<details>
<summary>Hashable 프로토콜에 대해서 설명해보세요.</summary>

- Hashable 프로토콜을 채택하는 타입은 모두 값을 `정수인 해시값`으로 표현할 수 있습니다.
- 스위프트의 기본 타입 중 `문자열, 정수, 실수, 불리언, 그리고 Set 콜렉션`이 Hashable 프로토콜을 채택하고 있습니다.
- Hashable 프로토콜을 채택하는 커스텀 타입의 `저장 프로퍼티가 모두` Hashable 프로토콜을 채택하고 있다면, 별다른 구현없이 Hashable 프로토콜을 채택하는 것 만으로 Hashable한 동작을 제공합니다.
- 그렇지 않다면 `==` 메서드를 만들고 hash(into:) 구현해서 해시값을 생성하는데 필요한 프로퍼티를 지정해주어야합니다.
</details>
<details>
<summary>Hashable 프로토콜을 채택하는 커스텀 타입이 Equtable도 채택해야하는 이유가 무엇인가요?</summary>

- 어떤 값에 대한 Hash 값은 고유하지만, Hash 값을 생성하는 built in 메소드인 hasher(_:) 가 서로 다른 값에 대해 동일한 Hash 값을 생성할 수 있기 때문입니다.
- 이런 경우를 해시 충돌이라고 하고, 해시 충돌이 발생하는 경우를 알기 위해서는 두 인스턴스가 값이 일치하는 확인해야하기 때문에 Equatable 프로토콜을 채택해야합니다.
</details>
## 전체범위 문제(중요 내용 복습)
<details>
<summary>함수형 프로그래밍 방식을 왜 고려해야 할까요?</summary>

- 함수형 프로그래밍
    - 기존 코드를 기반으로 생각하는 명령형 프로그래밍은 ‘어떻게 구현하는가’에 초점
    - 함수형 프로그래밍은 ‘무엇’을 활용할까의 관점.
        - 함수들을 조합해 결과를 만든다.
    - 장점
        - 사이드 이펙트를 방지한다.
        - 코드가 간결해진다.
- 사실 사이드 이펙트가 없다는 건 순수함수에 좀 더 가까운 설명.
- 함수형 프로그래밍의 장점은, 값-상태를 공유하지 않는다는 것. 동시성 문제를 보다 안전하게 해결할 수 있다.
</details>
<details>
<summary>swift에서 extension이 무엇인지, 어떻게 사용되는지 간단히 서술하세요.</summary>

**extension(확장)**은 클래스, 구조체, 열거형 타입에 새로운 메서드, 프로퍼티, 생성자를 추가적으로 정의해 사용하기 위해 사용.  
이 때 확장에는 저장 속성은 정의할 수 없으며, 계산 속성만 정의할 수 있습니다.  
소멸자의 경우에는 추가할 수 없고 생성자는 convenience init만 정의할 수 있습니다.  
구조체의 경우에는 확장에 생성자를 정의할 경우 멤버와이즈 이니셜라이저가 사라지지 않습니다. 
</details>
<details>
<summary>upcasting과 downcasting의 차이에 대해 설명하세요.</summary>

**upcasting**이란, 서로 상속 관계에 있는 클래스에서 자식 클래스를 부모 클래스로 타입캐스팅하는 것을 말합니다.  
as를 사용해서 업 케스팅할 수 있습니다. 컴파일이 되면 항상 성공합니다.  
**downcasting**은 반대로 부모클래스에서 자식클래스로 타입캐스팅하는 것입니다.  
이 역시 as를 사용하지만, 실패 가능성이 있기에 as? 나 as! 를 사용합니다.  
as! 는 실패하면 런타임 에러를 발생시키고, as? 는 nil을 반환합니다.  
</details>
<details>
<summary>dispatch queue의 serial queue에 대해 간단히 서술하세요.</summary>

serial queue, 즉 직렬 큐는 작업을 한번에 하나씩 처리하는 작업 큐 입니다.  
보통 순서가 중요한 작업을 처리할 때 사용합니다.  
스레드에 먼저 할당한 작업이 완전히 끝나야 큐에서 대기중인 작업을 스레드에 할당합니다. 
</details>
## Review
- 다음 스터디 계획 논의
</details>

## 12월 3일~ 12월 29일(iOS 면접내용 준비, 문법 복습)
### 진행방식
   - 메인1
       - 제르시 면접질문 정리 iOS의 질문 목록을 주차별로 나누기
       - 주차에 해당하는 질문들 공부
       - 스터디 시 해당 질문들 문제풀이
       - 문제풀이 후 각자 맡은 파트의 준비한 답변 공유 (필요시 추가 설명)
   - 메인2
       - 기존 문법 스터디의 각 주차에 해당하는 내용을 파트 상관없이 5문제씩 공유
       - 예시 : 1주차의 경우 열거형까지의 내용 중 랜덤하게 5문제 뽑기.
       - 선정 기준
           - 1순위 : 본인이 계속 헷갈리거나 체화되지 않은 부분
           - 2순위 : 분명 중요하다고 생각하는 부분
           - 질문이 다른 사람과 중복돼도 상관 없음.
- 아침 데일리 인증
    - 조장이 전날 저녁에 노션에 각 주차에 해당하는 문제 3개씩 랜덤하게 공유.
    - 다음날 점심 12시까지 해당 문제 풀고 카톡방에 인증샷 공유
    - 주 5일 진행 (주말엔 진행 안함)
    - 목표
        - 면접에서 대답하듯이 최대한 빠르고 분명하게 대답하는 연습 기르기
        - 스터디 몰아서 준비하는 대책
    - 주의
        - 모르는 내용이 나와도 찾아보고 답변하지 않기
        - 다른 사람의 답변 미리 참조하지 않기
        - 시간 엄수
        
- 패널티
    - 스터디 결석 시 스타벅스 아메리카노 기프토콘 공유
    - ‘아침 데일리 인증샷’ 공유 12시 초과 2회시 스타벅스 아메리카노 기프티콘 공유

### 진행내용

#### 메인1(iOS 면접질문 정리)
<details>
<summary>1주차</summary>

### Jess
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>

### Haha
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>

### John
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>

### Kyle
<details>
<summary>앱이 In-Active 상태가 되는 시나리오를 설명하시오.</summary>

앱의 5가지 상태중 In-Active 상태는 foreground 상태에 진입한후 Active 상태 바로 전의 상태를 의미한다.  
foreground 상태이기 때문에 UI가 화면에 표시되는 상태이지만, 사용자의 이벤트를 받을수 없다.  
앱의 In-Active 상태가 일어나는 시나리오는  

1. 다른 상태로 전환되기 전에 앱은 반드시 In-Active 상태를 거침.  
2. App Switter를 하고있는 상태일때
3. 앱 실행 도중 기기 우 상단을 쓸어내려 제어센터에 진입하는 경우
</details>
<details>
<summary>scene delegate에 대해 설명하시오.</summary>

iOS 13이후 한 앱에서 여러개의 화면을 지원하기 위해 전에 사용하던 window의 기능을 확장시킨 scene이 등장하였고,  
기존에 AppDeletage에서 담당하던 역할중 UI Lifecycle 관련 역할을 sceneDelegate에서 맏게 되었음.  
sceneDelegate에서 scene의 상태 전환에 따른 메소드를 호출한다.
</details>
<details>
<summary>UIApplication 객체의 컨트롤러 역할은 어디에 구현해야 하는가?</summary>

UIApplication 객체를 생성하는 UIApplicationMain 함수에서 구현해야 한다.
</details>
</details>
<details>
<summary>2주차</summary>
### Jess
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>

### Haha
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>

### John
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>

### Kyle
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>
</details>
<details>
<summary>3주차</summary>
### Jess
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>

### Haha
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>

### John
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>

### Kyle
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>
</details>
<details>
<summary>4주차</summary>
### Jess
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>

### Haha
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>

### John
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>

### Kyle
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>
</details>

#### 메인2(swift 문법 내용 복습)

<details>
<summary>1주차</summary>
### Jess
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>

### Haha
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>

### John
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>

### Kyle
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>
</details>
<details>
<summary>2주차</summary>
### Jess
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>

### Haha
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>

### John
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>

### Kyle
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>
</details>
<details>
<summary>3주차</summary>
### Jess
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>

### Haha
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>

### John
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>

### Kyle
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>
</details>
<details>
<summary>4주차</summary>
### Jess
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>

### Haha
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>

### John
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>

### Kyle
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>
<details>
<summary></summary>
</details>
</details>

#### 데일리 퀴즈
<details>
<summary>1주차 데일리 퀴즈</summary>

#### 12월 6일
<details>
<summary>swift 메모리 구조의 코드, 데이터, 힙, 스택에 대해 각각 설명하시오.</summary>

##### 코드
프로젝트에서 우리가 작성하는 코드가 기계어로 변환되어 저장됨.  
컴파일 타임에 저장되고. 중간에 코드가 변경되지 않도록 Read-Only 형태로 저장된다.
##### 데이터
전역변수, static 변수가 저장된다. 프로그램 시작시 메모리에 할당되고, 종료시 메모리에서 해제된다.  
런타임 도중에 변경될 수 있기 때문에 Read-Write 형태로 저장된다.
##### 힙
프로그래머가 할당하는 메모리 영역이다.  
사용하고 난 후 메모리 해제를 해야한다. -> 안할시 메모리 누수 발생한다.
##### 스택
함수 실행시 함수의 지역변수, 매개변수, 리턴 값 등이 저장되고, 함수 종료시 저장된 메모리도 같이 해제된다.
</details>
<details>
<summary>if문과 switch문의 차이점을 비교하고, 특징을 간단히 서술하세요.</summary>

if문은 조건이 만족할때까지 순차적으로 여러 조건을 비교하지만,  
switch문은 해당하는 표현식이나 변수를 매칭시켜 바로 true인 값으로 이동하는 작동방식에서의 큰 차이점이 있습니다.  

if문은 주로 간단한 조건문을 작성할때 주로 사용합니다.  
swift의 if문에서는 조건에 대한 소괄호는 선택사항입니다.  
  
switch문은 if문보다 복잡한 조건문을 작성할때 사용하고, if문보다 가독성이 좋습니다.  
switch문은 판별하는 표현식에 대해 모든 경우의 수를 다루어야 하고,  
모든 사례를 다루지 않을시 반드시 default 케이스가 있어야 합니다.  
각 케이스에는 최소 하나 이상의 문장이 존재해야 하고,  
만약 없을 경우 break를 반드시 입력해야 합니다.

</details>
<details>
<summary>swift에서 nil이란? 다른 언어의 null과 차이점은?</summary>

nil은 값이 없는게 아닌 값이 없는 상태를 나타내는 키워드입니다.  
어떠한 인스턴스가 nil 이라는 것은 값이 없는게 아니라 값이 없는 키워드를 나타내는 nil이 할당된 것입니다.
</details>

#### 12월 7일
<details>
<summary>swift에서 switch구문의 case를 연속 실행하려면 어떤 키워드를 사용해야 하고, 예시를 간단히 서술하세요.</summary>

해당 케이스에서 falltthrough를 사용하여 해당 케이스와 상관없이 무조건 다음 케이스를 실행시킨다.
```swift
switch value {
case one:
	fallthrough
case two:
	break
default:
	break
}
```
</details>
<details>
<summary>제어전송문 4가지를 각각 쓰이는 경우와 어떻게 사용되는지 간단하게 설명하세요.</summary>

##### break
- switch : 해당 케이스에서 아무것도 실행하지 않을때 반드시 break를 입력해야 합니다.
-  반복문 : 가장 인접한 반복문의 모든 사이클을 중지하고 반복문 다음의 문장으로 이동합니다.

##### fallthrough
- switch문에서 매칭된 값에 고려없이 무조건 다음 케이스를 실행합니다.

##### continue
- 반복문에서 다음 반복문의 싸이클로 넘어가서 계속 실행함.

##### return
- 리턴 타입이 없는 함수: 함수의 실행을 종료하고 함수를 벗어남
- 리턴 타입이 있는 함수: return 키워드 다음의 표현식을 평가하고 값을 리턴한 후 함수의 실행을 중지하고 벗어남

##### throw
- 에러가 발생 가능하도록 정의된 함수에서 throw 키워드 다음에 정의된 에러 의 타입을 리턴하면서 함수를 벗어남

</details>
<details>
<summary>딕셔너리의 키 값은 중복이 불가하고 Hashable 해야 한다. 여기서 Hashable이란 무엇인가?</summary>

해쉬 함수의 입력값으로 사용가능하다는 뜻이다.
</details>

#### 12월 8일

<details>
<summary>swift의 타입 관련 기본 문법 3가지에 대해 설명하시오(타입 주석, 타입 추론, 타입 안전성)</summary>

- 타입 주석
	- 변수를 생성할때 구체적으로 변수 옆에 명확하게 타입을 선언할 수 있다.
- 타입 추론
	- 타입을 구체적으로 선언하지 않아도 swift가 자동으로 타입을 추론하여 타입을 선언한다.
- 타입 안정성
	- swift는 타입에 민감한 언어로, 다른 타입과의 연산이 불가능하다.
</details>
<details>
<summary>튜플의 개념을 설명하고, 간단한 예시를 들어보세요.</summary>

튜플이란 여러가지 값의 모은 한 묶음을 의미한다. 각각의 값에 대해 이름을 붙여 사용할 수도 있다.
</details>
<details>
<summary>array, dictionary, set의 문서에 공통적으로 등장하는 sequence는 어떤 개념인가?</summary>

sequence는 프로토콜 타입으로 선언되어 있으며 element에 대한 순차적이고 반복적인 접근을 제공하는 타입이다.  
우리가 흔히 사용하는 컬렉션 타입은 모두 Sequence를 채택하고 있다.
</details>

#### 12월 9일

<details>
<summary>swift의 각 타입을 설명하세요.(Int, Float/Double, String/Character)</summary>

- Int(정수형 데이터 타입)
	- 정수 타입, 기본적으로 64비트 정수형이다.
- Float/Double(실수형 데이터 타입)
	- 실수 타입/ 부동 소수 타입
	- Float
		- 소수점 6자리까지 표현 가능 / 4바이트
	- Double
		- 소수점 15자리까지 표현 가능
- String / Charater (문자형 데이터 타입)
	- String
		- 문자열을 저장. 큰따옴표 사용
	- Charater
		- 문자 한 글자를 저장. 큰따옴표 사용
 
</details>
<details>
<summary>inout은 언제 사용하면 좋을까요?</summary>

함수의 파라미터는 상수로 그 값을 변경할수 없으나, 함수에서 매개 변수의 값을 수정하고 함수 호출이 종료된 후에도 변경 사항을 유지하려고 할 경우 inout 파라미터를 사용한다.
</details>
<details>
<summary>1..<3은 어떻게 for in 순환문으로 반복 순회가 가능할까요?</summary>

1...3 은 Range 객체이고, Range 객체는 Sequence 프로토콜을 채택하고 있다.  
Sequence 프로토콜은 채택한 타입의 element에 대해 순차적으로 연속적이고 반복적인 접근을 제공하는 타입이다.  
이러한 Sequence 프로토콜을 Range 객체가 채택하고 있기 때문에 for - in 반복문에서 순회가 가능하다.
</details>
</details>
<details>
<summary>2주차 데일리 퀴즈</summary>

<details>
<summary>12월 12일</summary>

<details>
<summary>클래스와 구조체에서 초기화의 의미에 대해 간단히 서술하시오.</summary>

초기화는 클래스나 구조체의 인스턴스 생성시 생성자 메서드를 이용하여 인스턴스의 모든 프로퍼티에 값을 할당하는 것을 의미한다.
</details>
<details>
<summary>저장 속성과 계산 속성의 차이를, 계산 속성을 사용하는 이유를 통해 설명하시오.</summary>

저장 속성은 고유의 메모리 공간을 할당받지만, 계산속성은 실질적인 메서드 형태로 사용된다.  
저장 속성을 상속받아 사용할 경우, 해당 속성의 값 변경이 불가능하다.  
실질적 메서드 형태인 계산 속성을 활용하면 데이터 공간을 변경하지 않고 값을 변경하지 않고도 활용이 가능하다.
</details>
<details>
<summary>Any와 AnyObject에 대하여 간단히 서술하세요.</summary>

Any는 swift에서 모든 타입을 다룰수 있는 타입이고,  
AnyObject는 클래스의 인스턴스만 다룰 수 있는 타입이다.
</details>
</details>
</details>