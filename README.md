# Dart Variables

## Dart 는 "Type" 또는 "var" 로 변수를 선언한다.

    int i = 33;
    var name = "junghoon";

- 변수의 값은 모두 재할당이 가능하다. 단, type 이 맞는 범위에서
- 함수나 메서드 안에서 변수 선언은 주로 var 를 사용하길 권장한다.
- class 의 변수나 프로퍼티를 선언할땐 type 을 사용하길 권장한다.

## Dart 에서 변수의 값을 수정하지 못하게 하는 방법은 "final" 을 사용하면 된다.

    final age = 33;

## Dart 에서 변수에 여러 종류의 값을 할당하려면 "dynamic" 을 사용하면 된다.

    dynamic something;
    something = 'junghoon';
    something = 33;

## Dart 에서 "final" 과 "const" 는 다른 의미이다. 그리고 두개 다 수정할수 없다.

- const 는 compile-time 상수로써 api_key 값 같이 컴파일 하기전에 알수있는 변수를 선언할때 사용한다.
- final 은 앱이 실행되고 나서 알수 있는 값들 ( form 의 값, api call result 등 ) 을 선언할때 사용한다.

## Dart 는 null safety 라는 성질이 있어서 null 을 참조하지 못하게 한다.

    String? name = 'nico';
    name = null;

- 하지만 type 뒤에 ? 를 사용하여 null 이 올수있도록 할수 있다.

## Dart 에서 어떤 값이 할당될지 모르는 변수에는 late 를 사용해주면 된다.

    late final String name;
    name = 'junghoon';

- late 는 final, var, String 같은 것들 앞에 써줄수 있다.
- late 를 사용하면 변수를 사용하기전에 값이 할당되었는지 확인해준다.

# Dart Data Types

## Dart 는 객체지향 언어다.

- 모든 type 이 object / class 다.

## Dart 의 List

    var example = [1,2,3,4, for(var i in example2) "$i"];
    var example = [1,2,3,4, if(true) 5,];

- List 의 마지막 요소에 , 를 붙여주면 자동 정렬이 된다.
- List 에 collection if 라는 편리한 기능이 있다. List 속에 분기처리를 할수 있다.
- List 에 collection for 이라는 편리한 기능이 있다. List 속에서 for 문을 돌릴수 있다.

## Dart 의 String Interpolation

- 문자열 속에 $변수 형태로 사용할수 있다. ( 큰따움표, 작은따움표 모두 동일 )
- 계산이 필요한 변수는 ${변수 + someting} 으로 사용할수 있다.

## Dart 의 Map

    var example = {1: true, 2: true, 3: false};
    Map<int, bool> example = {1: true, 2: true, 3: true};
    Map<List<int>, bool> example = {[1,2,3,4]: true};
    List<Map<String, Object>> example = [
        {'name': 'junghoon'},
        {'age': 33}
    ]

- 기본적으로 key:value 로 구성된 object 이다.
- Object 에는 모든 타입이 올수 있다.
- key:value 의 object 가 일정한 형태를 띄고 있다면 map 보다 class 를 사용하는게 더 좋다.

## Dart 의 Set

    var numbers = {1, 2, 3, 4};

- key:value 형태가 아닌 객체라고 이해하면 된다.
- 요소가 항상 하나씩만 있어야 되면 set 을 사용한다.
- unique 할 필요가 없다면 list 를 사용한다.

# Dart Function

## Dart 의 Position Parameter

    String sayHello(String name){
        return "Hello I am $name"
    }

    String sayHello(String name) => "Hello I am $name";

- Dart 는 함수명 앞에 리턴 타입을 정의할수 있다.
- Dart 는 파라미터 앞에 타입을 정의할수 있다.
- 화살표 함수를 사용하여 함수를 축약할수 있다.
- 파라미터의 순서가 중요하다.

## Dart 의 Named Parameter

    String sayHello({String name = "junghoon", required Int age}){
        return "Hello I am $name, $age";
    }

    void main(){
        print(sayHello(name : "walkerJung", age: 33))
    }

- Dart 함수에서 파라미터가 많아질 경우 선언부에서 객체형태로 파라미터를 묶어줄수 있다.
- Dart 함수에서 파라미터에 꼭 값이 들어와야 하는 경우 required 를 선언해주거나, 기본값을 지정해줄수 있다. (null 을 참조하지 않기때문)
- 파라미터의 순서는 중요하지 않다.

## Dart 의 Optional Positional Parameter

    String sayHello(String name, Int age, [String? country = "korea"]){
        return "Hello I am $name, $age, from $country";
    }

    sayHello("junghoon", 33);

- Dart 함수에서 position parameter 를 사용할때 사용할수 있는 문법이다.
- 필수 파라미터가 아니라면 대괄호로 묶어주고 타입 뒤에 ? 를 추가해주고 기본값을 할당해주는 식으로 사용할수 있다. (보통은 named parameter 형식을 선호함)

## Dart 의 QQ Operator

    String sayHello(String name){
        name ??= "junghoon";
        return name;
    }

- 삼항연산자 처럼 ?? 를 기준으로 true 일 경우 왼쪽, false 일 경우 오른쪽에 있는 값을 리턴한다.
- ??= 는 좌항이 null 일경우 = 우측에있는 값을 할당한다.
- Dart 의 null safety 와 관련있는 문법이다.

## Dart 의 typedef

    typedef UserInfo = Map<String, String>;

    String userInfo(UserInfo data){
        return "${data["name"]}";
    }

    userInfo({"name":"junghoon"});

- 구조화되지 않은 간단한 데이터의 타입을 정의할때 사용한다. (구조화된 데이터는 주로 클래스를 사용)
- 타입스크립트와 비슷하다.

# Dart Class

## Dart 의 Constructor

- Dart 에서 생성자 함수를 만들땐 Class 명과 똑같은 이름을 사용한다.

    Class Player {

        final String name;
        Int xp;

        Player(String name, Int xp){
            this.name = name;
            this.xp = xp;
        };
    }

- Class 가 너무 커질경우 생성자 함수를 파라미터 순서에 따라 축약할수 있다.

    Class Player {

        final String name;
        Int xp;

        Player(this.name, this.xp);
    }

- 생성자 함수를 다양하게 만들수 있다. 위에서 설명한 Named Parameters, Positional Parameters 를 사용할수 있고, 이런식으로 여러개의 생성자 함수를 만들 경우에는 : 을 사용하여 해당 라인에서 객체를 초기화 하도록 할수 있다.

    Class Player {

        final String name;
        Int xp;

        Player(this.name, this.xp);

        Player.createHuman({required String name, required Int xp}) : this.name = name,
          this.xp = xp, 
          this.tribe = 'human',

        Player.createMonster(String name, Int xp) 
        : this.name = name,
          this.xp = xp,
          this.trice = 'monster',

    }