# HTML 구조

### 1. 웹 문서 유형 지정

```html
<!DOCTYPE html>
```

- HTML5문서임을 알려줌

---

### 2. 웹 문서 시작

```html
<html lang="ko">
  ......
</html>
```

- 웹 문서의 시작과 끝을 알려줌

* lang은 특정언어로 제한하는 역할

---

### 3. 웹 브라우저에 문서 정보 전달

```html
<meta charset="UTF-8">
<title>HTML문서<title>
```

- meta의 중요 역할은 인코딩 알려주기
- 키워드, 간단한 설명, 제작자 등
- title은 웹 문서 제목

---

### 4. 웹 브라우저 내용

```html
<body>
  <h1>문서</h1>
  <p>HTML</p>
  <p>CSS</p>
</body>
```

- body에는 웹 브라우저 화면에서 보여주는 내용을 작성

---

### 5. 시맨틱 태그

- \<header> : 헤더 영역, 검색 창이나 사이트 메뉴
- \<nav> : 다른 위치, 문서로 연결하는 링크
- \<main> : 메인 콘텐츠(웹 문서에서 하나만 존재)
- \<article> : 신문이나 잡지의 기사처럼 독립된 웹 콘텐츠들
- \<section> : 몇 개의 콘텐츠를 묶는 용도
- \<aside> : 사이드바
- \<footer> : 맨 아래쪽 영역
- \<div> : id나 class를 이용하여 문서 구조를 만들거나 스타일 적용할 때 사용(block)

---

<br>

# 텍스트

- \<hn> : 1~6 순으로 제목으로 사용
- \<p> : 한 단락을 작성할 때 사용
- \<br> : 줄 바꿈(개행)
- \<blockqutoe> : 인용문
- \<strong>, \<b> : 굵게 표시(strong은 화면 낭독기)
- \<em>, \<i> : 기울여 표시(em은 특정부분 강조)
- \<s> : 취소선 표시
- \<u> : 밑줄 표시

---

<br>

# 목록

- \<ol> : 순서 있는 목록
  <details>
  <summary>속성</summary>

  - type = "1" : 숫자(기본값)
  - type = "a" : 영문 소문자
  - type = "A" : 영문 대문자
  - type = "i" : 로마 숫자 소문자
  - type = "I" : 로마 숫자 대문자
  </details>

- \<ul> : 순서 없는 목록
- \<dl> : 이름과 값의 형태로 된 목록
- \<dt> : 이름
- \<dd> : 값

---

<br>

# 표

- \<table> : 표의 시작과 끝
- \<caption> : 표의 제목
- \<thead> : 테이블 제목(맨 윗 항목)
- \<tbody> : 테이블 본문
- \<tfoot> : 테이블 요약
- \<tr> : 행 만들기
- \<Td> : 행 안에 셀 만들기
- rowspan="개수" : 행 합치기
- colspan="개수" : 열 합치기
- \<col> : 열 선택

---

<br>

# 이미지

- \<img src="경로" alt="텍스트"> : 경로에 존재하는 이미지 넣기
  - width, height : 이미지 너비, 높이

---

<br>

# 오디오, 비디오

- \<audio src="경로"> : 오디오 파일 넣기
- \<video src="경로"> : 비디오 파일 넣기
  <details>
  <summary>속성</summary>

  - controls : 재생하거나 정지 가능
  - autoplay : 자동 실행
  - loop : 반복 재생
  - muted : 소리 제거
  </details>

---

<br>

# 하이퍼링크 삽입

- \<a href="주소">텍스트 또는 이미지</a>
  - target="\_blank" : 새 탭에서 열기

---

<br>

# 폼 삽입하기

- 폼에 입력한 내용을 서버에 전달(데이터베이스를 기반으로 함)

* \<form [속성="속성값"]>여러 폼 요소</form>
    <details>
    <summary>속성</summary>

  - method : 서버 쪽 프로그램으로 어떻게 넘길지
    - get : 256~4096byte, 입력 내용이 그대로 드러남
    - post : 길이 제한 X, 내용 드러나지않음
  - name : 자바스크립트로 폼을 제어할 때 사용할 폼의 이름
  - action : 폼 태그 안의 내용을 처리할 서버 프로그램
  - autocomplete(="on") : 자동완성기능
    </details>

<br>

- \<label for="id">레이블명\<input id="id"></label> : 레이블의 for과 폼 요소의 id를 연결
- \<fieldset> : 폼 안에서 구역을 나누어 표시
- \<legend> : fieldset 그룹 제목

---

<br>

# input태그

<details>
<summary>type</summary>

- text : 텍스트
- password : 비밀번호
- search : 검색
- url : URL주소
- email : 이메일 주소
- tel : 전화번호
- checkbox : 체크 박스(2개 이상)
  - value : 서버에 넘겨줄 값
- radio : 1개만 선택 가능
  - radio의 name들은 통일
- number : 숫자 스핀 박스
- range : 숫자 조절 슬라이드 막대
- date : 연, 월, 일
- month : 연, 월
- week : 연, 주
- time : 시, 분, 초 등
- datetime : 국제표준 기준
- datetime-local : 사용자 지역 기준
- submit : 전송 버튼
- reset : 리셋 버튼
- image : submit 대신 사용할 이미지
</details>

* autofocus : 페이지 시작 시 자동 커서
* placeholder : 힌트 내용
* readonly : 읽기 전용
* required : 필수 입력

---

<br>

# 그 외

- \<textarea> : 텍스트 여러줄 입력
- \<select> : 드롭다운 목록
- \<datalist> : 데이터 목록
- \<option> value="값">옵션\</option>
