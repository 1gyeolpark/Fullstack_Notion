### IDEA 기본 설정
<empty-block/>
<empty-block/>
`프로젝트 구조`에서 SDK와 언어 수준 설정되어있는지 확인
![](images/image.png)
<empty-block/>
---
`환경설정` 눌러 설정 창 열어 기본 설정한다.
#### - gradle
검색 창에 `gradle` 검색, **종속성에 대한 외부 어노테이션 다운로드** 체크박스 클릭하고 **다음을 사용하여 빌드/테스트 진행**에 IntellU UDEA 클릭
![](images/image_2.png)
<empty-block/>
#### - 자동 가져오기
<empty-block/>
![](images/image_3.png)
<empty-block/>
#### - 일반-휠설정
![](images/image_4.png)
<empty-block/>
#### 컴파일러
![](images/image_5.png)
<empty-block/>
#### 고급설정
![](images/image_6.png)
<empty-block/>
<empty-block/>
<empty-block/>
<empty-block/>
---
<empty-block/>
<empty-block/>
<empty-block/>
**STEP 1. IntelliJ IDEA 설치<br>**
<empty-block/>
<empty-block/>
![](images/image_7.png)
![](images/image_8.png)
<empty-block/>
![](images/image_9.png)
**STEP 2. Spring Initializr 로 프로젝트 생성**
<empty-block/>
주소창에 [`https://start.spring.io/`](https://start.spring.io/) 검색
![](images/image_10.png)
<empty-block/>
<empty-block/>
이전 사용하던 jsp 활용 위해 지금은 war 선택 (jar 선택해야 톰캣이 내장됨, war는 외장)
<empty-block/>
![](images/image_11.png)
<empty-block/>
<empty-block/>
![](images/image_12.png)
![](images/image_13.png)
<empty-block/>
---
<empty-block/>
![](images/image_14.png)
<empty-block/>
여기 메이븐 레포지토리에서 기본으로 가져옴 확인
![](images/image_15.png)
![](images/image_16.png)
![](images/image_17.png)
<empty-block/>
<empty-block/>
이것도
![](images/image_18.png)
<empty-block/>
<empty-block/>
다했음 다운로드
![](images/image_19.png)
![](images/image_20.png)
아까 다운받은 거 환경변수 설정
![](images/image_21.png)
<empty-block/>
받은 폴더 zip 풀고 깃허브 연동
깃허브 연동한 폴더에  cmd 열고 
`idea .` 적고 클릭
![](images/image_22.png)
열리면 `환경설정` 눌러 설정하기
`gradle` 검색 - 경로 설정 가능
![](images/image_23.png)
<empty-block/>
`프로젝트 구조`에서 SDK와 언어 수준 설정되어있는지 확인
![](images/image_24.png)
<empty-block/>
import 경로 중복되지 않으면 자동으로 잡아주게 하는 설정
<empty-block/>
![](images/image_25.png)
<empty-block/>
<empty-block/>
테스트 하려면 클래스 부분에 마우스 대고 <br><br>`// JUNIT TEST CASE: Ctrl + Shift + t`
<empty-block/>
<empty-block/>
![](images/image_26.png)
<empty-block/>
휠로 글꼴 크기 변경
![](images/image_27.png)
<empty-block/>
<empty-block/>
이렇게 직접생성도 가능 (그러나 @Data가 편하다!)
![](images/image_28.png)
<empty-block/>
![](images/image_29.png)
<empty-block/>
<empty-block/>
<empty-block/>
![](images/image_30.png)
<empty-block/>
![](images/image_31.png)
<empty-block/>
<empty-block/>
![](images/image_32.png)
![](images/image_33.png)
![](images/image_34.png)
<empty-block/>
<empty-block/>
Pistman 다운로드
![](images/image_35.png)
<empty-block/>
![](images/image_36.png)
![](images/image_37.png)
![](images/image_38.png)
<empty-block/>
스프링 부트 개발 시 코드를 고치면 서버를 자동으로 빠르게 재시작해주고, 화면 파일을 고치면 새로고침 없이 즉시 반영해 주는 개발 도구
![](images/image_39.png)
![](images/image_40.png)
![](images/image_41.png)
![](images/image_42.png)
<empty-block/>
<empty-block/>
![](images/image_43.png)
<empty-block/>
<empty-block/>
<empty-block/>
![](images/image_44.png)
![](images/image_45.png)
<empty-block/>
p02 확인(postman사용)
![](images/image_46.png)
p09 확인(postman사용)
![](images/image_47.png)
<empty-block/>
p10 확인(postman. 쌤과좀다른데
![](images/image_48.png)
![](images/image_49.png)
<empty-block/>
<empty-block/>
충돌 해결
![](images/image_50.png)
<empty-block/>
![](images/image_51.png)
![](images/image_52.png)
![](images/image_53.png)
<empty-block/>
![](images/image_54.png)
![](images/image_55.png)
![](images/image_56.png)
<empty-block/>
<empty-block/>
![](images/image_57.png)
![](images/image_58.png)
![](images/image_59.png)
내용추가
<empty-block/>
---
<empty-block/>
06 다음부터 스프링 다른 것으로 다운
![](images/image_60.png)
압축파일로 받아서 풀기
<empty-block/>
<file src="file://%7B%22source%22%3A%22attachment%3A27893eab-7a3e-46cb-bfe7-3b8acad2bc7f%3Ademo.zip%22%2C%22permissionRecord%22%3A%7B%22table%22%3A%22block%22%2C%22id%22%3A%2237220a7d-9f4c-8024-bd91-fee7f886cdcc%22%2C%22spaceId%22%3A%22e3e20a7d-9f4c-816c-a8a0-0003c6ad3a11%22%7D%7D"></file>
<empty-block/>
<empty-block/>
![](images/image_61.png)
<empty-block/>
// Source:<br>implementation 'org.apache.commons\:commons-dbcp2\:2.14.0'
<empty-block/>
---
<empty-block/>
![](images/image_62.png)
기존 것에서 
![](images/image_63.png)
<br>이 둘만 복붙<br>`  implementation 'org.mybatis.spring.boot:mybatis-spring-boot-starter:3.0.5'`<br>`  testImplementation 'org.mybatis.spring.boot:mybatis-spring-boot-starter-test:3.0.5'`
<empty-block/>
<empty-block/>
---
<empty-block/>
09번
![](images/image_64.png)
![](images/image_65.png)
복붙
<br><br>`  implementation 'org.springframework.boot:spring-boot-starter-data-jpa'`
<empty-block/>
![](images/image_66.png)
![](images/image_67.png)
<empty-block/>
<empty-block/>
<empty-block/>
---
---
06.08
![](images/image_68.png)
<file src="file://%7B%22source%22%3A%22attachment%3A89bdae66-cb3a-4220-b11c-163921199c11%3Ademo.zip%22%2C%22permissionRecord%22%3A%7B%22table%22%3A%22block%22%2C%22id%22%3A%2237920a7d-9f4c-8008-9b65-ef03ddeb5210%22%2C%22spaceId%22%3A%22e3e20a7d-9f4c-816c-a8a0-0003c6ad3a11%22%7D%7D"></file>
![](images/image_69.png)
![](images/image_70.png)
<empty-block/>
<empty-block/>
<empty-block/>
![](images/image_71.png)
![](images/image_72.png)
<empty-block/>
---
<empty-block/>
---
[https://cdnjs.com/libraries/jquery](https://cdnjs.com/libraries/jquery)
![](images/image_73.png)
![](images/image_74.png)
<empty-block/>
[https://www.jsdelivr.com/package/npm/axios](https://www.jsdelivr.com/package/npm/axios)
<empty-block/>
![](images/image_75.png)
<empty-block/>
<empty-block/>
<empty-block/>
공공데이터센터 로그인 - 내 인증키 볼붙 - 필요한 데이터 활용신청 - 밑에 샘플 데이터 제이슨 형태로 가져오기 - 링크 복사 - 코드에 넣기 
[https://apis.data.go.kr/1360000/VilageFcstInfoService_2.0/getUltraSrtNcst?serviceKey=c362a32195cf2b83d32ee7f30975d327ce8b15c1316a55b4a985443830a61356&pageNo=1&numOfRows=1000&dataType=JSON&base_date=20260609&base_time=1430&nx=89&ny=90](https://apis.data.go.kr/1360000/VilageFcstInfoService_2.0/getUltraSrtNcst?serviceKey=c362a32195cf2b83d32ee7f30975d327ce8b15c1316a55b4a985443830a61356&pageNo=1&numOfRows=1000&dataType=JSON&base_date=20260609&base_time=1430&nx=89&ny=90)
![](images/image_76.png)
<empty-block/>
<empty-block/>
---
<empty-block/>
---
<empty-block/>
![](images/image_77.png)
<empty-block/>
![](images/image_78.png)
<empty-block/>
---
<empty-block/>
---
<empty-block/>
html 03에서 가져와 12번 지도 찍기 했다. 
![](images/image_79.png)
<empty-block/>
---
<empty-block/>
---
<empty-block/>
![](images/image_80.png)
![](images/image_81.png)
<empty-block/>
<empty-block/>
![](images/image_82.png)
![](images/image_83.png)
![](images/image_84.png)
f729eeecbbd0b2db8c757d6c8ac509fe
변경—→ cd2a4c4ac447447203306e330cc10fea
![](images/image_85.png)
![](images/image_86.png)
![](images/image_87.png)
![](images/image_88.png)
![](images/image_89.png)
<empty-block/>
<empty-block/>
<empty-block/>
---
![](images/image_90.png)
![](images/image_91.png)
아이피제외!
<empty-block/>
![](images/image_92.png)
<empty-block/>
![](images/image_93.png)
![](images/image_94.png)
<empty-block/>
---
<empty-block/>
사용설정활성화
<empty-block/>
![](images/image_95.png)
필수동의
![](images/image_96.png)
<empty-block/>
에러로그: test앱에 앱 아이콘을 추가하지 않아서 에러 발생
![](images/image_97.png)
![](images/image_98.png)
업로드해 문제해결
<empty-block/>
<empty-block/>
---
---
![](images/image_99.png)
---
---
6.11
<empty-block/>
![](images/image_100.png)
// Source: [https://mvnrepository.com/artifact/com.googlecode.json-simple/json-simple](https://mvnrepository.com/artifact/com.googlecode.json-simple/json-simple)<br>implementation 'com.googlecode.json-simple\:json-simple\:1.1.1'
<empty-block/>
![](images/image_101.png)
<empty-block/>
<empty-block/>
![](images/image_102.png)
<empty-block/>
<empty-block/>
카카오 채널 만들기
![](images/image_103.png)
<empty-block/>
![](images/image_104.png)
도메인 추가
![](images/image_105.png)
<empty-block/>
신청자격 확인 클릭
![](images/image_106.png)
![](images/image_107.png)
<empty-block/>
<empty-block/>
[https://developers.kakao.com/docs/ko/javascript/download-v1](https://developers.kakao.com/docs/ko/javascript/download-v1)
<empty-block/>
<empty-block/>
![](images/image_108.png)
<empty-block/>
![](images/image_109.png)
<empty-block/>
![](images/image_110.png)
![](images/image_111.png)
<empty-block/>
![](images/image_112.png)
<empty-block/>
![](images/image_113.png)
<empty-block/>
<empty-block/>
<empty-block/>
---
---
<empty-block/>
네이버 개발자 센터
![](images/image_114.png)
<empty-block/>
![](images/image_115.png)
<empty-block/>
![](images/image_116.png)
![](images/image_117.png)
<empty-block/>
[https://developers.naver.com/docs/login/devguide/devguide.md#3-4-2-네이버-로그인-연동-url-생성하기](https://developers.naver.com/docs/login/devguide/devguide.md#3-4-2-%EB%84%A4%EC%9D%B4%EB%B2%84-%EB%A1%9C%EA%B7%B8%EC%9D%B8-%EC%97%B0%EB%8F%99-url-%EC%83%9D%EC%84%B1%ED%95%98%EA%B8%B0)
0612
검색
![](images/image_118.png)
![](images/image_119.png)
<empty-block/>
[https://developers.naver.com/docs/serviceapi/datalab/search/search.md#통합-검색어-트렌드](https://developers.naver.com/docs/serviceapi/datalab/search/search.md#%ED%86%B5%ED%95%A9-%EA%B2%80%EC%83%89%EC%96%B4-%ED%8A%B8%EB%A0%8C%EB%93%9C)
![](images/image_120.png)
![](images/image_121.png)
![](images/image_122.png)
---
<empty-block/>
2단계 인증 설정
![](images/image_123.png)
![](images/image_124.png)
![](images/image_125.png)
[https://console.cloud.google.com/](https://console.cloud.google.com/projectselector2/apis/credentials?pli=1&supportedpurview=project)
![](images/image_126.png)
![](images/image_127.png)
<empty-block/>
![](images/image_128.png)
![](images/image_129.png)
<empty-block/>
OAuth 만들기
![](images/image_130.png)
클라이언트 만들기
![](images/image_131.png)
![](images/image_132.png)
<empty-block/>
![](images/image_133.png)
<empty-block/>
---
[https://fullcalendar.io/](https://fullcalendar.io/)
![](images/image_134.png)
<empty-block/>
![](images/image_135.png)
![](images/image_136.png)
![](images/image_137.png)
---
<empty-block/>
![](images/image_138.png)
<empty-block/>
google calender api
![](images/image_139.png)
<empty-block/>
사용 클릭
![](images/image_140.png)
<empty-block/>
<empty-block/>
---
![](images/image_141.png)
![](images/image_142.png)
![](images/image_143.png)
![](images/image_144.png)
<empty-block/>
![](images/image_145.png)
<empty-block/>
<empty-block/>
![](images/image_146.png)
![](images/image_147.png)
<empty-block/>
![](images/image_148.png)
![](images/image_149.png)
![](images/image_150.png)
[https://www.googleapis.com/auth/calendar](https://www.googleapis.com/auth/calendar)
<empty-block/>
![](images/image_151.png)
![](images/image_152.png)
![](images/image_153.png)
<empty-block/>
<empty-block/>
<empty-block/>
사용자인증정보api
key=API_KEY
AIzaSyA7Z9gpMSqNRMDT5bBsd5CBMREPzecdhNI
<empty-block/>
캘린더 ID<br>[b9fa6f9609d3d7ca840605efc35f53cde243799f2b675b8d790c53a068871721@group.calendar.google.com](mailto:b9fa6f9609d3d7ca840605efc35f53cde243799f2b675b8d790c53a068871721@group.calendar.google.com)
<empty-block/>
---
6.15
![](images/image_154.png)
<empty-block/>
![](images/image_155.png)
가입
![](images/image_156.png)
<empty-block/>
개발자센터
[https://developers.portone.io/opi/ko/readme?v=v2](https://developers.portone.io/opi/ko/readme?v=v2)
SDK 놀이터
[https://sdk-playground.portone.io/?_gl=1\*1d7q1r3\*_gcl_au\*Mzk1NDc5ODAxLjE3ODE0ODI1OTU.\*_ga\*MTk3OTc3NTgyOC4xNzgxNDgyNTk1\*_ga_PD0FDL16NZ\*czE3ODE0ODI1OTUkbzEkZzEkdDE3ODE0ODI4MjgkajE5JGwwJGgw](https://sdk-playground.portone.io/?_gl=1*1d7q1r3*_gcl_au*Mzk1NDc5ODAxLjE3ODE0ODI1OTU.*_ga*MTk3OTc3NTgyOC4xNzgxNDgyNTk1*_ga_PD0FDL16NZ*czE3ODE0ODI1OTUkbzEkZzEkdDE3ODE0ODI4MjgkajE5JGwwJGgw)
<empty-block/>
![](images/image_157.png)
![](images/image_158.png)
![](images/image_159.png)
![](images/image_160.png)
![](images/image_161.png)
![](images/image_162.png)
<empty-block/>
<empty-block/>
![](images/image_163.png)
<empty-block/>
![](images/image_164.png)
![](images/image_165.png)
<empty-block/>
![](images/image_166.png)
![](images/image_167.png)
<empty-block/>
![](images/image_168.png)
![](images/image_169.png)
<empty-block/>
<empty-block/>
휴대폰 결제 막아둬서 카드로 결제 재실행
<empty-block/>
![](images/image_170.png)
<empty-block/>
<empty-block/>
![](images/image_171.png)
![](images/image_172.png)
<empty-block/>
<empty-block/>
![](images/image_173.png)
<empty-block/>
![](images/image_174.png)
<empty-block/>
<empty-block/>
솔라피 회원가입 - APIKEY생성(내 ip만 허용)
[https://console.solapi.com/credentials](https://console.solapi.com/credentials)
![](images/image_175.png)
![](images/image_176.png)
<empty-block/>
<empty-block/>
[https://console.firebase.google.com/](https://console.firebase.google.com/)
![](images/image_177.png)
![](images/image_178.png)
<empty-block/>
앱추가
![](images/image_179.png)
<empty-block/>
![](images/image_180.png)
<empty-block/>
![](images/image_181.png)
<empty-block/>
웹 푸시 인증서 발급 
![](images/image_182.png)
<empty-block/>
<empty-block/>
키 생성
서비스계정 - 새 비공개 키 생성
![](images/image_183.png)
<empty-block/>
json 파일 코드와 같은 파일 안에 넣기
<empty-block/>
<empty-block/>
![](images/image_184.png)
<empty-block/>
<empty-block/>
<empty-block/>
![](images/image_185.png)
<empty-block/>
---
6.16
<empty-block/>
![](images/image_186.png)
![](images/image_187.png)
<empty-block/>
<empty-block/>
<empty-block/>
---
<empty-block/>
![](images/image_188.png)
<empty-block/>
<empty-block/>
![](images/image_189.png)
![](images/image_190.png)
<br><br>`  implementation 'org.springframework.boot:spring-boot-starter-batch'`
![](images/image_191.png)
<empty-block/>
---
<empty-block/>
06.18
![](images/image_192.png)
<empty-block/>
<file src="file://%7B%22source%22%3A%22attachment%3A57fad220-e954-46b9-a017-8882ed28382f%3Ademo.zip%22%2C%22permissionRecord%22%3A%7B%22table%22%3A%22block%22%2C%22id%22%3A%2238320a7d-9f4c-8069-8c20-ea0d354c2069%22%2C%22spaceId%22%3A%22e3e20a7d-9f4c-816c-a8a0-0003c6ad3a11%22%7D%7D"></file>
<empty-block/>
---
6.19
![](images/image_193.png)
![](images/image_194.png)
<empty-block/>
<empty-block/>
**REST API 키 클라이언트 시크릿**
![](images/image_195.png)
<empty-block/>
[http://localhost:8080/login/oauth2/code/kakao](http://localhost:8080/login/oauth2/code/kakao) 경로추가
![](images/image_196.png)
<empty-block/>
<empty-block/>
![](images/image_197.png)
<empty-block/>
<empty-block/>
![](images/image_198.png)
<empty-block/>
<empty-block/>
<empty-block/>
---
-6.22
![](images/image_199.png)
<empty-block/>
<empty-block/>
<empty-block/>
[https://www.jwt.io/](https://www.jwt.io/)
<empty-block/>
![](images/image_200.png)
<empty-block/>
---
06.23
![](images/image_201.png)
<empty-block/>
<empty-block/>
![](images/image_202.png)
<empty-block/>
<empty-block/>
<empty-block/>
<empty-block/>
![](images/image_203.png)
![](images/image_204.png)
![](images/image_205.png)
![](images/image_206.png)
![](images/image_207.png)
<empty-block/>
<empty-block/>
<empty-block/>
<empty-block/>
<empty-block/>
<empty-block/>
<empty-block/>
<empty-block/>
<empty-block/>
<empty-block/>
<empty-block/>
<empty-block/>
<empty-block/>
<empty-block/>
<empty-block/>
<empty-block/>
<empty-block/>
<empty-block/>
<empty-block/>
<empty-block/>
<empty-block/>
