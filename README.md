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
<summary>Bound와 Frame의 차이점에 대해 서술하시오.</summary>

**Frame** 

 : SuperView 좌표계에서 View의 위치와 크기를 나타낸다

** SuperView : 최상위View가 아니라 한 칸 윗 계층인 View를 뜻함

** frame의 orgin값 : SuperView의 원점을 (0,0) 으로 놓고 원점으로부터 얼마나 떨어져 있는가?

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/fdd79d86-0d8a-4394-b91f-5b28ab7d8d8f/Untitled.png)

**Bounds**

: 자신의 좌표계에서 View의 위치와 크기를 나타낸다

frame이 슈퍼뷰의 좌표계였다면, bounds는 자신의 좌표계 즉 자신의 원점을 (0,0) 으로 놓음

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/82bd20b3-d814-4d42-ad2a-8c5dce851e21/Untitled.png)

![bounds의 size는 도형을 돌려도 바뀌지 않는다. View자체의 영역을 나타내기 때문에](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/db537043-aca1-4f27-9409-ed7344541014/Untitled.png)

bounds의 size는 도형을 돌려도 바뀌지 않는다. View자체의 영역을 나타내기 때문에

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/a250e725-6973-40d9-8f76-0603df022696/Untitled.png)

**frame과 bounds를 언제, 어떨 때 쓰는가?**

 : 위치(x,y)를 변경할 때 어떻게 차이가 나는지에 대해 알아야 한다

![frame의 경우](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/7d3082d7-f938-435d-ba34-d5ff4ad1528f/Untitled.png)

frame의 경우

![bounds의 경우](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/554918b0-4cbd-43fa-b730-211c05944c30/Untitled.png)

bounds의 경우

** bounds의 경우, viewport를 자체 좌표계에서 (50,50)으로 이동하는 것
    bounds의 x, y좌표를 바꿔준다 = viewport의 x, y좌표를 바꿔준다

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/94bc7924-5897-46ed-b290-d7f252dd5b8b/Untitled.png)

**Frame은 언제 사용할까**

UIView의 위치, 크기를 나타낼 때 사용한다

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/e7a6ac52-327f-4d26-ae28-9c06ecb55742/Untitled.png)

**Bounds는 언제 사용할까**

View를 회전한 후 View의 실제 크기를 알고 싶을 때 , ScrollView를 다룰 때 

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/e94cfddd-f069-49a9-af91-f600a8f092cc/Untitled.png)

**→ 정리**
가장 기본적인 차이는 어떤 좌표계가 기준이 되는가 라고 할 수 있습니다. Frame의 경우에는 상위뷰의 좌표계가 기준이 되며, Bounds는 자체 좌표계가 기준이 됩니다.
두번째의 차이는, 뷰를 회전하였을때 size의 값이 다르다는 것입니다. Frame 같은 경우 해당 뷰를 감쌀 수 있을 만큼 값이 커지지만, bounds는 변화가 없습니다.
두 가지 대표적인 사용 예시로는, Frame은 UIView의 위치나 크기를 설정하는 경우가 있고,
Bounds는 대표적으로 ScrollView에서 사용이 됩니다.
</details>
<details>
<summary>실제 디바이스가 없을 경우 개발 환경에서 할 수 있는 것과 없는 것을 설명하시오.</summary>

**하드웨어**

- 가속도 센서 기압계 센서, 주변광 센서들, GPS센서 기능을 이용할 수 없다.
- 카메라, 마이크, 전화기능

**API**

- 애플 푸시알림
- 사진, 연락처, 캘린더, 리마인더 등 개인정보 접근
- Handoff 기능
- MessageUI 기능

**그 외**

- 맥의 성능이 아이폰의 성능보다 훨씬 뛰어나 CPU나 메모리 부담이 얼마나 되는지 알 수 없다.
- 네트워크 속도를 테스트 할 수 없다.
- 페이스아이디의 직접적인 얼굴 인식은 안되지만 인식여부 처리는 해볼 수 있다.
</details>
<details>
<summary>앱의 콘텐츠나 데이터 자체를 저장/보관하는 특별한 객체를 무엇이라고 하는가?</summary>

**UserDefaults**

키 - 값으로 저장하는 인터페이스. 런타임시 개체를 이용하여 기본 데이터베이스에서 사용하는 기본값을 읽어오기 때문에 데이터베이스를 열 필요가 없다.

대용량의 데이터보다 자동로그인 여부, 아이디, 환경설정에서의 설정 데이터 값과 같은 단일 데이터 등을 보관한다.

**CoreData**

객체 그래프를 관리하기 위한 Framework 이다.

SQLite와 같이 테이블을 이용하지 않고 객체를 생성하여 데이터를 운영하기에 더 많은 저장공간과 메모리를 필요로 한다. 그렇지만 더욱 빠르게 데이터를 가져온다.

Data Model을 생성한 후 Entity를 생성한다.

**SQLite**

Swift에서는 특별한 설치 없이 바로 사용할 수 있다. 
C언어로 작성되어 있기에 매우 가벼운 것이 특징이며, 전체 데이터베이스를 디스크 파일 1개에 저장하고, 설정 자체가 매우 간편하기에 관리하기가 수월하다. 

SQLite는 iOS, Android, Linux, Windw 등과 같이 다양한 운영체제에서 사용된다.

수많은 프로세스와 스레드의 접근으로부터 안전하다.

**Realm**

SQLite와 같이 오픈소스이며, 모바일에 최적화된 라이브러리이다. SQLite, CoreData보다 속도가 빠르고 성능면에서 더 우수하다.

많은 작업들을 처리하기 위해 코드가 많이 필요하지 않으며, 메인 스레드에서 데이터의 읽기, 쓰기 작업을 모두 할 수 있어 편리하다.

대용량의 데이터에 대해 무료로 사용할 수 있으며 용량이 적고 큼에 상관없이 속도와 성능이 유지된다.
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
<summary>@Main에 대해서 설명하시오.</summary>

- 프로그램 시작 시 타입을 지정하기 위한 스위프트 언어 기능
- 스위프트 기반 iOS 언어에서는 UIkit 프레임워크에 숨겨져 있다.
- 어플을 실행하는데에 entry point를 지정하는 UIApplicationMain의 대체.
- UIApplicationMain과의 차이
    - 기존 UIApplicationMain는 클래스에 한정되어 사용이 가능하다.
        - @main은 타입 기반이기에 클래스 외에도 사용 가능하다.
    - 기존 UIApplicationMain은 UIKit 프레임워크을 위한 속성이다. (즉 NAppKit 프레임워크를 위해선 NSApplicationMain가 필요)
        - @main은 어떤 프레임워크든 상관없이 작동한다.
    - @main의 장점 정리
        - 기존보다 간편한 진입점을 제공하고 일관성을 구축한다.
