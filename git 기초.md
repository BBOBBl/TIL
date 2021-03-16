# git 기초

> 분산버전 관리시스템(DVCS) (>띄어쓰기)

## 로컬저장소 설정

```bash
$ git init
Initialized empty Git repository in C:/Users/baymax/Desktop/정리/.git/
(master)$
```

.git 폴더가 생성되고 여기에 git과 관련된 정보들이 저장

## 기본작업흐름

모든 작업은 touch 명령어를 통해서 파일을 만드는것으로 대체

### 1. add

```bash
$ git add 디렉토리
$ git add a.txt # 특정파일
$ git add folder #특정폴더
$ git add a.txt b.txt #특정 파일들
$ git add . #현재 디렉토리
```

* 커밋대상 파일 목록에 추가한다
  * working directory(첫번째통)의 변경사항을 staging area(둘째통) 상태로 변경

### add이전

```bash
$ touch new.txt
$ git status
On branch master

No commits yet
# git으로 관리된적 없는 파일(새파일)
Untracked files:
	# 포함시키기 위해서는 git add 명령어를 사용
	# 커밋이 될것
	# => 두번째통에 담기 위해
  (use "git add <file>..." to include in what will be committed)
  #파일 목록
        new.txt
# SA X (스테이징 아리아)
# WD O (워킹 디렉토리)
nothing added to commit but untracked files present (use "git add" to track)
```

### add 이후

```bash
$ git add .
$ git status
On branch master

No commits yet
# 커밋될 애들 staging area
Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   new.txt
```

### 2. commit

```bash
$ git commit -m 'Add new.txt
[master (root-commit) 9f94e46] Add new.txt
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 new.txt
```

* commit 지금 파일상태를 스냅샷
* 커밋 메시지는 코드 변경사항을 충분히 나타낼수 있도록 작성
* 아래의 명령어를 통해 지금까지 기록된 커밋 확인가능

### log

```bash
$ git log
commit 9f94e46bdfe7b51950f8434ec97eea4728d3a967 (HEAD -> master)
Author: JUN <seohj109@gmail.com>
Date:   Tue Mar 16 15:08:21 2021 +0900

    Add new.txt
$ git log --oneline
9f94e46 (HEAD -> master) Add new.txt
$ git log -1
Author: JUN <seohj109@gmail.com>
Date:   Tue Mar 16 15:08:21 2021 +0900

    Add new.txt
$ git log --oneline -1
9f94e46 (HEAD -> master) Add new.txt
```

