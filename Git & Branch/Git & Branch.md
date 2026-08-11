### Git 정의

> Git은 분산 버전 관리 시스템(DVCS,Distributed Version Control System)으로 소스 코드의 변경사항을 추적하고 **개발자들이 협업할 수 있도록 돕는 기구**다. 주로 소프트웨어 개발에 사용되지만, 버전 관리를 필요로 하는 모든 프로젝트에 사용할 수 있다.

<callout icon="📌" color="gray_bg">

	**Git 주요 기능**

	- **버전 관리**

	소스 코드의 변경 이력 관리<br>이전 버전으로 돌아가거나 특전 버전 확인<br>

	- **분산형 시스템**

	모든 개발자가 전체 프로젝트의 히스토리를 복사해 로컬 저장소에 저장<br>중앙 서버가 없어도 작업할 수 있고 인터넷 연결 없이도 로컬에서 커밋하고 브랜치를 생성할 수 있다.<br>

	- **브랜치와 병합**

	독립된 작업을 위해 브랜치를 생성할 수 있다.<br>브랜치를 이용해 새로운 기능 개발, 버그 수정, 완료 작업 메인 브랜치 병합 등을 할 수 있다.<br>

	- **다양한 협업 워크플로우**

	여러 명의 개발자가 동시에 작업할 수 있다.<br>풀 리퀘스트(Pull Request)를 통해 코드 리뷰와 협업할 수 있다.

</callout>

### **\*Git & Branch 명령어 요약** {toggle="true"}
	```javascript
// 전역설정
git config --global user.email "your email"
git config --global user.name "your nickname"

// 전역설정 삭제
git config --global --unset user.name
git config --global --unset user.email

// 전역설정 확인
git config --list 
git config --global --list

// 초기화
git init

// 저장 명령어
git add *                   // WD → SA add
git commit -m "log message"  // SA → repo commit

// 확인 명령어
git reflog         // 전체 로그 확인
git log            // 로그 확인
git log --oneline  // 한줄 단축 로그 확인

// WD와 SA의 상태 확인 
git status

// 되돌리기
git reset --soft "Commit Hash"   // 폴더 내용 유지, commit을 취소해 add에 남긴다.
git reset --mixed "Commit Hash"  // 폴더 내용 유지,  commit과 add를 모두 취소한다.
git reset --hard "Commit Hash"   // 폴더 내용 삭제, commit과 add 모두 취소한다. 

git rm --cached filename // tracked file -" untracked file

// ============Branch============ //

// 확인 명령어
git branch

// 생성 명령어
git branch "name"

// 이름 변경 명령어 (현재 작업 중인 브랜치 이름 강제 변경)
git branch -M "name"

// 변경 명령어 (둘 중 자유 사용)
git switch "name"
git checkout "name"

// --------병합 명령어(A→B)-------- //

// Fast-Forward(Default: FF) - 비권장
git switch "B 병합될 브랜치"  // 병합될 브랜치에 switch해서 진행
git merge "A 브랜치"

// non-Fast-Forward - 권장
// A→B
git switch "B 병합될 브랜치"
git merge "A 브랜치" --no-ff -m "log message"

// 동기화
git switch "A 병합한 브랜치"
git merge "B 브랜치"

// -------충돌 해결 후 병합------ //

// 충돌 해결 후 병합
git merge "B 병합될 브랜치" // 또는 non-ff사용. 문제 메시지 출력+다른 내용 강조. 폴더에서 해당 파일을 열어 최종수정 후 add 진행.
git add * 
git merge —continue // 메세지 작성하라고 문서 오픈. i 로 수정, esc로 수정종료 가능, :wq 로 저장-나가기

// 동기화  
git switch "A 브랜치"
git merge "B 병합될 브랜치"
	```

	**git 다운로드**

	1. git 다운로드

	2. `cmd`  검색해 명령 프롬프트 오픈

	3. git 버전 확인 `git -v` 

	**전역 설정**
	```javascript
// 깃허브와 동일 email, nickname
git config --global user.email "your email"
git config --global user.name "your nickname"

// 저장 확인
git config --list

// 삭제
git config --global --unset user.name
git config --global --unset user.email
	```
	git config --global user.email "**marine3682@gmail.com**"<br>git config --global user.name "**1gyeolpark**"

---

## Git 기본 명령어

**파일 저장 순서**

> 실제 폴더 → 임시 저장소(add된 파일) → 최종 저장소(commit된 파일)<br>WD(Working Directory) → SA(Staging Area) → Git Directory(repo)

HEAD: 현재 위치 포인터 (보통 브랜치 마지막 커밋)

저장할 파일 폴더 주소 부분에 `cmd` → enter 해 명령 프롬프트 오픈 

**초기화**

현재 폴더를 <span color="red">새로운 git 저장소</span>로 만들거나 기존 저장소를 초기화한다.
```javascript
git init
```

---

### 저장 명령어

실제 폴더에 저장할 파일 생성

**WD → SA add**<br>실제 폴더(WD) → 임시저장소(SA)로 add한다.
```javascript
// 특정 파일
git add 파일명
// ex) git add abc.txt

//전체 파일
git add *
```

