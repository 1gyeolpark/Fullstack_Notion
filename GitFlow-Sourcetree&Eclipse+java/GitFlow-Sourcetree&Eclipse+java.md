리드미 없는 깃허브 저장소 생성

원격 - 설정 클릭, 추가 클릭

![](images/image.png)

디폴트 원격, 경로 설정후 확인

푸쉬 누르고

모두 선택 눌러서 푸쉬

![](images/image_2.png)

![](images/image_3.png)

깃플로우-새기능시작

![](images/image_4.png)

![](images/image_5.png)

func2도 동잃게

먼저 댓브랜치 최신화 (한번 위로 올리기

![](images/image_6.png)

그다음 둘다 재패치-병합.

1. **병합할 브랜치**’에 헤더를 두고 ‘**dev**’가 있는 곳 오른쪽 마우스 → `재배치`

2. 한칸 올라가면 그 아래 ‘**dev**’에 헤더를 두고 ‘**병합할 브랜치**’에 오른쪽 마우스 → `병합` \*\* 이때 fast-forward가 가능해도 `새 커밋으로 생성`  필수 체크

환경변수 설정\~

![](images/image_7.png)

![](images/image_8.png)

![](images/image_9.png)

![](images/image_10.png)

IDE

Integrated      : 통합<br>Development : 개발<br>Environment   : 환경

---

Editor + Debugger + Compiler

![](images/image_11.png)

![](images/image_12.png)

![](images/image_13.png)

![](images/image_14.png)

압축 풀고 C드라이브로 옮기기

eclipse.exe 더블클릭 실행

저장될 상위폴더 지정 후 Launch

![](images/image_15.png)

프로젝트 만들기

![](images/image_16.png)

이름 설정, 

Create [modul-info.java](http://modul-info.java) file 체크 해제 (지금은 필요없음)

![](images/image_17.png)

패키지 생성

![](images/image_18.png)

이름 설정

![](images/image_19.png)

이름 설정, public…클릭해서 만들기

![](images/image_20.png)

실행 확인(Ctrl-F11)

![](images/image_21.png)

![](images/image_22.png)

use..클릭, create repositort클릭하고 finish

![](images/image_23.png)

다음

![](images/image_24.png)

두개 클릭하고 오픈

![](images/image_25.png)

두개 확인. ++클릭해 아래 칸에 올리고 커밋

![](images/image_26.png)

커밋 메시지 쓰고 커밋 클릭

![](images/image_27.png)

깃허브에 새 저장소 만들어 이것 올리기(리드미 미포함)

![](images/image_28.png)

![](images/image_29.png)

![](images/image_30.png)

URL: 깃허브 저장소 URL<br>User: 깃허브 이메일 주소<br>password: 깃허브 access tokens

finish하고 save and push

<br>

![](images/image_31.png)

![](images/image_32.png)

깃허브에서 access tokens 만들기

![](images/image_33.png)

메모-만료날짜

![](images/image_34.png)

![](images/image_35.png)

접근 권한설정

![](images/image_36.png)

![](images/image_37.png)

![](images/image_38.png)

![](images/image_39.png)

![](images/image_40.png)

![](images/image_41.png)

![](images/image_42.png)

![](images/image_43.png)

![](images/image_44.png)

![](images/image_45.png)

---

## **26.04.14**

**project 생성** {color="blue_bg"}

![](images/image_46.png)

**package **

![](images/image_47.png)

![](images/image_48.png)

![](images/image_49.png)

![](images/image_50.png)

![](images/image_51.png)

과제: utf-8 확인했다는 스크린샷 필요

![](images/image_52.png)

![](images/image_53.png)

.git만들기

폴더모양오른쪽마우스-team-

![](images/image_54.png)

![](images/image_55.png)

![](images/image_56.png)

![](images/image_57.png)

![](images/image_58.png)

![](images/image_59.png)

![](images/image_60.png)

![](images/image_61.png)

![](images/image_62.png)

![](images/image_63.png)

![](images/image_64.png)

master로 브랜치 변경

폴더 오른쪽 마우스-team-switch to-master

merge하기

폴더 오른쪽 마우스-team-merge

![](images/image_65.png)

![](images/image_66.png)

히스토리켜서 확인

![](images/image_67.png)

깃허브 연결

![](images/image_68.png)

![](images/image_69.png)

![](images/image_70.png)

![](images/image_71.png)

![](images/image_72.png)

![](images/image_73.png)

![](images/image_74.png)

![](images/image_75.png)

![](images/image_76.png)

![](images/image_77.png)

![](images/image_78.png)

![](images/image_79.png)

![](images/image_80.png)

충돌 시키기

![](images/image_81.png)

master로 스위치 이동

머지 실행 (머지할 부분에 클릭하고 해야함!)

![](images/image_82.png)

![](images/image_83.png)

![](images/image_84.png)

수정하고 커밋

![](images/image_85.png)

![](images/image_86.png)

작업본 푸쉬 (브랜치 별로 푸쉬해야 함)

![](images/image_87.png)

**타인의 깃허브를 공유해 협업 연습**

파일 하나 만들고 깃허브 링크 git clone한 뒤 declipse로 그 파일을 열어준다.

![](images/image_88.png)

![](images/image_89.png)

![](images/image_90.png)

![](images/image_91.png)

원격 브랜치 로컬로 받아오기

![](images/image_92.png)

![](images/image_93.png)

![](images/image_94.png)

여기서 이슈 열고 본인 브랜치 연결

![](images/image_95.png)

푸시하고 깃허브에 이슈 닫고, 풀리퀘스트 올려 확인 받고 병합
