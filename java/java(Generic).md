# 1. 제네릭 사용 목적

- 타입 안정성
  - 타입 캐스팅 필요 없음
  - 강한 타입 체크
- 매개변수화 타입(Parameterized type)

# 2. 제네릭 - 클래스, 인터페이스
```java
class 클래스이름<T>{
}  

interface 인터페이스이름<T>{
}
```

# 3. 제네릭 - 메서드
```java
<T1, T2, ..., TN> 반환타입 메소드이름(P1, P2, ..., PN);
```

# 4. 타입 제한 
```java
<P extends 부모타입>
```

부모타입을 포함한 부모타입의 하위 클래스(상속 받은 클래스)만 올 수 있다.

