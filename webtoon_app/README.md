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