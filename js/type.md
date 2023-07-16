# Number

- 자바스크립트는 숫자라는 타입을 가짐
- 양수, 음수, 정수, 소수 모두 포함
- NaN(Not a Number)은 숫자

---

<br>

# Variable

```js
let year = 2023;
var year = 2023;
const year = 2023;
```

- var : 전역, 함수 범위(재선언 가능)
- let : 블록 범위(재선언 불가)
- 한 변수에 값을 저장하고 사용
- const : 상수

---

<br>

# boolean

- true, false

---

<br>

# String

```js
let name = "SangHyeok";
"lol".length; // 3
```

- "", ''으로 가능
- .length 시 길이 리턴

---

<br>

# Array

```js
var season = ["봄", "여름", "가을", "겨울"];
```

<details>
<summary>메소드</summary>

1. concat : 배열 2개 합치기

2. join : 배열 안의 요소를 합쳐 문자열로

3. push, unshift : 새로운 요소 추가

4. pop, shift : 배열에서 요소 꺼내기

5. splice : 원하는 위치에 요소 추가, 삭제

6. slice : 기존 배열을 바꾸지 않으면서 요소를 꺼내기

---

<br>

# ==, ===

### ==

서로 다른 유형의 두 변수를 비교

### ===

'값 and 자료형'을 비교
