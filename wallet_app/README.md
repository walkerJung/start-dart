# wallet_app

1. brew install --cask flutter

2. flutter create wallet_app

# Hello Flutter

- flutter 를 구성하는것은 모두 위젯이다. 위젯은 하나의 class 를 의미한다.
- 위젯의 종류는 공식문서를 찾아보자. https://docs.flutter.dev/development/ui/widgets
- 모든 위젯은 build 메서드를 사용해야하고, 이 메서드가 UI 를 그려준다.
- runApp() 에서 호출하는 root class 에서는 CupertinoApp 또는 MaterialApp 을 선택해야하는데 후자가 보기 더 좋다.
- 모든 화면은 Scaffold(구조) 를 가져야 한다. 물론 이것도 위젯이다

# UI Challenge

## 1. Header

- SizeBox 위젯으로 비어있는 공간을 만들수 있다.
- Padding 위젯을 사용하여 padding 인자에 EdgeInsets 객체를 전달하여 사용한다. padding 을 적용할 위젯은 child 인자에 전달한다

    Padding(
        padding: EdgeInsets.symmetric(horizontal: 40),
        child: Column(...)
    )

- Row 위젯과 Column 위젯에 children[] 을 전달하여 구성하고, mainAxisAlignment 와 crossAxiosAlignment 로 수직, 수평 정렬을 설정할수 있다.    

## 2. Developer Tools

- 개발자 도구를 사용하면 현재 스크린의 tree 정보부터 각각의 위젯 정보들을 확인, 조정 해볼수 있다.

## 3. Buttons Section

- Container 위젯은 HTML 의 div 와 같다.
- Container 위젯의 child 인자를 사용하여 Container 위젯 안에 넣은 위젯을 추가할수 있다.

    Container(
        child: Text('Hello Flutter'),
    )

- Container 위젯의 decoration 인자를 사용하여 디자인을 변경할수 있다.

    Container(
        decoration: BoxDecoration(
            color: Colors.white,
            borderRadius: BorderRadius.circular(45),
        ),
    )

## 4. VSCode Settings

- const 를 사용하면 유리한 부분에 const 를 자동으로 붙여줄수 있도록 settings.json 에 아래 내용을 추가한다.

    "editor.codeActionsOnSave": {
        "source.fixAll": true
    },

- 위젯의 트리 형태를 편하게 확인할수 있도록 settings.json 에 아래 내용을 추가한다.

    "dart.previewFlutterUiGuides": true
    

## 5. Code Actions

- 소스코드 리펙토링에 큰 도움을 주는 기능으로, Text 위젯을 Padding 위젯에 넣는다거나 할때 소스코드 왼쪽에 전구모양을 클릭해서 사용할수 있다. "command + ." 로 마우스 클릭 없이 열수 있다.

## 6. Reusable Widgets

- Code Actions 기능중에 Extract Widget 을 사용하면 반복적으로 사용되는 위젯을 class 로 만들어 준다.
- stl 을 입력하면 Stateless Widget 의 스니펫을 만들수 있다. 
- build 를 입력하면 build 관련 스니펫을 추가할수 있다.

## 7. Cards

- 내부에서 메서드를 사용하고 있는 위젯들은 인자들이 상수로 들어오지 않기 때문에 const 를 빼줘야 한다.

## 8. Icons and Transforms

- Icon 위젯을 사용하면 flutter SDK 에 있는 다양한 아이콘으로 아이콘을 표현할수 있다.
- Transform 위젯의 scale 을 사용하여 scale 을 설정할수 있다.
- Transform 위젯의 translate 를 사용하여 offset 을 설정할수 있다.
- Transform 위젯을 사용한 이유는 단순하게 padding, margin 값을 조정하면 Icons 를 감싸고있는 Container 크기가 늘어나기 때문이다.
- Container 위젯에 clipBehavior: Clip.hardEdge 를 사용하여 overflow: hidden 과 같은 효과를 낼수 있다.

    Container(
        clipBehavior: Clip.hardEdge
    )

## 9. Reusable Cards

- Class 에 필요한 속성들을 final 로 선언하고 Code Action 을 사용하면 쉽게 생성자 메서드를 만들수 있다.
- 부모 위젯에 영향이 가지 않도록 디자인을 변경할땐 Transform.translate() 의 Offset 을 설정하는게 좋다.
- body 에 SingleChildScrollView 위젯을 사용하면 스크롤 가능한 뷰를 사용할수 있다.

## 10. Code Challenge

- CurrencyCard 위젯에 offsetY 속성을 추가하여 해당 위젯 내부에서 offset 을 조정할수 있도록 변경하였다.