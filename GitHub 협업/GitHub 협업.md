## GitHub 협업

> github에 로그인하여 Oranization(조직, 팀)과 Repository(리포지토리)를 생성하고 협업할 수 있다. 팀에 초대해 여러 프로젝트를 함께 진행할 수 도 있고, 리포 하나에만 초대할 수도 있다.

### Oranization 생성 및 설정

<callout>

	1. 팀장이 Oranization과 Repository 생성. 이때 readme를 추가하고, 유료 계정이 아니라면 public으로 생성한다.<br><br>-하단 권한 및 기타 설정을 완료한다.

	2. dev branch를 생성한 뒤, 기본 branch를 dev로 만든다. 

		<span color="gray">— Settings → Default branch를 dev로</span>

	3.  Oranization 팀원 기본 권한을 Write로 설정한다. 

		<span color="gray">— Oranization→ Settings → Member Privileges → Write 권한</span>

	4. 브랜치 접근 권한을 관리하기 위해 Repository’s Branch Rule을 설정한다.

		— Oranization → Repository →  Settings →  Branchs → Add classic branch protection rule {color="gray"}

			main: Lock Branch    \|    dev: Require a pull request before merging

	5. project(pj)를 public으로 생성해 프로젝트를 관리한다. 이슈를 설정하고 팀원들이 작업 후 merge를 요청하면 된다.

		<span color="gray">— Oranization → Repository → Projects → New project</span>

</callout>

### member 초대

<callout>

	**Oranization 초대**

	Oranization → people → Members 에서 lnvite member로 초대

	---

	**Repository 초대**

	Oranization→ Repository → Settings → Collaborators and Teams → Add People로 초대

</callout>

### pull request(병합) 요청

<callout>

	1. main branch 권한이 없어 병합하지 못할 때 팀원이 병합 요청을 하고, 팀장이 pull request 확인 및 병합 승인 처리한다.

	2. 팀원 n명(설정 가능)이 pull request 요청에 Files changed → Submit review 작성 후 승인 클릭하면 자동 merge처리되게 할 수도 있다.

</callout>
