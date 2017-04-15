Android XML
===========

# Android Layout XML 기본 용어

* View(뷰) : 화면을 구성하는 일반적인 요소

* Widget(위젯) : 뷰를 정의한 후 그 중에서 컨트롤을 하는 화면 구성요소

* Layout(레이아웃) : 뷰들을 담고 있는 긋릇을 뷰그룹으로 정의한 후 그 안의 뷰들을 배치하는 역활

## Android Layout XML 기본 속성

### 뷰의 폭과 높이 설정
```
Android:layout_width="설정 부분"
Android:layout_height="설정 부분"
```
* 설정
  - match_parent : 무조건 남아있는 여유 공간을 채움
  - wrap_content : 뷰에 들어있는 내용물의 크기에 따라 뷰의 크기가 결정되도록 조정
  - 정수값 : 지정한 크기에 맞춤

### 뷰의 ID 지정
```
android:id="@+id/ "
```
* 설정
  - '@' 기호는 id를 리소스(R.java)에 정의하거나 참조한다는 뜻
  - '+'기호는 id를 새로 정의한다는 뜻, 처음 정의할 때만 붙이고 참조할 때는 붙이지 않음
  - 소문자 id는 예약어
  - '/'뒤에 원하는 이름 작성

### 뷰의 배경을 설정
```
android:background="#RGB"
```
* 설정
  - #RGB
  - #ARGB(A:Alpha, R:Red, G:Green, B:Blue)
  - #RRGGBB
  - #AARRGGBB

### 뷰를 추가하는 방향을 설정
```
android:orientation=" "
```
* 설정
  - vertical : 세로 방향으로 추가
  - horizontal : 가로 방향으로 추가

### 뷰의 정렬 반향을 설정, 뷰의 화면에 표시하는 내용물을 정렬
```
android:gravity=""
```
* 설정
  - top : 해당 위젯을 윗쪽에 위치 시킵니다. 이때 사이즈에 변화는 없습니다.
  - bottom : 해당 위젯을 하단에 위치 시킵니다. 이때 사이즈에 변화는 없습니다.
  - left : 해당 위젯을 왼쪽에 위치 시킵니다. 이때 사이즈에 변화는 없습니다.
  - right : 해당 위젯을 오른쪽에 위치 시킵니다. 이때 사이즈에 변화는 없습니다.
  - center_vertical : 해당 위젯을 세로 중앙에 위치 시킵니다. 이때 사이즈에 변화는 없습니다.
  - fill_vertical : 해당 위젯의 세로를 부모 뷰그룹의 사이즈에 맞게 늘려 채워줍니다.
  - center_horizontal : 해당 위젯을 가로 중앙에 위치 시깁니다. 이때 사이즈에 변화는 없습니다.
  - fill_horizontal : 해당 위젯의 가로를 부모 뷰그룹의 사이즈에 맞게 늘려 채워줍니다.
  - center : 해당 위젯을 정중앙에 위치 시킵니다. 이때 사이즈의 변화는 없습니다.
  - fill : 해당 위젯을 가로/세로 길이를 부모 뷰그룹의 사이즈에 맞게 늘려 채워줍니다.
  - clip_vertical : 해당 위젯의 세로 길이가 부모 뷰그룹보다 클 경우 넘어서는 부분은 잘라냅니다.
  - clip_horizontal : 해당 위젯의 가로 길이가 부모 뷰그룹 보다 클 경우 넘어서는 부분은 잘라냅니다.
  - start : 해당 위젯을 부모 뷰그룹의 시작점에 위치 시켜 줍니다. 이때 사이즈의 변화는 없습니다.
  - end : 해당 위젯을 부모 뷰그룹의 마지막에 위치 시켜 줍니다. 이때 사이즈의 변화는 없습니다.
  - 두가지 이상의 방향을 설정할 때에는 '|'를 사용하여 여러 속성값을 적용

### 뷰의 여유공간을 설정(안쪽 여백)
```
android:pandding=" "
android:panddingLeft=" "
android:panddingRight=" "
android:panddingTop=" "
android:panddingBottom=" "
```
* 설정
  - pandding 속성은 상하좌우 모든 방향에 적용
  - 각 방향의 여배을 다른 값으로 설정 가능

### 뷰와 부모와의 간격(바깥 여백)
```
android:margin=" "
```
### 뷰의 표시 유무를 결정
```
android:visibility=" "
```
* 설정
  - visible : 보이는 상태
  - invisible : 보이지 않는 상태, 자리 차지
  - gone : 보이지 않는 상태, 자리 차지 X

### 부모가 컨테이너의 여유 공간에 뷰가 모두 채워지지 않아 여유 공간 안에서 뷰를 정렬
```
android:layout_gravity=" "
```

### 키보드 포커스를 받을 수 있을지 결정
```
android:focusable=" "
```
* 설정
  - true : Default 값
  - false : 사용자의 입력을 받아야 하는 것은 이 속성의 Default값이 true로 지정

## Button 클릭 시 Button의 background 색 변경
버튼을 누르고 있는 동안 색을 바꿔주는 효과를 넣고 싶을때 사용한다.

1. res/drowable 디렉토리 안에 button_selector.xml파일 생성 후 소스 작성
  ```
  <selector xmlns:android="http://schemas.android.com/apk/res/android">
      <item android:state_pressed="true" android:drawable="@drawable/bg_select"/>
      <item android:state_focused="true" android:drawable="@drawable/bg_select"/>
      <item android:state_pressed="true" android:drawable="@drawable/bg_select"/>
      <item android:drawable="@drawable/bg"/>
  </selector>
  ```
2. res/value/colors.xml 파일에 소스 작성
  ```
  <?xml version="1.0" encoding="utf-8"?>
  <resources>
      <color name="colorPrimary">#3F51B5</color>
      <color name="colorPrimaryDark">#303F9F</color>
      <color name="colorAccent">#FF4081</color>
      <color name="colorWhite">#FFFFFF</color>
      <color name="colorBlue">#2196F3</color>
      <drawable name="bg_select">#2196F3</drawable>
      <drawable name="bg">#EEEEEE</drawable>
  </resources>
  ```

3. activity_main.xml
  ```
  <Button
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:background="@drawable/button_selector"
    android:text="ButtonTest"/>
  ```



## 참고 문서
* [초보 개발자](http://freehoon.tistory.com/entry/안드로이드-gravity-속성)
* [Azdesign™](http://azdesigntm.com/329)
* 출처: http://dutax.tistory.com/2 [Dutax의 안드로이드]
