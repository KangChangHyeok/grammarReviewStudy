## Sequence
```swift
protocol Sequence<Element> {
    associatedtype Element where Self.Element == Self.Iterator.Element
    associatedtype Iterator: IteratorProtocol
    func makeIterator() -> Self.Iterator
}
```
프로토콜 타입으로 선언되어 있으며, 해당 element에 대한 순차적이고 반복적인 접근을 제공하는 타입.  
즉 Sequence는 값의 리스트이고 각각의 값 하나를 element라고 한다.  

Sequence Protocol은 기본적으로 IteratorProtocol을 채택하는 Iterator이 있고,  
Iterator를 만들어 반환하는  makeIterator 함수가 있다.  
-> 즉  앞에서 말했던 Sequence의 element는 Iterator이고, Iterator은 IteratorProcotol을 채택한다.  

### IteratorProtocol
```swift
protocol IteratorProtcol {
    associatedtype Element
    mutating func next() -> Element?
}
```
IteratorProtocol은 Element라는 associatedtype을 가지고 있으며,  
Element를 반환하는 next() 함수를 가지고 있음.    

우리가 쉽게 사용하는 for- in 반복문의 동작 원리는 makeIterator() 함수를 실행하여 Iterator를 만든 후,  
Iteraotor의 next()함수를 사용하여 Seqeunce의 내용을 반복하는 것.

```swift
let family = ["나","동생","아빠","엄마"]

var familyIterator = family.makeIterator()
while let family = familyIterator.next() {
    print(family)
}
```

### Custom Sequence 만들기

```swift
struct CountDown: Sequence {
    let startNumber: Int
    
    func makeIterator() -> CountDownIterator {
        return CountDownIterator(count: self.startNumber)
    }
}

struct CountDownIterator: IteratorProtocol {
    var count: Int
    mutating func next() -> Int? {
        guard count != 0 else { return nil }
        defer {
            count -= 1
        }
        return count
    }
}

let oneTwoThree = CountDown(startNumber: 3)

for i in onetwothree {
    print("\(i)")
}
```
Sequence 프로토콜을 채택하는 CountDown 구조체 선언.   
첫 카운트 숫자인 startNumber를 선언하고 Iterator타입을 반환하는 makeIterator() 함수 선언.  

IteratorProtocol을 채택하는 CountDownIterator선언.(makeIterator()함수의 반환되는 값).  
값이 0 이 될 경우 next() 함수 종료.(next()함수의 종료는 nil값 반환).  

### Custom Seqeunce 만들기(nested Type)

```swift
struct CountDown: Sequence, IteratorProtocol {
    typealias Element = Int
    
    var startNumber: Int
    
    mutating func next() -> Int? {
        guard startNumber != 0 else { return nil}
        defer {
            startNumber -= 1
        }
        return startNumber
    }
    
}

let oneTwoThree = CountDown(startNumber: 3)

for i in oneTwoThree {
    print(i)
}
```

자기 자신이 Iterator가 되기 때문에 makeIterator() 함수를 구현하지 않아도 된다.   
next() 함수만 선언해준다면 기존의 Seqeunce와 똑같은 기능을 하는 함수를 만들 수 있음.