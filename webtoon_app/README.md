# webtoon_app

1. flutter create webtoon_app

## 1. AppBar

- Scaffold 에 appBar 를 추가하여 HomeScreen 화면 구성

## 2. Data Fetching

- pubspec.yaml 파일에 프로젝트를 구성하고 있는 여러가지 의존성 정보와 설정 정보를 가지고 있다.
- pubspec.yaml 에 직접 의존성버전을 추가해도 되고, cli 로 명령어를 입력해도 된다.
- http.dart 의존성 설치 후 api 요청을 할수 있다.
- js 와 마찬가지로 async 함수 내에서 await 를 사용할수 있다.
- Future 타입과 async/await 는 같이 쓰인다고 볼수 있다.

## 3. fromJson

- json 은 dynamic 타입으로 받으면 된다.
- json 정보로 초기화 해주는 model class 를 만든다.
- Future<List<WebtoonModel>> 을 api_service 에서 리턴하게 된다.

## 4. api request/response recap

- service 파일을 만든다.
- pub.dev 에서 http 의존성을 설치한다.
- api server 에 http 요청을 보낸다.
- api 요청은 Future 타입 이므로 작업이 끝날때까지 기다린다. (Future 을 기다리기위헤 async/await 를 사용)
- 완료되면 Response 타입을 반환한다.
- 반환반은 response 의 statusCode 를 확인하고, body 에 데이터를 확인한다.
- response(JSON) 으로 Model 을 만든다. json 의 타입은 선언 안해도 되지만 List<dynamic> 이다.
- response.body 를 for in 으로 돌려서 Model 생성자에 전달해준다.
- 각각의 인스턴스들을 add() 해서 리턴해준다.

## 5. waitForWebToons

- 데이터를 불러올 화면에서 initState 를 사용하여 ApiService 를 호출한다.
- ApiService 를 호출할때에도 당연히 async/await 를 사용해야한다.
- 데이터 로드가 끝나면 setState 를 사용하여 다시 랜더링 시킨다.

## 6. FutureBuilder

- Scaffold 에 FutureBuilder 위젯을 사용하면 initState 와 setState 를 사용하지 않고 data fetching 을 할수있다.
- FutureBuilder 는 Future 의 값을 기다리고 데이터가 존재하는지 알려준다.
- 데이터 관련 Service 를 호출해서 변수에 할당한다.
- FutureBuilder 의 future 에 해당 변수를 인자로 넘겨준다.

    FutureBuilder(
        future: webtoons
    )

- FutureBuilder 의 builder 메서드를 사용하여 데이터를 랜더링한다. snapshot 은 Future 의 상태를 의미한다.

    FutureBuilder(
        builder: (context, snapshot) {
            If(snapshot.hasData){}
        }
    )

## 7. ListView

- Listview 의 builder 를 사용하면 Row 나 Column 보다 리스트를 구현하는데 편하다.
- builder 를 사용하면 실제 뷰에 보이는것들만 렌더링하게 된다.
- separatorBuilder 는 아이템들 사이사이에 구분자를 넣어주는데 다양한것들이 들어간다.

## 8. Webtoon Card

- ListView 위젯에 padding 을 줄수 있다.
- 부모, 자식 위젯이 관여될 경우 clipBehavior: Clip.hardEdge 를 사용하면 된다.
- Container 의 decoration 에서 BoxDecoration boxShadow 를 설정할때 눈에 띄는 못생긴 색으로 먼저 진행하는게 확인하기 편하다.

## 9. Detail Screen

- GestureDetector 위젯을 사용하면 사용자의 행동에 따른 이벤트를 추가할수 있다.
- onTap 안에 Navigator 위젯을 사용하여 화면 전환을 할수 있다.
- MaterialPageRoute 의 builder 를 사용해서 보여줄 위젯을 선택할수 있다.

    MaterialPageRoute(
        builder: (context) => DetailScreen(),
        fullScreenDialog: true,
    )

- fullScreenDialog: true 를 설정하면 아래에서 올라오는 팝업 형식으로 화면 이동이 된다. 이 설정에 따라 아이콘이 뒤로가기, 닫기 로 보여진다.

## 10. Hero

- Hero 위젯을 사용하면 해당 부분을 floating 시켜놓는것과 같은 효과를 줄수있다.
- Hero 위젯은 두 화면 사이에 애니메이션을 주는 기능을 담당한다.

## 11. ApiService

- List 안에 Model 을 넣어 반환할때의 리턴 타입 설정을 항상 주의하자.