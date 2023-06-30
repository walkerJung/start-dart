# pomodoro_app

1. flutter create pomodoro_app

## 1. User Interface

- Flexible 위젯을 Column 이나 Row 안에 넣어서 flex 속성을 건드리며 사용하면 편하다.
- Expanded 위젯을 사용하면 확장시킬수 있다.
- 유저 인터페이스 같은경우 theme 속성에 필요한 것들을 미리 정의하고, build context 에서 꺼내서 사용했다.

## 2. Timer

- import 'package:flutter/material.dart'; 를 가져오면 Timer 를 사용할수 있다.
- 변수 선언시 late 를 사용하여 필요할때 초기화를 진행하도록 한다.
- Timer 의 periodic 메서드를 사용하여 반복할 시간과 콜백함수를 넘겨줄수 있다. 콜백함수 인자에 필수로 Timer 를 전달해야 한다.

## 3. Pause Play

- Timer 의 cancel 메서드를 사용하여 타이머를 정지시킬수 있다.
- isRunning 이라는 bool 속성을 추가하여 setState 메서드로 관리하고, 속성에 맞는 UI 를 랜더링하고 이벤트를 바인딩한다.