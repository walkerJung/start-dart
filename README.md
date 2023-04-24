## Dart 는 "Type" 또는 "var" 로 변수를 선언한다.

- `int i = 33;`
- `var name = "junghoon";`
- 변수의 값은 모두 재할당이 가능하다. 단, type 이 맞는 범위에서
- 함수나 메서드 안에서 변수 선언은 주로 var 를 사용하길 권장한다.
- class 의 변수나 프로퍼티를 선언할땐 type 을 사용하길 권장한다.

## Dart 에서 변수의 값을 수정하지 못하게 하는 방법은 "final" 을 사용하면 된다.

- `final age = 33;`

## Dart 에서 변수에 여러 종류의 값을 할당하려면 "dynamic" 을 사용하면 된다.

- `dynamic something;`
- `something = 'junghoon';`
- `something = 33;`

## Dart 에서 "final" 과 "const" 는 다른 의미이다. 그리고 두개 다 수정할수 없다.

- const 는 compile-time 상수로써 api_key 값 같이 컴파일 하기전에 알수있는 변수를 선언할때 사용한다.
- final 은 앱이 실행되고 나서 알수 있는 값들 ( form 의 값, api call result 등 ) 을 선언할때 사용한다.

## Dart 는 null safety 라는 성질이 있어서 null 을 참조하지 못하게 한다.

- 하지만 type 뒤에 ? 를 사용하여 null 이 올수있도록 할수 있다.
- `String? name = 'nico';`
- `name = null;`

## Dart 에서 어떤 값이 할당될지 모르는 변수에는 late 를 사용해주면 된다.

- late 는 final, var, String 같은 것들 앞에 써줄수 있다.
- late 를 사용하면 변수를 사용하기전에 값이 할당되었는지 확인해준다.
- `late final String name;`
- `name = 'junghoon';`