- 참고
    - [https://barosalki.tistory.com/entry/iOS-Swift-53-main-type기반의-프로그램-진입점](https://barosalki.tistory.com/entry/iOS-Swift-53-main-type%EA%B8%B0%EB%B0%98%EC%9D%98-%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%A8-%EC%A7%84%EC%9E%85%EC%A0%90)
    - [https://github.com/apple/swift-evolution/blob/main/proposals/0281-main-attribute.md](https://github.com/apple/swift-evolution/blob/main/proposals/0281-main-attribute.md)
</details>
<details>
<summary>앱이 foreground에 있을 때와 background에 있을 때 어떤 제약사항이 있나요?</summary>

- Foreground 상태에 제약사항이 있다기 보단, background 상태에 제약사항이 존재한다는 표현이 적절하다.
    - (Foreground의 제약사항을 구지 말하자면 저전력모드에서 애니메이션 사용을 줄이고 프레임 속도를 낮추는 등을 언급 가능)
- background 상태의 제약사항
    - 시스템 리소스와 메모리 공간 사용에 제약을 받는다. (더 적은 메모리 공간을 사용해야 하며 더 적은 자원을 할당받는다.)
    - 특정 활동 제외한 경우 추가적인 실행시간을 할당받지 않는다.
        - 추가적인 실행 시간을 할당받는 경우
            1. AirPlay, Picture in Picture 비디오를 사용한 오디오 통신
            2. 사용자 위치 서비스
            3. Voice over IP
            4. 외부 악세서리와의 통신
            5. 블루투스 LE(Low Energy)와 통신, 혹은 디바이스를 블루투스 LE 악세서리로 변환
            6. 서버에서의 정기적인 업데이트
            7. Apple Push Notification 지원
- 참고 : [https://icksw.tistory.com/178](https://icksw.tistory.com/178)
- 추가 : 앱의 실행 상태에 따른 구분
    - Not running : 앱이 실행되지 않고 메모리에 올라와있지 않은 상태.
    - Foreground : 사용자가 보고 있는 화면. 시스템 리소스에 대한 우선수위가 높다.
        - Inactive : 앱이 활성화되고 있지만 메모리에서 최우선이 아닌 경우. ex) 앱 실행 중 전화가 오는 경우. 앱에 이벤트를 전달할 수 없다.
        - Active : 앱이 활성화된 상태. 실행되고 있는 앱이 높은 메모리 및 시스템 리로스의 우선순위를 가진다. 앱에 이벤트를 전달한다.
    - Background :
        - 앱이 홈화면에 들어가 사용자에게 보이지 않는 상태
        - 보통 Suspended에 들어가기 전 짧게 머물지만, 특정 앱들의 경우 Background 상태를 지속시키는 실행을 하기도 한다.
        - 가능한 적은 메모리 공간을 사용해야 하는 제약이 있다.
        - 메모리 공간이 부족할 경우, 운영체제는 Foreground에게 우선권을 부여하고 Background 상태의 앱을 종료한다.
        - Notification이나 Airplay 등의 경우는 제한된 사용시간을 할당받는다.
    - Suspended :
        - 앱이 Background 상태에 있으며 메모리에 남아 있으나 코드가 실행되는 상태는 아니다.
        - 메모리가 부족할 경우 운영체제는 별도의 알림 없이 Suspended 상태의 앱을 종료한다.
    - 참고
        - [https://minosaekki.tistory.com/16](https://minosaekki.tistory.com/16)
</details>
<details>
<summary>상태 변화에 따라 다른 동작을 처리하기 위한 앱델리게이트 메서드들을 설명하시오.</summary>

- application(_:didFinishLaunchingWithOptions:)
    - 애플리케이션이 실행된 직후 사용자의 화면에 보여지기 직전에 호출
- application(_:wilFinishLauchingWithOptions:)
    - 애플리케이션이 최초 실행될 때 호출되는 메소드
- applicationWillResignActive
    - 애플리케이션이 InActive 상태로 전환되기 직전에 호출.
    - task 일시정지, 타이머 비활성화, 일시정지(게임)
- applicationWillEnterForeground
    - 애플리케이션이 Active 상태가 되기 직전, 화면에 보여지기 직전에 호출
- applicationDidBecomeActive
    - 애플리케이션이 Active 상태로 전환된 후 호출
- applicationDidEnterBackground
    - 애플리케이션이 백그라운드 상태로 전환된 직후 호출
- apllicationWillTerminate
    - 애플리케이션이 종료되기 직전에 호출
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
<summary>Delegate란 무엇인지 설명하고, retain 되는지 안되는지 그 이유를 함께 설명하시오.</summary>

Swift에서는 Delegate 패턴을 통해 특정 기능을 위임하는 것이 가능하다. 한 객체에서 모든 프로세스를 처리하기에는 가독성, 코드 재사용성 측면에서 많은 손해를 보기 때문이다

Delegate는 대리자, 위임하다 라는 단어의 뜻처럼, 하나의 객체가 모든 일을 처리하는 것이 아니라 처리해야할 일 중 일부를 다른 객체에 넘기는 것을 말한다.
위임된 책임을 캡슐화하는 프로토콜로 구현되며, 위임자가 위임된 기능을 제공하도록 보장한다.

Delegate를 통해 일을 위임하는 객체들은 일을 시킬 뿐, 일이 어떻게 처리되는지 모르기 때문에 코드의 유지보수 측면에서 장점을 가지고 있다. 

retain은 객체가 메모리에서 해제되지 않도록 호출되어 레퍼런스 카운트를 증가시키는데,
Delegate는 객체끼리 참조값을 사용하기 때문에 retain이 된다.
</details>
<details>
<summary>NotificationCenter 동작 방식과 활용 방안에 대해 설명하시오.</summary>

**NotificationCenter**

등록된 모든 Observer에게 정보를 전달하는 메커니즘

**동작방식**

Notification Center

- Listener (observer) : notifications를 감지
- Sender : 필요할 때 notifications 를 보내주는 역할
- itself : notification center 그 자체.

Observer가 관찰 시작 → 작업이 발생하면 Sender가 Post → Observer selector 실행

```swift
NotificationCenter.default.addObserver(self, selector: #selector(handleNoti(_:)), name: myNoti, object: nil)
NotificationCenter.default.post(name:"myNoti", object:" 전달할 값")
```

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/d582344b-6aac-4ea1-9fa6-6dd47ad6a550/R1280x0.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/d582344b-6aac-4ea1-9fa6-6dd47ad6a550/R1280x0.png)

Notification 

특정 객체가 Notification Center에 등록된 이벤트를 발생시키면 해당 이벤트를 처리할 것이라고 등록된 옵저버들이 이벤트에 대한 행동을 취하는 것이 동작 방식. 
이렇게 특정 객체가 이벤트를 발생시키는 것을 Post라고 한다. 
NotificationCenter는 델리게이트 패턴과 함께 어플리케이션 내에서 객체가 서로 상호작용할 수 있는 방법 중 하나이다. 

[https://baked-corn.tistory.com/42](https://baked-corn.tistory.com/42)

**→ 정리** 

**동작방식**

1) 옵저버를 등록한다.

2) 시스템에서 등록된 옵저버를 감시하면서 변경사항이 발생하면 1을 등록한 객체에게 알려준다. 

**활용방안**

다른 객체의 변경사항을 알고 싶을 때 , 예를들어 화면의 가로세로 전환 

- John 추가
    - NotificationCenter : 등록된 Observer에 정보를 뿌리는 노티피케이션 발송 메커니즘
    - Notification : NotificationCenter를 통해 등록한 모든 옵저버에게 정보를 뿌리는 컨테이너
    - NotificationCenter는 Notification에서 발송한 모든 Observer가 처리 완료될때까지 대기한다.(동기적) ↔ 비동기적 사용을 위해선 NotificationQueue 사용
    - 참조 : [https://vincentgeranium.github.io/ios,/swift/2020/05/31/iOS-QnA-Summary-1.html](https://vincentgeranium.github.io/ios,/swift/2020/05/31/iOS-QnA-Summary-1.html)
    - 대표적인 활용 사례는 키보드의 등장 여부에 따른 알림을 받아 원하는 코드를 처리할 수 있다.
        
        ```swift
        NotificationCenter.default.addObserver(self, selector: #selector(textViewMoveUp), name: UIResponder.keyboardWillShowNotification, object: nil)
        ```
        
    - 참조 : [https://nsios.tistory.com/17](https://nsios.tistory.com/17)
</details>
<details>
<summary>UIKit 클래스들을 다룰 때 꼭 처리해야하는 애플리케이션 쓰레드 이름은 무엇인가?</summary>

**Main Thread**

`CocoaTouch` 어플리케이션은 `UIApplication`의 인스턴스가 메인스레드에 붙게 된다.
메인스레드는 `UIApplication`으로부터 만들어지고, `UIApplication`은 앱이 처음 시작될 때 인스턴스화 되는 앱의 첫 시작 부분이다.

`UIApplication`은 어플리케이션 런루프를 포함한 메인 이벤트 루프를 세팅하고, 이벤트 처리를 한다.

어플리케이션의 메인이벤트 루프는 터치, 제스처같은 모든 UI이벤트들을 받는다.
</details>
<details>
<summary>자신만의 Custom View를 만들려면 어떻게 해야하는지 설명하시오.</summary>

**1) Xib을 이용해서 별도의 StroyBoard처럼 관리 가능**

- Xib를 생성하고 또한 별도의 UIView를 상속받은 Class를 생성한다. 그리고 Xib에서 오너로 해당 클래스를 임명하고 클래스 내에서 초기화 시, Xib파일을 불러와 뷰로 임명하는 코드를 추가하고 원하는 작업들을 StroyBoard와 동일하게 수행하면 된다.

**2) UIView를 상속해서 코드로만 구현**

- UIView를 상속받는 클래스를 생성해 정말 코드로만 원하는 작업들을 설정
</details>

### John
<details>
<summary>Global DispatchQueue 의 Qos 에는 어떤 종류가 있는지, 각각 어떤 의미인지 설명하시오.</summary>

- Global DispatchQueue는 QoS(Qualtiy of Service)에 따라 실행할 작업의 우선순위를 6가지로 나눈다.  
- userInteracitve : main 쓰레드에서 UI 관련 업데이트 및 애니메이션 수행. 즉각적인 반응 필요.
- userInitiated : 사용자의 이벤트에 반응. 빠른 결과 필요.
- default : 별다른 QoS를 설정해두지 않은 상태. userInitiative와 utility의 중간.
- utility : 데이터 다운로드와 같이, 즉각적인 결과가 필요하지 않을 때 사용.
- background : 백그라운드에서 동작. 백업/동기화 등과 같이 사용자가 볼 수 없는 작업.
- unspecified : QoS를 추론해야 함을 시스템에 전달.
</details>
<details>
<summary>iOS 앱을 만들고, User Interface를 구성하는 데 필수적인 프레임워크 이름은 무엇인가?</summary>

- UIKit 프레임워크.
- 화면 구성 요소 설정 : 버튼, 슬라이더, 테이블뷰, 알림창 등 화면을 구성하는 요소
- 사용자 이벤트 처리 : 제스처 처리, 애니메이션, 이미지/텍스트 처리
- 주의사항 : 메인 쓰레드에서 사용할 것.
</details>
<details>
<summary>Foundation Kit은 무엇이고 포함되어 있는 클래스들은 어떤 것이 있는지 설명하시오.</summary>

- Foundation Kit은 Cocoa Touch Framework에 포함된 프레임워크 중 하나.
    - Cocoa Touch Framework : NSObject를 상속받는 모든 객체. Cocoa Framework는 맥.
- String, Int 등의 원시 타입과 컬렉션 타입, 운영체제 서비스를 사용하여 앱의 기본적인 기능을 구현한다.
</details>
<details>
<summary>모든 View Controller 객체의 상위 클래스는 무엇이고 그 역할은 무엇인가?</summary>

- UIViewController
- 뷰 크기 조정 및 전체 인터페이스 레이아웃 관리
- 뷰 데이터 업데이트
- 뷰 사용자 상호작용에 응답
- 뷰 컨트롤러간의 이동
- 뷰 컨트롤러의 상위 클래스는 UIResponder
</details>

### Kyle
<details>
<summary>App의 Not running, Inactive, Active, Background, Suspended에 대해 설명하시오.</summary>

- Not running
    - 앱이 아직 실행되지 않아 메모리에 올라가지 않은 상태.
- lnactive
    - 앱이 foreground 상태이지만, 이벤트를 받을 수 없는 상태.
    - 모든 앱의 상태는 이 상태를 반드시 거쳐가야 한다.
    - 앱 스위처 모드, 제어 센터 접근시의 상태
- Active
    - 앱이 foreground 상태이며, 이벤트를 받을수 있는 상태.
- Background
    - 앱 사용중 다른 앱을 실행하거나, 홈 화면으로 나갔을때의 상태
- Suspended
    - 앱이 백그라운드에 있고, 메모리에 올라가있는 상태이지만 아무런 코드가 실행되지 않는 상태.
    - 앱이 Background인 상황에서 아무 동작도 하지 않으면 Suspended 상태로 진입한다.
</details>
<details>
<summary>NSOperationQueue 와 GCD Queue 의 차이점을 설명하시오.</summary>

## 멀티스레딩을 위한 API

멀티스레딩을 처리하기 위해 애플은 두가지 API를 제공하고 있다.

**GCD**라는 C언어 기반의 저수준 API와 **NSOperation**이라는 Object-C기반의 고수준 API가 있다.

### GCD(Grand Central Dispatch)

스레드를 관리해주고 동시적으로 작업을 처리할 수 있게 해주는 저수준 API를 제공해주는 라이브러리.

GCD는 멀티 코어 프로세서 시스템에 대한 응용 프로그램 지원을 최적화하기 위해 사용되는 라이브러리로,

스레드 관리와 실행에 대한 책임을 운영체제 레벨로 넘겨 버림으로서 프로그래머가 쉽게 비동기적으로 작업을 처리할 수 있음.

GCD에서 사용하는 Queue가 바로 **DispatchQueue**이다.

### NSOperation

NSOperation들을 만들어서 병렬로 실행시키는 스레드 풀을 제공한다. 

Operation queue가 GCD의 일부는 아니다.

### GCD Queue(DispatchQueue)

- C기반 로우레벨의 API
- Global Queue에서 QOS 우선순위를 줄 수 있다.
- Main Queue: 메인 스레드에서 사용될 것 들을 처리, UI코드

### NSOperationQueue

- Objective-C 기반 고수준 API
- GCD보다 약간의 오버헤드가 더 발생되고 느리다. But KVO 지원 및 작업취소등을 지원
- 다양한 작업들 중에서 의존성을 추가할 수 있다
- 재사용, 취소, 중지 가능하다
- NSOperation을 만들어서 병렬 or 직렬로 스레드 풀을 사용가능하다.
</details>
<details>
<summary>GCD API 동작 방식과 필요성에 대해 설명하시오.</summary>

### ***GCD란?***

스레드를 관리해주고 동시적으로 작업을 처리할 수 있게 해주는 저수준 API를 제공해주는 라이브러리.

GCD는 멀티 코어 프로세서 시스템에 대한 응용 프로그램 지원을 최적화하기 위해 사용되는 라이브러리로,

스레드 관리와 실행에 대한 책임을 운영체제 레벨로 넘겨 버림으로서 프로그래머가 쉽게 비동기적으로 작업을 처리할 수 있음.

### GCD의 필요성

실행할 작업을 클로저의 형태로 DispatchQueue에 추가하면 GCD가 스레드를 자동으로 생성하고 실행해주고 스레드를 관리.

개발자는 **내부 동작을 자세히 알 필요없이 Queue에 작업을 넘기기만 하면 되어**
서, Thread를 직접 생성하고 관리하는 것에 비해 관리도 용이하고 성능 면에서도 좋은 결과를 얻을 수 있음.
</details>
<details>
<summary>App Bundle의 구조와 역할에 대해 설명하시오.</summary>

## Bundle

- 실행가능한 코드와 관련 리소스(앱 아이콘, 이미지 등)를 한 공간에 묶는 디렉토리 모음

## Application Bundles

- 개발자들에 의해 흔히 생성되는 가장 흔한 번들
- 앱이 정상적으로 작동하기 위해 필요한 모든 것.
- 플랫폼에 따라 상세한 구조는 다르지만 번들을 사용하는 방법은 동일하다.

### Application Bundle에 포함되어 있는 파일들

### Info.plist file

- 앱에 대한 구성(configuration) 정보(bundle ID, version number 등)를 포함한 파일

### Excutable

- 모든 앱은 실행 가능 파일이 있어야 하고 앱의 메인 진입점과 정적으로 앱 타겟에 연결된 코드가 포함한다.

### Resources files:

- 앱의 실행가능한 파일 밖에 데이터 파일로 존재한다. 일반적으로 이미지, 아이콘, 사운드, nib 파일, 문자열 파일, 구성 파일 등의 것들로 구성된다. 대부분의 리소스는 특정 언어와 지역에 따라 localized될 수 있으며 localized된 파일은 `lproj` 확장자를 가진 파일로 저장된다.
- 거의 대부분 옵셔널하지만 항상 그런 것은 아니다.
- ex) iOS앱은 보통 추가적인 아이콘 이미지를 요구한다.

