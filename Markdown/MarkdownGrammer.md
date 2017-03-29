Markdown 작성법
================

# Markdownd이란?
-Markdown은 일반 텍스트 문서의 양식을 편집하는 문법이다. 특수기호와 문자를 이용하여 매우 간단한 구조의 문법을 사용하여 설치방법, 소스코드 설명, 이슈 등을 간단하게 기록하여 가독성을 높일 수 있다. github를 사용하는 사람이라면 쉽게 접할 수 있다.(README.md작성)

## Markdown 장-단점
### 장점
        1. 간단하고 간결함
        2. 별도의 도구(Tool)없이 작성가능
        3. 다양한 형태로 변환 가능
        4. 텍스트(Text)로 저장되어 용량이 적어 보관 용이함
        5. 텍스트파일이기 때문에 버전관리시스템을 이용하여 변경이력 관리 가능
        6. 지원하는 프로그램과 플랫폼이 다양        
### 단점
        1. 표준이 없다.
        2. 표준이 없기 때문에 도구에 따라서 변환방식이나 생성물이 다르다.
        3. 모든 HTML 마크업을 대신하지 못한다.

****
# Markdown 문법(사용법)

## Headers 헤더
* 주 제목 : 문서 제목
   ```
   Markdown 주 제목
   =============
   ```
   * 결과

   Markdown 주 제목
   =============

* 부 제목 : 문서 부제목
   ```
   Markdown 부 제목
   ----------------
   ```
   * 결과

   Markdown 부 제목
   -----------------

* 글머리 : 1~6까지만 지원
```
# 1번째로 큰 글머리
## 2번째로 큰 글머리
### 3번째로 큰 글머리
#### 4번째로 큰 글머리
##### 5번째로 큰 글머리
###### 6번째로 큰 글머리
```

* 결과
# 1번째로 큰 글머리
## 2번째로 큰 글머리
### 3번째로 큰 글머리
#### 4번째로 큰 글머리
##### 5번째로 큰 글머리
###### 6번째로 큰 글머리

## BlockQuote 인용
이메일에 사용하는 ```>```블럭인용문자를 사용한다.
```
> 이 것은 인용이다.
```
* 결과

> 1번째 인용(BlockQuote)
>	> 2번째 인용(BlockQuote)
>	>	> 3번째 인용 (BlockQuote)

BlockQuote안에 Markdown 요소 포함 가능
> ###제목
> * list
>     ```   
>     code
>     ```

## List 목록
### 순서있는 목록(번호)
```
1. 첫번째
2. 두번째
3. 세번째
```
결과  
1. 첫번째
2. 두번째
3. 세번째

**현재까지는 어떤 번호를 입력해도 순서는 내림차순으로 정의됨**
```
1. 첫번째
3. 세번째
2. 두번째
```
1. 첫번째
3. 세번째
2. 두번째

### 순서없는 목록(글머리기호)
```
* 빨강
* 녹색
* 파랑

+ 빨강
+ 녹색
+ 파랑

- 빨강
- 녹색
- 파랑
```
* 빨강
* 녹색
* 파랑

+ 빨강
+ 녹색
+ 파랑

- 빨강
- 녹색
- 파랑

**혼합해서 사용하는 것도 가능**
```
* 1단계
	- 2단계
    	+ 3단계
			= 4단계
```
* 1단계
	- 2단계
    	+ 3단계
			= 4단계

## code 코드 ```<pre><code></code></pre>```
4개의 공백 또는 하나의 탭으로 들여쓰기를 만나면 변환되기 시작하여 들여쓰지 않은 행을 만날때까지 변환이 계속된다.
```
 void main(void){
    printf("HelloWorld");
return 0;
}    
```
실제로 적용하면,
void main(void){

  printf("HelloWorld");
return 0;
}    
## 수평선 ```<hr/>```
아래 줄은 모두 수평선을 만든다. 마크다운 문서를 미리보기로 출력할 때 *페이지 나누기* 용도로 많이 사용한다.
```
* * *

***

*****

- - -

---------------------------------------
```

## 링크 Link
* 인라인 링크
```
syntax: [Title](link)
```
Link: [Google](https://google.com, "google link")

* 자동연결
```
<https://google.com>
<yckim4g@gmail.com>
```
<https://google.com>
<yckim4g@gmail.com>

* 참조링크
```
[link keyword][id]
[id]: URL "Optional Title here"

Link: [Google][googlelink]
[googlelink]: https://google.com "Go google"
```
Link: [Google][googlelink]
[googlelink]: https://google.com "Go google"

## 강조 Highlight
```
*single asterisks*
_single underscores_
**double asterisks**
__double underscores__
++underline++
~~cancelline~~
```
*single asterisks*

_single underscores_

**double asterisks**

__double underscores__

++underline++

~~cancelline~~

## 이미지 Image
```
![Alt text](/path/to/img.jpg)
![Alt text](/path/to/img.jpg "Optional title")
```
![마크다운 로고](https://upload.wikimedia.org/wikipedia/commons/4/48/Markdown-mark.svg)
![마크다운 로고](https://upload.wikimedia.org/wikipedia/commons/4/48/Markdown-mark.svg "마크다운로고")

사이즈 조절 기능은 없기 때문에 ```<img width="" height=""></img>```를 이용

## Markdown 편집기
### 윈도우(Window)용 편집기
* 마크다운 패드 2(MarkdownPad 2)<http://markdownpad.com/>
### 맥(OS X)용 편집기
* 모우 포 맥(Mou for Mac)<http://25.io/mou/>
### 아이폰, 아이패드(ios)용 편집기
* 라이트 앱 포 ios(Write App for ios)

아이폰 버전<https://itunes.apple.com/kr/app/write-for-iphone-a-note-taking-and-markdown-writing-app/id587363157?mt=8&ign-mpt=uo%3D4>

아이패드 버전<https://itunes.apple.com/kr/app/write-for-ipad-a-note-taking-and-markdown-writing-app/id638171770?mt=8&ign-mpt=uo%3D4>
### 안드로이드(Android)용 편집기
* 라이터(Writer)<https://play.google.com/store/apps/details?id=com.jamesmc.writer>
### 웹사이트형(Web) 인터넷 편집기
* 스택 에디터(StackEdit)<https://stackedit.io/editor>

# 정리
마크다운은 기본문법만 알고  있다면 일반 텍스트편집기에서 손쉽게 작성이 가능한 마크업언어이다. 현재 다양한 도구와 플랫폼에서 지원하고 있기 때문에 더욱 손쉽게 스타일적용된 문서를 작성할 수 있기 때문에 널리 사용되고 있다.


## 참고문서
* [깃허브 마크다운 Markdown 작성법](https://gist.github.com/ihoneymon/652be052a0727ad59601)
* [마크다운 위키키백과](https://ko.wikipedia.org/wiki/%EB%A7%88%ED%81%AC%EB%8B%A4%EC%9A%B4)
* [서지스원@IT.블로그 매거진](http://sergeswin.com/1013)
