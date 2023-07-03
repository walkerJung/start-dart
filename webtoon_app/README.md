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

## 3. fronJson

- json 은 dynamic 타입으로 받으면 된다.
- json 정보로 초기화 해주는 model class 를 만든다.
- Future<List<WebtoonModel>> 을 api_service 에서 리턴하게 된다.