### Other support files

- 커스텀 데이터 리소스를 iOS 앱 번들에 포함할 수 있지만 커스텀 프레임워크 또는 플러그인은 포함할 수 없다.

## iOS App Bundle structure

프로젝트 템플릿은 아이폰 또는 아이패드 앱의 번들에 대한 대부분의 필요한 작업을 Xcode에 의해 제공한다. 하지만 앱 번들 구조에 대한 이해는 커스텀 파일을 어디에 배치해야할지 결정하는데 도움을 준다.

iOS 앱의 번들 구조는 모바일 기기의 필요에 더 초점이 맞춰져 있다. 디스크 공간을 절약하고 파일 접근을 단순화하기 위해 적은 수의 외부 디렉토리가 있는 비교적 평평한 구조를 사용한다.

일반적인 iOS 앱 번들은 최상위 번들 디렉토리에서 앱 excutable과 앱에서 사용되는 리소스(앱 아이콘, 이미지, localized된 내용)로 구성된다.

아래는 MyApp이라는 앱의 구조이다. 서브 디렉토리로 존재하는 파일들은 localized 파일이다. 하지만 추가 서브 디렉토리에 리소스 또는 관련 파일을 추가할 수 있다.

```xml
MyApp.app
   MyApp
   MyAppIcon.png
   MySearchIcon.png
   Info.plist
   Default.png
   MainWindow.nib
   Settings.bundle
   MySettingsIcon.png
   iTunesArtwork
   en.lproj
      MyImage.png
   fr.lproj
      MyImage.png
```

