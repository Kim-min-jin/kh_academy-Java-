# 1.1. 클래스
- 클래스 선언
```java

```
접근지정자(Access Modifier) : 
  - private : 스코프(scope)가 클래스 내부
  - public : 스코프가 전체
  - ---------------
  - default : 같은 패키지 내부(하위 클래스 X)
  - protected   

한정자(modifier):
    - static : 클래스에 소속 
    - final : 확장/변경 불가능 선언
      - 상속 불가능
    - abstract : 추상 클래스/메소드

클래스 : 
    - 필드(멤버 변수)
    - 메소드
  
## 1.2. 클래스 상속

class 자식클래스이름 exten ds 부모클래스 {

}

상속을 코드 재사용 용도로 X
상속은 타입 계층 구조화

코드 재사용
    - 합성해서 (다른 객체의 멤버가)

## 1.3. 인터페이스, 추상클래스의 목적

- 공통된 약속
  - 메세지를 수신 받은 객체가 하기로 한 것.

차이점 
    - 인터페이스 : 약속 뿐
    - 추상클래스 : 구현된 메서드가 존재할 수 있음

list.size();
- ArrayList
- LinkedList

## 1.4. 추상 클래스
```java
abstract 클래스이름 {
    //abstract 메소드선언();
    //혹은 구체적인 구현
}
```

## 1.5. 인터페이스
```java
interface 인터페이스 이름{
    메서드형태
}
```

## 1.6. enum
enum 열거형이름 {
    값1, 값2, 값3, ..., 갑수
}

열거형이름 변수이름 = 


# 스택 프레임
- 메서드 호출 시 스택 프레임이 생성 됨
- 스택 프레임 내부 :
  - 지역변수(메소드 중괄호 안에서 유효한 변수들)
    - 원시타입(int, long, float, double, ...)
    - 참조값

# 힙
- 생성된 객체가 존재

# 객체
- 참조 횟수(레퍼런스 카운트)
  - 레퍼런스 카운트가 0이 되면 JVM이 제거해줌
    - GC(garbage collection)

# JVM 메모리 구조

검색 : jvm memory layout

-young generation
    - 최근에 생성된 객체가 머무는 곳
    - minor gc - young generation을 청소하는 것 
    - 청소 빈도 높음
-old generation
    - young generation에서 살아남은 친구들이 이곳으로 이동함
    - major gc - old generation 영역 청소
    - 청소 빈도 낮음
    - 

# 상속
- 멤버 변수 
  - private인 경우 상속 안됨
  - 부모 클래스 멤버 변수와 이름이 동일한 경우 상속 안됨
  
- 메서드
Sub - Super - Object

# 싱글톤
## 생성하는 방법
- 외부에서 생성 불가능하게 막아야함 -> private 생성자
- 인스턴스를 외부로 공개 : getInstance()

## 사용목적
- 메모리 절약
- 시스템에서 하나만 있어도 되는 모듈들


# 4 tier 
- domain(entity): 비지니스 로직
- service : repository, domain, controller 통합
- controller : 뷰, 사용자 요청 등
- repository(persistence) : 데이터 저장 장소