**SA → repo commit 최종 저장**

임시 저장소(SA) → 최종 저장소(repo)로 commit한다.

메세지를 작성해 로그 확인을 통해 볼 수 있는 변경 사항 메시지를 기록할 수 있다.

로그 메시지에 스페이스바를 사용하지 않으면 “”가 없어도 된다.
```javascript
git commit -m "log message" 
// ex) git commit -m "V0.0 aaa.txt added"
```

---

### 확인 명령어

**WD와 SA의 상태 확인 **

<span color="red">변경 사항을 파악해 파일이 add에 들어갔는지, 전부 commit 되어 SA가 비어있는지 알 수 있다.</span><br>add되지 않은 파일(untracked files), <br>add된 커밋 예정 파일(Changes to be committed), <br>add되었고 수정된 파일(Changes not staged for commit)을 볼 수 있다. {color="blue"}
```javascript
git status
```

**로그 확인**

<span color="red">작업 기록을 확인</span>하고, 기록을 되돌릴 수 있는 해시(ID)를 볼 수 있다.

> **전체 로그 확인**: HEAD되었던 모든 기록들을 출력한다. `git log` 에는 없는 삭제된 커밋도 볼 수 있다.<br>**로그 확인**: 현재 존재하는 모든 기록들을 출력한다. <br>**단축 로그 확인**: 현재 존재하는 모든 기록들을 1줄로 줄여 출력한다.
```javascript
// 전체 로그 확인
git reflog 

// 로그 확인
git log

//한줄 단축 로그 확인
git log --oneline
```

---

### 복원 명령어

로그를 확인해 파악한 해시를 이용하여 <span color="red">해당 시점까지 되돌린다.</span>

> —soft: 폴더 내용 유지, commit을 취소해 add에 남긴다.<br>—mixed: 폴더 내용 유지,  commit과 add를 모두 취소한다.<br>—hard: 폴더 내용 <span color="red">삭제</span>, commit과 add 모두 취소한다. <br>→ hard에서 add에 파일을 넣어두고 파일 생성 전 시점으로 되돌릴 경우, 이미 폴더 안 내용을 삭제했고 최종 저장소에 담긴 적이 없으므로 다시 앞으로 돌려도 add에 있는 파일은 복원할 수 없다.
```javascript
git reset --hard "Commit Hash"
// ex) git reset --hard 3052268
```
<table>

<colgroup>

<col width="119.36874389648438">

<col width="141.4">

<col width="141.4">

<col width="145.3874969482422">

<col width="141.4">

</colgroup>

<tr>

<td>git reset</td>

<td>포인터<br>HEAD</td>

<td>실제 폴더<br>Working Directory </td>

<td>임시 저장소<br>Staging Area</td>

<td>최종 저장소<br>Git Directory(repo)</td>

</tr>

<tr>

<td>--soft</td>

<td>이동</td>

<td>유지</td>

<td>유지+repo 파일 추가</td>

<td>삭제 ❌</td>

</tr>

<tr>

<td>--mixed (기본값)</td>

<td>이동</td>

<td>유지</td>

<td>삭제 ❌</td>

<td>삭제 ❌</td>

</tr>

<tr>

<td>--hard (비권장)</td>

<td>이동</td>

<td>삭제 ❌</td>

<td>삭제 ❌</td>

<td>삭제 ❌</td>

</tr>

</table>

---

### Git 실습 {toggle="true"}
	```javascript
```
저장할 파일을 만든다.

파일 위치부분 클릭 - cmd → 명령프롬프트 오픈된다.

진행: 차례대로 aaa.txt, ccc.txt, bbb.txt를 만들고 특정 시점 복원해본다.
```
// 현재 폴더를 git 저장소로 만듦
git init
// 파일 상태 확인
git status

// 로그 확인 (중간중간 확인해가며 진행)
// 삭제 포함 모든 로그 확인
git reflog
// 로그 확인
git log
// 로그 한줄 확인
git log --oneline

// 문서에 파일 만든 뒤 git 에 add (임시 저장소) -" commit+로그메시지 (최종 저장소)
git add aaa.txt 
git commit -m "V0.0 aaa.txt added"

git add bbb.txt 
git commit -m "V0.1 bbb.txt added"

git add *
git commit -m "V0.2 ccc.txt added"

// 로그 확인으로 커밋 해시 확인
git log --oneline

// 특정 시점 복원 
git reset --hard "Commit Hash"
// ex) git reset --hard 3052268
	```

---

## Branch 정의

> 개발자들이 프로젝트를 공유하고 같이 작업할 수 있도록 해주며, 각 독립적인 저장소 안에서 소스코드를 변경할 수 있다. 각각의 브랜치는 다른 브랜치의 영향을 받지 않으므로 여러 작업을 동시 진행할 수 있다.

branch 가지 확인 `git log --graph`

### **확인 명령어**
```javascript
git branch
git branch -a // 모든 브치 확인
```

### **생성 명령어**

branch를 생성한다.
```javascript
git branch "name"
// ex) git branch dev 
```

