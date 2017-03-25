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
