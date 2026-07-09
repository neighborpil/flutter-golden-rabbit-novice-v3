Practice
---------------------
# Grammer

- final: 런타임 상수
- const: 빌드타임 상수
- var: 변수 선언시 사용, 타입 추론 한번 하면 그 이후에 값이 안바뀜
- dynamic: 변수 선언시 사용, 변수의 타입이 바뀌어도 저장 가능
- 변수 타입 명시
  + String
  + int
  + double
  + bool
- Collections
  + List
    - List<String>
    - .reduce(): 같은 타입 반환
    - .fold<type>(): 다른 타입 반환 가능
  + Map
    - Map<String, String>
  + Set
- enum
- null 타입
  + 값이 없음을 뜻함
  + 타입을 명시해야 함
```
double number1 = null; # compile error
double? number2 = null;
```

### 타입 비교
```
number1 is int
number1 is! int
