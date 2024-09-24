## Git 명령어 정리

### 1. Git 써보기

- `git init` : 현재 디렉토리를 Git이 관리하는 프로젝트 디렉토리로 설정하고, 그 안에 레포지토리(`.git` 디렉토리) 생성.
- `git config user.name 'codeit'` : 현재 사용자의 아이디를 'codeit'으로 설정.
- `git config user.email 'teacher@codeit.kr'` : 현재 사용자의 이메일 주소를 'teacher@codeit.kr'로 설정.
- `git add [파일 이름]` : 수정사항이 있는 특정 파일을 `staging area`에 올림.
- `git add [디렉토리명]` : 해당 디렉토리 내 수정된 모든 파일을 `staging area`에 올림.
- `git add .` : 작업 디렉토리 내 모든 수정된 파일을 `staging area`에 올림.
- `git reset [파일 이름]` : `staging area`에 올렸던 파일을 다시 내림.
- `git status` : 현재 Git이 인식하고 있는 프로젝트 관련 내용을 출력.
- `git commit -m "커밋 메시지"` : `staging area`에 있는 변경사항을 커밋으로 남김.
- `git help [커맨드 이름]` : 사용법이 궁금한 Git 커맨드의 공식 메뉴얼 출력.

### 2. GitHub 시작하기

- `git push -u origin master` : 로컬 레포지토리의 내용을 처음으로 리모트 레포지토리에 올릴 때 사용.
- `git push` : 이후 커밋된 내용을 리모트 레포지토리로 올림.
- `git pull` : 리모트 레포지토리의 최신 내용을 로컬 레포지토리로 가져옴.
- `git clone [프로젝트 주소]` : GitHub에 있는 프로젝트를 로컬로 복제.

### 3. Git에서 커밋 다루기

- `git log` : 커밋 히스토리를 출력.
- `git log --pretty=oneline` : 한 줄로 간단하게 커밋 히스토리 출력.
- `git show [커밋 아이디]` : 특정 커밋에서 어떤 변경사항이 있었는지 확인.
- `git commit --amend` : 최신 커밋을 다시 수정해서 새로운 커밋으로 만듦.
- `git config alias.[별명] [커맨드]` : 긴 커맨드에 별명을 붙여 간편하게 실행.
- `git diff [커밋 A] [커밋 B]` : 두 커밋 간의 차이 비교.
- `git reset [옵션] [커밋 아이디]` : HEAD, staging area, working directory를 리셋.
    - `--soft`: HEAD만 이동.
    - `--mixed`: HEAD와 staging area 리셋.
    - `--hard`: HEAD, staging area, working directory 리셋.
- `git tag [태그 이름] [커밋 아이디]` : 특정 커밋에 태그 붙임.

### 4. Git에서 브랜치 사용하기

- `git branch [새 브랜치 이름]` : 새로운 브랜치를 생성.
- `git checkout -b [새 브랜치 이름]` : 새로운 브랜치를 생성하고 해당 브랜치로 이동.
- `git branch -d [브랜치 이름]` : 브랜치를 삭제.
- `git checkout [브랜치 이름]` : 해당 브랜치로 이동.
- `git merge [브랜치 이름]` : 현재 브랜치에 다른 브랜치를 머지.
- `git merge --abort` : 머지 중 conflict 발생 시 작업 취소하고 이전 상태로 복구.

### 5. Git 실전 I

- `git fetch` : 리모트 레포지토리로부터 최신 커밋들을 로컬로 가져옴 (머지는 하지 않음).
- `git blame` : 특정 파일의 내용이 어떤 커밋에서 생긴 것인지 한 줄씩 표시.
- `git revert` : 특정 커밋에서 이루어진 작업을 취소하는 새 커밋을 생성.

### 6. Git 실전 II

- `git reflog` : HEAD가 가리켜왔던 커밋들의 기록 출력.
- `git log --all --graph` : 모든 브랜치의 커밋 히스토리를 그래프 형식으로 출력.
- `git rebase [브랜치 이름]` : 분기점 이후의 커밋을 이어붙여 깔끔하게 합침.
- `git stash` : 현재 작업 내용을 스택 영역에 저장.
- `git stash apply [커밋 아이디]` : 스택에 저장된 특정 작업 내용을 적용.
- `git stash drop [커밋 아이디]` : 스택에서 특정 작업 내용을 삭제.
- `git stash pop [커밋 아이디]` : 스택에 저장된 작업 내용을 적용하면서 스택에서 삭제.
- `git cherry-pick [커밋 아이디]` : 특정 커밋의 내용을 현재 커밋에 반영.

### 그 밖에 알아야 할 사실

- `git commit` : 커밋 메시지를 입력할 수 있는 텍스트 에디터 창이 열림.
- `git push`, `git pull`은 브랜치 단위로 작업.
- `git push --all` : 모든 브랜치의 내용을 리모트 레포지토리에 전송.

