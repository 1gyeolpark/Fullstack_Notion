## GitHub Remote repository 연동
> GitHub에 회원가입 후 리포지토리를 생성하고 로컬에 연동한다. 이를 통해 효과적으로 데이터를 관리하거나 협업할 수 있다. 
<empty-block/>
### \*GitHub 연동 명령어 요약 {toggle="true"}
	```javascript
// 원격 저장소 내용 로컬 복사
// (처음 시작해 컴퓨터에 파일이 없을 때 실행!)
git clone "https://github.com/계정이름/리포지토리 이름.git"  // 저장소 링크 복사-붙여넣기
cd "Repository name" // 리포 안으로 이동한다.

// ------- 로컬 원격 저장소 확인, 연결 -------- //
// (clone으로 파일 불러와 컴퓨터에 코드가 있을 때 실행) 

// 연결된 원격 저장소들 이름 확인
git remote

// 연결된 원격 저장소들 이름, URL 확인
git remote -v

// 해당 원격 저장소 상세 정보 확인
git remote show "이름"

// 새로운 원격 저장소 연결 
git remote add "원하는 이름" "https://github.com/계정이름/리포지토리 이름.git"
git remote add origin "링크" // 보통 origin 사용

// 원격 저장소 삭제(로컬 데이터는 남아있음)
git remote remove "이름" // = git remote rm "이름"

// 원격 저장소 별칭 변경
git remote rename "기존이름" "새이름"

// ------- 원격저장소의 branch와 commit을 로컬 내려받고 merge ------- //

git pull "저장소명" "브랜치명"
git pull origin // 보통 이렇게 사용

// 원격저장소의 branch와 commit을 로컬 내려받기
git fetch "저장소명" "브랜치명"
git fetch origin // 보통 이렇게 사용

// 로컬의 commit을 원격 저장소 업로드

git push "저장소명" "브랜치명" 
git push "저장소명" // 브랜치 지정 생략도 가능
git push origin // 보통 이렇게 사용

// 저장소명 작성 생략 명령어 (브랜치마다 따로따로 실행해야 한다.)
git push --set-upstream "저장소명" "브랜치명" // = git push -u origin master
// 이후부터는 git push  git pull 만 해도 업로드된다.

// ------- 충돌 해결 후 push ------- //

// 충돌을 확인한 뒤 해당 파일을 열어 내용을 고친 뒤 add merge한다.

git add *
git merge  --continue // 메세지 작성하라고 문서 오픈. i 로 수정, esc로 수정종료 가능, :wq 로 저장-나가기

git push origin
	```