MyApp (필수)

- 앱의 코드를 포함하고 있는 실행가능한 파일이다. .app 확장자를 뗀 것이 실제 앱 프로젝트의 이름과 같다. 번들 구조에 반드시 있어야 한다.

Application icons((MyAppIcon.png, MySearchIcon.png, and MySettingsIcon.png)

- 앱 아이콘은 앱을 표시하는데 사용된다. 예를 들어 홈 스크린, 검색 결과 그리고 설정에서 앱이 앱의 아이콘으로 표시된다. 대부분의 경우 앱 아이콘을 꼭 포함해야 한다.

Info.plist (필수)

- bundle ID, 버젼 번호 등 앱에 대한 구성(configuration) 정보를 포함하고 있는 파일이다.

Launch images(Default.png)

- 앱의 시작 인터페이스를 보여주는 이미지.
- 시스템은 제공된 런치 이미지 중 하나를 앱이 윈도우와 유저 인터페이스를 로드할 동안 임시로 사용한다. 만약 임시 런처 이미지가 없다면 검은 화면이 보여진다.

MainWindow.nib

- 앱의 main nib file은 앱 런치 시간에 앱을 로드하기 위한 기본 인터페이스 객체를 포함한다. 보통 앱의 메인 윈도우 객체와 앱 델리게이트 객체를 갖고 있다.

Settings.bundle

- 앱의 application-specific preferences를 포함하는 특별한 타입의 플러그인이다. 이 번들은 property list와 구성하기 윈한 다른 리소스 파일이 포함되어 있고 preference를 보여준다.

Custom resource files

- non-localized 리소스들은 최상위 디렉토리에 위치하고 localized 리소스는 language-specific 하위 디렉토리에 위치한다.

### 정리

하나의 앱을 구성하는 요소(실행파일, 리소스 등)들을 하나의 디렉토리에 모아서 번들이라는 개념으로 관리하고 있다.

번들에는 필수적으로 포함되야 하는 것들과 필수는 아니지만 권장되는 요소들이 많고, 이러한 요소들은 각각의 역할이 있다.  
출처 - https://thoonk.tistory.com/64
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
<summary>Optional에 대해 설명하시오.</summary>

‘nil’이라는 값을 가질 수 있으면 Optional 타입이고, Optional타입을 선언할 때에는 타입 옆에 ?(물음표)를 붙인다. (nil은 값이 없음을 나타낸다.)
</details>
<details>
<summary>Optional 타입에는 .none이 있는데, 이것과 nil의 공통점 또는 차이점은?</summary>

Optional.none은 옵셔널을 열거형으로 표현하여 값이 없음을 나타내는 것일 뿐이고, nil과 완벽히 동일하다. 
 때문에 nil을 쓸 수 있는 자리에 Optional.none으로 대체 가능하다.
</details>
<details>
<summary>Optional을 언래핑하는 4가지 방법은?</summary>

1. **강제 언래핑**
-  nil이 아닌 값이 있다는 것을 확신하고 강제로 값을 추출
- `num!`
2. **암시적 언래핑**
- if문을 통해 nil이 아님을 먼저 확인 후, 강제추출 

```swift
 if num != nil {
       print(num!)
    }
```

1. **옵셔널 바인딩** 
 - 바인딩이 되는 경우만 특정 작업을 하겠다는 의미

```swift
if let name = optionalName {
    pirnt(name)
} 
```

1. **닐 코얼레싱**
- 옵셔널 표현식 뒤에 기본값을 제시해서, 옵셔널의 가능성을 없앰 (물음표 2개 뒤 옵셔널이 nil일 경우 대체할 수 있는 값 지정)
- 디폴트값을 제시 가능한 경우 사용
</details>
<details>
<summary>Hashable이 무엇이고, Equatable을 왜 상속해야 하는지 설명하시오.</summary>

기본적으로 Hash함수에 input으로 쓰일 수 있는 타입을 Hashable하다고 한다. swift의 기본 타입은 모두 Hashable하다. hash란, 해시 함수에 의해 얻어지는 값이다. 

hashValue는 어떠한 데이터를 Hash함수에 넣게 되면 반환해주는 값이다.

Equatable은 값이 동일한지 아닌지를 비교할 수 있는 타입인 프로토콜이다.
이 프로토콜을 준수하는 타입은 == 혹은 ! =을 사용하여 동등성을 비교할 수 있다.

HashValue는 고유값이어야 하므로, 고유값인지 식별해줄 수 있는 ==함수가 필요하기 때문에 Equatable을 상속해야 합니다.
</details>
<details>
<summary>제어전송문 4가지를 각각 쓰이는 경우와 어떻게 사용되는지 간단하게 설명하시오.</summary>

1. break문
- 반복문(for/while) : 가장 가까운 반복문 완전히 종료
- switch문 : break-case에서 어떤 문장의 실행도 없을 때 입력하는 약속
2. fallthrough문
 - switch문에서 어떤 해당 case를 해당한 후, 다음 case의 해당 여부를 따지지 않고, 다음 case내부의 문장을 실행
3. continue문
 - 반복문에서 가장 가까운 반복의 이번 주기를 끝내고 바로 다음 주기로 넘어가서 실행
4. return문
 - return 타입이 없는 경우 : 해당 함수를 종료하고 벗어남
- return 타입이 있는 경우 : return문 뒤의 표현식 평가 후, 그 값을 반환하면서 함수를 종료하고 벗어남
</details>

### John
<details>
<summary>프레임워크와 라이브러리에 대해 간략히 설명하고, 알고있는 예시를 몇 가지 알려주세요.</summary>

프레임워크는 swift 기본 언어에 import하여 사용하는 기본적인 기능이며,  
라이브러리는 프레임워크를 활용하여 쓰기 편하게 미리 구현해 놓은 기능이다.
</details>
<details>
<summary>폰노이만 컴퓨터 구조에 대해 설명해보세요</summary>

개발자의 코드는 평소 하드디스크에 저장되어 있다가, 실행되는 순간 RAM으로 복사된다.  
복사된 이 코드들은 CPU가 하나씩 실행한다.  
또한 메모리에는 실제 모든 공간에 주소가 붙어있어 CPU에서 접근이 가능하다.
</details>
<details>
<summary>파라미터/아규먼트 차이는?</summary>

파라미터는 함수의 정의에서 사용되는 인자를 호칭한다.  
아규먼트는 실제 함수의 실행에서 입력되는 인스턴스 값.
</details>
<details>
<summary>함수에서 쓰이는 제어전송 키워드 2개와 역할은?</summary>

return: 함수 실행 종료. 결과값이 있는 함수일 경우 값을 반환한다.  
throw: 에러 발생 가능 함수에서 error 타입을 반환하고 함수 종료.
</details>
<details>
<summary>리턴값이 있는 함수와 없는 함수의 차이는?</summary>

리턴값이 없는 함수는 CPU 제어권만 가져오지만,  
리턴값이 있는 함수는 CPU 제어권과 더불어 값을 반환하기 위한 임시 메모리 공간을 별도로 만든다.
</details>

### Kyle
<details>
<summary>swift 메모리 구조의 코드, 데이터, 힙, 스택에 대해 각각 설명하시오.</summary>

- 코드
프로젝트에서 우리가 작성하는 소스 코드가 기계어 형태로 저장.
컴파일 타임에 저장되고, 중간에 코드가 변경되지 않도록 Read-Only 형태로 저장.
- 데이터
전역변수, static 변수가 저장된다.
프로그램 시작과 동시에 할당되고, 프로그램 종료시 메모리에서 해제된다.
실행 도중 변수 값이 변경될 수 있으니 Read-Write로 지정된다.
- 힙
프로그래머가 할당/해제 하는 메모리 영역
사용하고 난 후 반드시 메모리 해제 필수! -> 안할 경우 메모리 누수가 발생.
- 스택
함수 호출 시 함수의 지역변수, 매개변수, 리턴 값 등등이 저장되고, 함수 종료시 저장된 메모리도 해제.
</details>
<details>
<summary>스위프트의 각 타입을 설명하세요.(Int, Float/Double, String/Character, Float/Double)</summary>

### Int(정수형 타입)

- 정수 타입이다. 기본적으로 64비트 정수형.

### Float/Double

- Float
    - 6자리까지 소수점 표현 가능 / 4바이트
- Double
    - 15자리까지 소수점 표현 가능

### String/Charater

- String
    - 문자열을 저장. 큰따옴표 사용
- Charater
    - 문자(한글자)를 저장. 큰따옴표 사용.
</details>
<details>
<summary>swift의 타입 관련 기본 문법 3가지에 대해 설명하시오(타입 주석, 타입 추론, 타입 안전성)</summary>

- 타입 주석
    - 변수를 선언하면서, 타입도 명확하게 지정하는 방식
- 타입 추론
    - 타입을 지정하지 않아도, 컴파일러가 타입을 유추해 저장하는 방식
- 타입 안정성
    - 스위프트는 데이터 타입을 명확하게 구분하여 사용한다.
</details>
<details>
<summary>튜플의 개념을 설명하고, 간단한 예시를 들어보세요.</summary>

튜플은 타입의 이름이 따로 지정되지 않은, 프로그래머 마음대로 만드는 타입.
ex) var human: (String, Int, Double) = (”Jess”, 123, 12.3)
</details>
<details>
<summary>array, dictionary, set의 문서에 공통적으로 등장하는 sequence는 어떤 개념인가?</summary>

