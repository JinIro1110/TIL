# 1. git 설정

## 커밋 시 사용할 사용자 이름과 이메일

모든 프로젝트에 위 설정이 적용됨

```bash
git config --global user.name "name"
git config --global user.email "email"
git config --list
```

<br>

# 2. git 명령어

### 1. git 저장소 만들기

```
git init
```

.git이라는 폴더가 생성되는데 git저장소이자 git으로 추적, 관리하는 대상을 의미한다.

---

### 2. github 원격저장소와 연결

```
github add origin "link"
```

직접 github에서 원격저장소를 생성 후 명령어를 통해 로컬 저장소와 연결시킨다.

---

### 3. 새로운 파일을 stage영역에 추가 후 commit

- add는 stage 영역에 파일 추가
- commit은 stage영역의 파일을 git저장소에 추가

```
git add file1.py
git commit -m "version1"
```

---

### 4. 기존 원격저장소 가져오기

```
git clone "link"
```

---

### 5. 작업디렉토리와 stage영역의 파일들 상태 조회

```
git status
```

---

### 6. 원격저장소로부터 최신 버전의 파일들 로컬저장소에 복사

```
git pull origin main
```

---

### 7. 로컬저장소 파일들을 원격저장소에 저장

- origin = 원격저장소의 주소
- main = branch 이름

```
git push origin main
```