### git clone <br>: 원격 저장소 내용 로컬 복사
> 내 컴퓨터에 원격 저장소(Remote Repository: 깃허브 저장소)를 내 로컬 저장소(Local Repository: 로컬 컴퓨터)로 복사해 가져온다. 보통 처음 시작해 컴퓨터에 파일이 없을 때 실행한다. clone으로 불러올 때 기본 이름은 origin(원격주소)이다.
```javascript
// cd하거나 가져올 파일 주소창에 cmd작성해서 cmd를 연다.

git clone "https://github.com/계정이름/리포지토리 이름.git"  // 저장소 링크 복사-붙여넣기

cd "Repository name" // 리포 안으로 이동한다.
```
<empty-block/>
### git remote<br>: 로컬에서 원격 저장소 확인, 연결
> 현재 프로젝트에 연결된 원격 저장소를 확인하거나 새로운 저장소를 추가한다. 보통 clone으로 파일을 불러와 이미 내 컴퓨터에 코드가 있을 때 실행한다.
```javascript
// 연결된 원격 저장소들 이름 확인
git remote

// 연결된 원격 저장소들 이름, URL 확인
git remote -v

// 해당 원격 저장소 상세 정보 확인
git remote show "이름"

// 새로운 원격 저장소 연결 
git remote add "원하는 이름" "https://github.com/계정이름/리포지토리 이름.git"
git remote add origin "링크" // 보통 origin 사용

// 원격 저장소 삭제(로컬 데이터는 남아있음)
git remote remove "이름" // = git remote rm "이름"

// 원격 저장소 별칭 변경
git remote rename "기존이름" "새이름"
```
<empty-block/>
### git pull<br>:원격저장소의 branch와 commit을 로컬 내려받고 merge
> ** **git pull** = **git fetch + git merge.** **원격 저장소에 있던 파일을 로컬로 동기화하고 merge 시킨다. 원격 저장소의 변경 사항들을 pull로 가져와 동기화하고 push해야 기타 문제가 발생하지 않는다.
```javascript
git pull "저장소명" "브랜치명"
git pull origin // 보통 이렇게 사용
```
<empty-block/>
### git fetch<br>:원격저장소의 branch와 commit을 로컬 내려받기
> ** **원격 저장소에 있던 파일을 로컬로 동기화한다. merge하지 않는다.
```javascript
git fetch "저장소명" "브랜치명"
git fetch origin // 보통 이렇게 사용
```
<empty-block/>
### git push<br>: 로컬의 commit을 원격 저장소 업로드
> 로컬에서 branch를 작업하고 commit한 파일들을 원격 저장소에 업로드한다. 원격 저장소에 다른 추가된 내용이 존재할 경우 pull부터 시도하라는 메시지가 출력된다.
```javascript
git push "저장소명" "브랜치명" 
git push "저장소명" // 브랜치 지정 생략도 가능
git push origin // 보통 이렇게 사용

// 저장소명 작성 생략 명령어 (브랜치마다 따로따로 실행해야 한다.)
git push --set-upstream "저장소명" "브랜치명" // = git push -u origin master
// 이후부터는 git push  git pull  만 해도 업로드된다.
```
<empty-block/>
### 충돌 해결 후 push
> 원격 저장소와 로컬저장소의 동일한 파일에 다른 내용이 작성되어있는 상태에서 pull를 시도할 경우 문제 메시지가 출력되고, 해당 파일에서 다르게 작성된 내용을 강조해준다. 이를 수정하고 continue하여 push한다.
```javascript
// 충돌을 확인한 뒤 해당 파일을 열어 내용을 고친 뒤 add merge한다.

git add *
git merge  --continue // 메세지 작성하라고 문서 오픈. i 로 수정, esc로 수정종료 가능, :wq 로 저장-나가기

git push origin
```
<empty-block/>
### GitHub Remote repository 실습 {toggle="true"}
	```javascript
```
깃허브에 로그인해 새 리포지토리를 생성한다.

로컬에 저장할 파일을 만든다. 
파일 위치부분 클릭 - cmd → 명령프롬프트 오픈된다.
```

// -------- Remote → Local(git clone) -------- //
// 상황: 원래 존재하는 리포지토리의 내용을 컴퓨터에 받아오고 싶다.

git clone "https://github.com/계정이름/리포지토리 이름.git"  // 저장소 링크 복사-붙여넣기

// -------- Local → Remote Repository(git push) -------- //

// Local에서 오픈한 명령 프롬프트에서 진행
// 상황: 새로운 리포지토리에 내가 작성한 파일들을 업로드하고 싶다.

// 현재 폴더를 git 저장소로 만들고 add, commit
git init
git add *
git commit -m "V0.0"

git branch // 브랜치 확인해보면 기본 이름이 master임을 알 수 있다.

git branch -M main // 요즘 표준 이름인 main으로 현재 브랜치명 강제변경

git branch // 브랜치를 확인하면 main으로 바뀌어 있다.

git remote add origin https://github.com/계정이름/리포지토리명.git // 원격 저장소 연결

git remote -v // 연결된 원격 저장소를 확인한다.

git push origin 
// main브랜치를 어디로 보낼지 연결고리(upstream)가 생성되지 않았다는 오류 메시지가 나온다.
// 아래 명령어로 연결시켜준다.

git push --set-upstream origin main // 저장소명 작성 생략 명령어 (브랜치마다 따로따로 실행해야 한다.)

// 로컬에서 다른 파일을 추가하고 add, commit, push

git add *
git commit -m V0.1
git push origin

// -------- Remote → Local(git pull) -------- //
// pull하고 push해야 기타 문제가 발생하지 않는다. 

git pull origin01 main // 리포지토리의 내용을 로컬로 pull해 동기화시킨다.

	```
<empty-block/>