Sequence는 프로토콜 타입으로 구성되어 있으며, 
채택할 경우 타입의 요소들에 대해 순차적으로 연속적인 값의 접근을 제공한다.
</details>
</details>
<details>

<summary>2주차</summary>
### Jess
<details>
<summary>지연저장속성을 사용하는 이유?</summary>

1. 메모리 공간을 많이 차지하는 이미지 등의 속성에 저장할 때, 반드시 메모리에 다 올릴 필요가 없으므로 메모리의 낭비를 막기 위해서
2. 다른 속성들을 이용해야 할 때, 초기화 시점에 모든 속성들이 동시에 메모리 공간에 저장되므로 어떤 한가지 속성이 다른 속성에 접근할 수 없다.
하지만, 지연 저장 속성을 사용할 경우 지연으로 저장된 속성은 먼저 초기화된 속성에 접근할 수 있게 됨
</details>
<details>
<summary>객체지향의 개념에서, 클래스가 다른 타입과 구별되는 결정적인 차별점은 무엇인가?</summary>

상속성.  
부모클래스의 속성과 메서드를 자식클래스에서 그대로 물려받는 개념이다.  
상속을 통해 코드가 재활용되기 때문에 생산성이 높아진다.
</details>
<details>
<summary>메서드가 아닌 속성방식으로 구현하는 무슨 장점이 있을까?</summary>

