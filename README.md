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


### parameter
- positional parameter
  + 순서가 고정된 파라미터
  + 기본값은 대괄호 사용
```
int add(int a, [int b = 2]) {}
```
- named parameter
  + 이름이 있는 파라미터
  + 중괄호로 감싸서 사용
  + required 키워드로 필수값 표현
```
int divide({required int a, int b = 2}) {}
```

### typedef
- 함수의 시그니처를 정의
- 시그니처: 반환값, 타입, 매개변수 개수와 타입 등을 말함, 즉 함수 선언부
- 매개변수로 넣어서 사용 가능
```
typeof Operation = void Func(int x, int y);

void add(int x, int y){
  print('value: ${x+y}');
}
Operation op = add;
op(1, 2);
```

#### JIT(just in time)
- 변경된 코드만 컴파일해서 반영
- 핫 리로드 기능

### named constructor
- 생성자 이름 명시하고 싶을 때
```
class Idol {
  final String name;
  final int count;

Idel.fromMap(Map<String, dynamic> map)
  : this.name = map['name'],
    this.count = map['count'];
}
```

### getter setter
class Idol {
  String _name = 'test';
  String get name {
    return this._name;
  }

  set name(String name) {
    this._name = name;
  }
}

### inheritance(상속)
- extends 키워드 사용

### Override
- @Override 키워드 사용

### mixin
- 특정 클래스에 원하는 기능만 골라 넣을 수 있는 기능
```
mixin Idol2 on Idel {
  void sing() {
    print('test');
  }
}
```

### abstract
- same as Java

### Generic
```
class Cache<T> {
  final T data;

  Cache({
    required this.data,
  });
}

void main() {
  final cache = Cache<List<int>>(
    data: [1,2,3],
  );
}
```

### static
- it belongs to the class

### cascade operator
- 인스턴스의 속성이나 멤버 함수를 연속해서 사용
```
void main() {
  Idol test = Idel('test', 4)
    ...sayName()
    ...sayCount();
}
```

## Async programming

### Future
- 어떤 미래의 값을 받아올지 정하는 것
- 반환값을 한번만 받아올 때 사용
```
Future<String> name;

void main() async {
  await addNums(1, 2);
  await addNums(2, 3);
}

Future<void> addNums(int num1, int num2) async {
  print('$num1+ $num2 start');
  await Future.delayed(Duration(seconds: 3), () {
    print('$num1 + $num2 = ${num1 + num2}');
  });

  print('$num1+ $num2 end');
}

```



 
