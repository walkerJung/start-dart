# toonflix

1. brew install --cask flutter

2. flutter create toonflix

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

## 3. Buttons Section

## 4. VSCode Settings

## 5. Code Actions

## 6. Reusable Widgets

## 7. Cards

## 8. Icons and Transforms

## 9. Reusable Cards

## 10. Code Challenge