1. 관련이 있는 두 가지 메서드(함수)를 한번에 구현할 수 있다.
2. 외부에서 보기에 속성 이름으로 설정이 가능하므로 보다 명확해보인다.
3. 실제로 계산 속성의 겉 모습은 속성(변수) 형태를 가진 메서드이다.
4. 인스턴스 외부에서 메서드를 통해 접근하려면 메서드를 여러개 구현해야 하기 때문에 코드의 가독성이 나빠진다. → 코드의 가독성을 좋게 만들 수 있다.
</details>
<details>
<summary>접근제어가 필요한 이유?</summary>

코드의 영역을 분리시켜서 효율적으로 관리가 가능하다. 
또한 컴파일러가 해당 변수가 어느 범위에서만 쓰이는지를 인지하여 컴파일 시간이 줄어든다.
</details>
<details>
<summary>싱글톤의 사용 예제를 간단히 말해보세요.</summary>

- `**UserDefaults.standard**` 사용자 기본 설정과 같은 단일 데이터 저장소
- `**UIApplication.shared**`  앱 실행동안, 앱을 제어하는 객체
- `**NotificationCenter.default**` 알림을 통해, 다른 객체간에 정보 전달
</details>

### John
<details>
<summary>객체지향 프로그래밍의 단점은?</summary>

- 단방향의 상속
- 객체간 정보교환이 모두 메세지를 통해 이뤄지기 때문에, 메모리와 처리 시간에 많은 오버헤드가 발생한다.
</details>
<details>
<summary>하위 클래스가 상속받은 저장 속성을 수정할 수 없는 이유는?</summary>

상속받은 저장 속성은 이미 상위 클래스의 생성자를 통해 초기화되어 있다.
</details>
<details>
<summary>클래스가 구조체보다 성능이 느린 이유는?</summary>

- 클래스의 인스턴스를 만드는 것 자체가 느리다.
    - 클래스가 생성자를 통해 초기화될 때, 힙 영역 전체를 훑어 적절한 공간을 찾아 인스턴스의 값을 저장한다.
    - 스택프레임에 쌓인 인스턴스가 힙 영역의 주소를 저장한다.
- 클래스의 메서드를 실행하는 것이 느리다.
    - 클래스의 인스턴스가 힙 영역에 만들어졌다고 생각했을 때, 그 메서드를 실행하려면 데이터영역의 vtable에 저장된 메서드를 찾는 과정이 필요하다. vtable의 메서드는 코드영역의 해당 메서드 주소를 가지고 있다.
- 메모리 구조를 관리하는 것이 느리다.
</details>
<details>
<summary>Any와 any의 차이는 무엇인가?</summary>

