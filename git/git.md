# 대충 저장 구조

로컬 <-> 스테이지 <-> 깃저장소 <-> 깃허브

- untracked -> staged
- unmodified -> modified -> staged
- staged -> (commit) -> unmodified
- unmodified -> (remove the file) -> untracked

1. 작업디렉토리에서 파일 변경
2. stage영역에 변경한 파일들 추가
3. commit을 통해 stage영역에 올라간 파일들을 git에 반영

# 가지(Branch)

- 기존의 작업과 분리된 작업을 수행하기 위함
- 각각의 브랜치는 병합함으로써 하나의 브랜치로 모음
