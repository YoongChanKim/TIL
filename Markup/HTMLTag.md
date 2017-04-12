HTML 태그 정리
=============

## div tag
div는 division의 영문의 약자로 __분활 하다__ 또는 __영역을 나누다__. 라는 뜻을 가지고 있다. 또한 완벽한 하나의 독립된 영역을 기본 성질로 가지고 있어 레이아웃을 나눌때 주로 사용된다.

* 문법

  ```<div>넣고 싶은 내용</div>
  ```
* 예시
  ```  
  < div id="Layer" style="position:absolute;top:20px;left:20px;
  width:200px;height:100px;z-index:1;visibility:hidden;
  overflow:auto;background:#ffcc00">
  ```
* 속성
  - position : absolute(절대위치), relative(상대위치)
  - top : 브라우저 위에서 부터 아래쪽으로 떨어진 위치
  - left : 브라우저 왼쪽에서 부터 오른쪽으로 떨어진 위치
  - width : 레이어 가로 길이
  - height : 레이어 세로 길이
  - visibility : hidden(레이어 숨김), visible(레이어 보임)
  - background : 레이어 배경색
  - overflow :
      + visible : 정해진 크기 무시(width, height를 무시하고 모두 보여줌)
      + scroll : 수평,수직 스크롤을 보여준다.
      + auto : 내용이 넘치는 방향으로 스크롤을 보여준다.