### 이름 변경 명령어

```javascript
// 현재 작업 중인 브랜치 이름 강제 변경
git branch -M "name"
```
### **변경 명령어**

현재 작업 중인 branch를 변경한다.
```javascript
// 둘 중 자유 선택 사용
git switch "name"
// ex) git switch dev
git checkout "name"
```

---

### **병합 명령어**

A branch에서 작업한 내용은 B branch에 보이지 않기 때문에 A 작업 완료 후 합치는 작업이 필요하다. <br><span color="red">병합될 브랜치</span>에 switch해서 진행해야 한다. (ex. feature → dev 로 병합할 경우 dev에서 진행)

**1.Fast-Forward(Default: FF)**

기본값. 커밋을 생성하지 않고, 메시지를 작성할 수 없다. 정확한 시점이 기록되지 않으므로 권장되지 않는다.
```javascript
// A→B
git switch "B 병합될 브랜치"
git merge "A 브랜치" 

```
ex) feature → dev 로 병합

git swtich dev

git merge feature
```
```

**2.non-Fast-Forward**

커밋을 생성하고, 메시지를 작성할 수 있다. 흔히 사용되며 권장된다.<br>**non-ff**는 브랜치를 자동으로 올려주지 않으므로 FF로 브랜치 위치 동기화가 필요하다.
```javascript
// A→B
git switch "B 병합될 브랜치"
git merge "A 브랜치" --no-ff -m "로그 메시지"

// 동기화
git switch "A 병합될 브랜치"
git merge "B 브랜치"

// 로그 메시지를 작성하지 않을 경우
git merge "A 브랜치" --no-ff  // 메세지 작성하라고 문서 오픈. i 로 수정, esc로 수정종료 가능, :wq 로 저장-나가기
```
<details>

<summary>**non-ff** 예시</summary>
	```javascript
// ex) feature → dev 로 병합
git swtich dev
git merge feature --no-ff -m "V0.3-merge"
git switch feature
git merge dev
	```
</details>

### 충돌 해결 후 병합 

각 branch의 동일한 파일에 다른 내용이 작성되어있는 상태에서 병합을 시도할 경우 문제 메시지가 출력되고, 해당 파일에서 다르게 작성된 내용을 강조해준다. 이를 수정하고 continue하여 병합한다.
```javascript
git merge "B 병합될 브랜치" // 적용 X 문제 메시지 출력+다른 내용 강조. 
// 폴더에서 해당 파일을 열어 최종수정 후 add 진행.
git add * 
git merge --continue // non-ff라 동기화 진행 필요. 메세지 작성하라고 문서 오픈. i 로 수정, esc로 수정종료 가능, :wq 로 저장-나가기

// 동기화  
git switch "A 병합될 브랜치"
git merge "B 브랜치"
```
<details>

<summary>충돌 해결 후 병합 예시</summary>
	```javascript
// ex) dev → master 로 병합
git branch master
git merge dev --no-ff -m "V0.5 merge" // 오류 출력. 폴더 해당파일 수정.
git merge --continue // 메세지 작성하라고 문서 오픈. i 로 수정, esc로 수정종료 가능, :wq 로 저장-나가기

git add *
git merge —continue

// 동기화  
git switch dev
git merge master
	```

</details>

---

### Branch 실습 {toggle="true"}
	```javascript
```
저장할 파일을 만든다.

파일 위치부분 클릭 - cmd → 명령프롬프트 오픈된다.
```
// 현재 폴더를 git 저장소로 만듦
git init
// 파일 상태 확인
git status

// 초안 파일 init.txt 생성 후 커밋
git add *
git commit -m "V0.0 INIT"

// 로그 한줄 확인 (중간중간 확인해가며 진행)
git log --oneline

// Branch확인(기본 master branch 존재)
git branch

// Branch 생성 
git branch dev

// Branch 변경 (둘 중 하나)
git switch dev
git checkout dev

// Dev branch에 div_01.txt 생성 후 커밋
git add *
git commit "V0.1 div_01"

// 이때 div branch에 작업한 것은 master가 아직 알 수 없다.

// 파일 병합(Default: FF) (비효율. 커밋이 만들어지지 않음.)
git switch master
git merge dev

// Dev branch에 div_02.txt 생성 후 커밋
git switch dev
git add *
git commit -m "V0.2 dev_02"

// 파일 병합(non-FF) (많이 쓰는 것. 추천)
git switch master
git merge dev --no-ff -m "V0.2 dev_02 merge" 
git switch dev // 동기화 진행
git merge master

// 충돌 해결 후 병합
// div_02 파일 dev 와 master 의 내용이 다를 때
// 병합될 branch로 이동
git branch master
git merge dev // 적용 X 문제 메시지 출력+다른 내용 강조. 
// 폴더에서 해당 파일을 열어 최종수정 후 add 진행. 
git add *
git merge --continue // non-ff라 동기화 진행 필요. 메세지 작성하라고 문서 오픈. i 로 수정, esc로 수정종료 가능, :wq 로 저장-나가기

// 동기화  
git switch dev
git merge master
	```