- Any는 클로저를 포함한 모든 타입을 나타낸다.
- any는 Any 및 AnyObject와 전혀 다른 개념.
- any는 generic 타입과 existential 타입(프로토콜을 타입 주석으로 적은 경우)의 병기를 혼돈하는 경우를 방지하기 위해 스위프트 5.6부터 고안되었다.
- exitstential 타입은 타입 추론 위해 dynamic dispatch로 동작하기 때문에 성능의 저하를 가져올 수 있다. 따라서 개발자들에게 existential 타입으로 쓰는 것을 인지시키기 위해 any 키워드를 붙여야 한다.
- existential 타입을 피하고 싶은 경우 제네릭 타입으로 병기하면 concrete 타입으로 static dispatch로 동작한다.
- [https://zeddios.tistory.com/1348](https://zeddios.tistory.com/1348)
- [https://raonnydev.tistory.com/entry/Any-AnyObject-any-언제-써야할까](https://raonnydev.tistory.com/entry/Any-AnyObject-any-%EC%96%B8%EC%A0%9C-%EC%8D%A8%EC%95%BC%ED%95%A0%EA%B9%8C)
- [https://www.hackingwithswift.com/swift/5.6/existential-any](https://www.hackingwithswift.com/swift/5.6/existential-any)
</details>
<details>
<summary>AnyClass는 어떤 클래스 타입의 인스턴스도 표현할 수 있는 AnyObject 프로토콜이자 메타타입이다 이때, 메타타입이란 무엇인가?</summary>

- 메타타입은 타입의 타입이다.
- swift에서 타입은 1. metatype (String.Type) 2. metatype의 인스턴스인 type (String.self) 3. 타입의 인스턴스 (String) 으로 나뉘어진다.
</details>

### Kyle
<details>
<summary>Any와 AnyObject에 대하여 간단히 서술하세요.</summary>

특정 타입을 지정하지 않고 여러 타입의 값을 할당할 수 있는 타입입니다.  
상속 관계에 있는 타입들끼리만 타입캐스팅이 가능하지만,  해당 타입은 상속 관계 상관 없이 타입캐스팅이 가능하다.  
Any는 swift의 모든 타입, AnyObject는 class 타입만 할당이 가능하다.
</details>
<details>
<summary>클래스와 구조체에서 초기화의 의미에 대해 간단히 서술하시오.</summary>

초기화란 생성자 메서드를 실행하여 클래스나 구조체의 모든 저장 속성의 값 설정을 완료하고, 인스턴스를 생성하는것을 말한다.
</details>
<details>
<summary>확장에 대해 간단히 서술해주세요.</summary>

클래스나 구조체, 열거형 타입에 추가적인 기능을 확장시키는 방법.  
메서드를 추가하는 것만 가능하며, 저장 속성은 추가할 수 없음.  
클래스에서 생성자를 구현하려는 경우, 편의생성자 형태만 추가 가능.
</details>
<details>
<summary>상속과 확장의 차이점을  설명해주세요.</summary>

클래스의 상속은 상위 클래스를 상속받아 비슷한 형태의 새로운 타입을 정의하고, 추가 기능을 구현하는 수직확장의 형태.  
반면 확장은 기존에 존재하는 타입에 기능을 추가하는 수평확장의 형태입니다.  
상속을 받으면 기존 기능을 재정의할 수 있지만, 확장은 재정의 할 수 없음.
</details>
<details>
<summary>static과 class의 차이점을 설명해주세요.</summary>

static 키워드는 타입 속성이나 메서드를 선언할때 사용한다.  
class 키워드도 마찬가지로 static과 기능이 유사하나, class 키워드의 경우 해당 속성이나 메서드를 상속 가능하게 하여 재정의할수 있다.
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


#### 12월 12일

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


#### 12월 13일

<details>
<summary>Class 타입의 초기화 위임 규칙에 대해 설명해주세요.</summary>

1. 서브클래스의 지정 생성자는 슈퍼클래스의 지정생성자를 반드시 호출해야 한다.
2.  편의 생성자는 자신을 정의한 클래스의 다른 생성자를 반드시 호출해야 한다.
3. 편의 생성자는 궁극적으로 반드시 지정 생성자를 호출해야 한다.
</details>
<details>
<summary>required 키워드에 대해서 설명해보세요.</summary>

클래스 상속시 필수적으로 구현해야 되는 생성자.
</details>
<details>
<summary>init?()은 어떤 특징을 가지고 있고, init()과 어떤 차이가 있나요?</summary>

init?()은 기존의 생성자와 다르게 초기화에 실패할수 있는 가능성을 가지고있다.  
따라서 init?()은 초기화가 실패할 경우 nil을 반환한다.
</details>

#### 12월 14일

<details>
<summary>저장 속성과 계산 속성의 차이를, 계산 속성을 사용하는 이유를 통해 설명하시오.</summary>

저장 속성은 클래스/구조체에서 일정 데이터 공간을 차지한다. 반면 계산 속성은 실질적인 메서드 형태이기 때문에 메모리 공간을 차지하지 않는다.  
계산속성을 쓰는 이유는 상속시 값을 변경할수 없는 저장속성과 다르게 상속받아도 값 변경이 가능하다.  
또한 함수실행에 비해 속성값으로 표시되기 때문에 코드의 가독성이 좋아진다.
</details>
<details>
<summary>타입 속성의 뜻과 그 키워드인 static과 class의 차이는?</summary>

타입 속성은 인스턴스에 포함되지 않고, 타입 자체에 속해 데이터 영역에 앱 종료시까지 계속 할당되는 속성이다.  
타입 속성은 저장 타입 속성과 계산 타입 속성으로 나뉜다.  
저장 타입 속성은 lazy하게 동작하기 때문에 초기값이 반드시 필요하다.  
기본적으로 타입 속성을 선언할때 사용하는 static 키워드로 선언 할 경우 재정의가 불가능하지만, class 키워드로 대신 선언할 경우 재정의가 가능하다.(단, 저장 속성에 대해서는 엄격하게 재정의 불가능.)
</details>
<details>

<summary>클래스를 상속받았을 때, 저장 프로퍼티는 재정의가 불가한데 계산 프로퍼티는 재정의가 가능한 이유는?</summary>

실질적 메서드 형태로 저장되기 때문이다.  
저장 프로퍼티는 힙에 값을 저장하지만, 저장 프로퍼티는 메서드 처럼 작동해 데이터 영역에 저장된 클래스의 virtual table에 배열 형태로 저장된다. 이러한 메서드들은 상속할때 항상 새로운 배열을 만들어내기 때문에 재정의가 가능하다.
</details>

#### 12월 15일

<details>
<summary>String은 왜 subscript로 접근이 안되는지 설명하시오.</summary>

String이 Charater로 이루어진 collection이기 때문, 서브스크립트가 아닌 String.index 형태로 접근 가능하다.
</details>
<details>
<summary>Any와 AnyObject에 대하여 간단히 서술하세요.</summary>

특정 타입을 지정하지 않고 여러가지 타입을 할당할 수 있는 타입이다.  
상속 관계의 타입들끼리만 타입 캐스팅이 가능하지만, 이를 사용할 경우 상속관계가 아니어도 타입 캐스팅이 가능하다.  
Any는 모든 타입, AnyObject는 클래스 타입만 할당 가능하다.
</details>
<details>
<summary>확장의 개념과 유의점, 사용하고자 하는 경우 등을 간단하게 서술하세요.</summary>

현재 존재하는 클래스, 구조체, 열거형에 새로운 기능을 추가하는 기능입니다.  
메서드를 추가하는 것만 가능하며, 저장 속성은 추가할수 없습니다.
</details>

#### 12월 16일

<details>
<summary>클래스의 상속과 확장의 차이점을 간단히 서술하세요.</summary>

상속은 기존에 존재하는 타입을 상속받아 비슷한 형태의 새로운 타입을 생성하여 속성과 기능을 추가하는 수직확장의 형태이다.  
확장은 기존에 존재하는 타입에 기능을 추가하는 수평확장의 형태이다. 속성 추가는 불가능하다.
</details>
<details>
<summary>하위 클래스가 상속받은 저장 속성을 수정할 수 없는 이유는?</summary>

하위 클래스는 상위 클래스의 데이터 구조를 그대로 상속받는다. 상위 클래스의 데이터를 복사하지 않고 참조하여 사용하기 때문에 수정이 불가능하다.
</details>
<details>
<summary>Convenience init에 대해 설명하시오.</summary>

지정생성자보다 적은 갯수의 파라미터로 편리하게 생성하기 위한 생성자.  
편의 생성자는 지정생성자에 의존 및 호출된다.  
상속이 발생하는 경우 서브클래스에서 재정의를 할수 없다.  
편의생성자는 다른 편의생성자를 호출하거나 지정생성자를 호출해야함.
</details>
</details>
<details>
<summary>3주차 데일리 퀴즈</summary>

#### 12월 19일
<details>
<summary>고차함수 중 flatMap과 compactMap의 차이를 설명해보세요.</summary>

flatMap: 중첩된 배열을 제거하고 리턴.  
compactMap: 옵셔널 요소 제거하고 리턴
</details>
<details>
<summary>함수형 프로그래밍은 무엇인가요? Swift는 함수형 프로그래밍 언어인가요?</summary>

Swift는 미리 선언된 함수들을 선언하여 사용해 부작용이 없도록 프로그래밍이 가능한 함수형 프로그래밍이다.
</details>
<details>
<summary>High Order Function에 대해서 설명해보세요.</summary>

입력값이나 출력값이 함수인 함수를 의미한다.
</details>
#### 12월 20일
<details>
<summary>프로토콜이란 무엇이며, 프로토콜을 사용하는 이유는 무엇인가?</summary>

프로토콜은 특정 작업이나 기능에 적합한 메서드, 속성 및 기타 요구 사항의 청사진을 정의한다.  
상속의 경우 사용하지 않는 불필요한 속성과 메소드도 같이 상속되지만,  
프로토콜은 필요한 요구사항만을 채택하여 선언하고 사용할 수 있다.
</details>
<details>
<summary>스위프트가 프로토콜을 일급 객체로 취급한다는 것은 무슨 의미인가?</summary>

1. 프로토콜을 변수에 할당할 수 있음.
2. 함수 호출시 프로토콜을 파라미터로 할당 할 수 있음.
3. 함수에서 프로토콜을 반환할수 있음
</details>
<details>
<summary>mutating 키워드가 무엇인지와 그 원리를 설명하세요.</summary>

구조체의 인스턴스 메서드는 기본적으로 속성값을 변경할수 없다.  
하지만 인스턴스 메서드를 선언할 때, mutating 키워드를 붙여 선언할 경우 구조체 인스턴스의 속성 값을 변경할 수 있다.
</details>

#### 12월 21일
<details>
<summary>클로저의 캡처현상에 대해 간단히 설명하시오</summary>

클로저는 클로저 사용이 필요 없어질때까지 힙에 존재해야하고, 내부에서 외부에 존재하는 변수를 계속 사용해야 하기 때문에 캡처 현상이 발생.
</details>
<details>
<summary>강한 참조 사이클에 대해 설명해주세요</summary>

두 객체들끼리 서로를 참조해서 발생한다. 서로를 참조해서 RC가 증가하고, RC가 계속 남아있어 메모리에서 해제되지 못하고 남아있는 현상이다.
</details>
<details>
<summary>Method Dispatch가 무엇인가요? 또한, Method Dispatch의 대표적인 두가지 타입의 특징을 간략히 설명하세요.</summary>

메소드를 호출할 때 어떤 메소드를 실행할지 결정하는 과정.  
1. 정적 디스패치  
코드의 메서드 주소를 찾아서 동작. 실행속도에 큰 이점이 있음.  
2. 동적 디스패치  
참조 타입인 클래스의 메서드의 동작 방식.  
데이터에 virtual table을 만들고 메서드를 배열로 생성, 더 많은 시간과 자원이 소모.
</details>

#### 12월 22일
<details>
<summary>중첩타입이 무엇인지, 어떻게 사용하는지 간략히 설명하세요.</summary>

타입 내부의 타입을 말한다.  
자신이 속한 타입을 자신의 타입 이름과 함께 . 를 사용하여 표기.  
ex) Food.Rice
</details>
<details>
<summary>self와 Self의 차이를 설명하세요.</summary>

self는 인스턴스를 가르키고, Self는 타입을 가르킨다.  
self는 인스턴스 내부에서 인스턴스의 속성을 더 명확하게 가르키기 위해 사용한다.  
Self는 특정 타입 내부에서 타입을 선언하는 위치에 사용한다.
</details>
<details>
<summary>델리게이트 패턴을 활용하는 경우를 예를 들어 설명하시오.</summary>

델리게이트 패턴은 다른 객체에 자신이 할 일을 대리자에게 위임시키는 디자인 패턴이다.  
여러가지 상황에 대한 호출되는 메소드를 대리자 객체에서 작성하고, 실제로 상황이 발생할 경우 위임자 객체가 대리자 객체에서 작성한 메소드를 호출한다.
</details>

#### 12월 23일
<details>
<summary>Delegate와 Notification 방식의 차이점에 대해 설명하시오.</summary>

delegate: 1:1 방식, 하나의 객체애 대해 다양한 이벤트 처리에 용이.  
Notification: 1:n 방식, 다수의 객체들에게 동시에 이벤트 발생을 알려줘야 할때 사용한다. NotificationCenter 싱글턴 객체로 이벤트의 발생여부를 등록한 객체들에게 post하는 방식으로 동작한다.
</details>
<details>
<summary>unowned는 객체가 사라질 경우 crash된다. 그럼에도 unowned를 사용하는 이유는?</summary>

weak로 참조하는 객체는 옵셔널 타입으로 선언되어 nil을 반환할수 있기 때문에 계속 관찰하게 되어 unowned에 비해 리소스가 많이 소모된다.  
참조하는 객체보다 생명주기가 짧을 경우나 nil값이 확실하게 되지 않는다면 unowned 키워드를 사용하여 리소스를 절약할수 있다.
</details>
<details>
<summary>@autoclosure는 무엇이며, 그 장점을 두 가지 언급하세요.</summary>

@autoclosure 키워드를 사용 할 경우 함수의 인자로 전달된 표현식을 래핑하여 자동으로 클로저를 생성한다.  
클로저를 표현하는 중괄호 없이 표현식으로만 전달하기 때문에 코드의 가독성이 높아짐.  
내부 코드가 클로저를 호출할때까지 실행하지 않으므로 연산을 지연시켜 부작용이 있는 코드에 용이하다.

</details>
</details>