# statefull_widgets

1. brew install --cask flutter

2. flutter create statefull_widgets

## 1. State

- Stf 를 입력하면 StatefulWidget 의 스니펫이 제공된다.

## 2. setState

- setState 메서드는 새로운 State 와 함께 UI 가 다시 build 되도록 한다.
- 꼭 setState 메서드 안에 데이터를 넣어야 할 필요는 없지만, 가독성때문에 메서드 안에 state를 넣는다

## 3. BuildContext

- BuildContext 는 위젯의 트리형태를 제공한다. 어떤 위치의 위젯에서든 빌드된 위젯 트리 정보를 제공받아서 사용할수 있도록 한다.
- theme 에 자주쓰는 스타일들을 저장해놓고 한번에 불러와서 사용할수도 있다.

## 4. Widget Lifecycle

- 위젯들은 initState() -> build() -> dispose() 의 생애주기를 가진다.
- initState() 는 build() 되기 전에 실행되며 주로 api call 을 한다.
- build() 는 필요한 데이터와 함께 위젯 렌더링을 담당한다.
- dispose() 는 위젯이 사라질때 실행되며 이벤트 리스너 구독 취소 등의 역할을 담당한다.