![](images/image.png)

![](images/image_2.png)

```powershell
wsl --install
wsl --update
```
![](images/image_3.png)

Hyper-v 체크

![](images/image_4.png)

Docker 설치

![](images/image_5.png)

설치완료 앱 열면

![](images/image_6.png)

설치 확인

![](images/image_7.png)

![](images/image_8.png)

```powershell
FROM node:18 란? node에서 이미지 가져옴(하단 사진)
```
node검색

![](images/image_9.png)

![](images/image_10.png)

확인 후 있으면 삭제
```powershell
docker images
```
![](images/image_11.png)

```powershell
npx create-react-app 01
```
![](images/image_12.png)

만들고 이 안에 Dockerfile 적어 넣기

빌드 실행 - 이미지 생성
```powershell
docker build -t node01:latest .
```
![](images/image_13.png)

이미지 확인
```powershell
docker images 
docker rmi [이미지 아이디 명] // 이미지 삭제
```
![](images/image_14.png)

도커 내 이미지 진입(확인용)
```powershell
docker run -it [이미지 아이디 명] sh
ls -l
```
![](images/image_15.png)

```powershell
# cd /app
# ls -l
# exit // 탈출 명령어
```

![](images/image_16.png)

임시 컨테이너 생성 후 외부 포트와 연결
```powershell
docker run -it --rm -p 3000:3000 node01:latest
```
![](images/image_17.png)

dockerfile fn에 만들어ㅓ새로 적고
```powershell
docker build -t  fn:1.1 .
```
![](images/image_18.png)

```powershell
docker images
docker run -it 93e311766584 sh
ls -l
```
```powershell

C:\Fullstack~~\Fullstack_Docker\00_INIT\01>docker images
                                                                                                             i Info →   U  In Use
IMAGE           ID             DISK USAGE   CONTENT SIZE   EXTRA
fn:1.1          93e311766584         95MB         26.5MB        
node01:latest   5e8df4690410       2.53GB          539MB        

C:\Fullstack~~\Fullstack_Docker\00_INIT\01>docker run -it 93e311766584 sh
/ # ls -l
total 64
drwxr-xr-x    2 root     root          4096 Jun 21 18:51 bin
drwxr-xr-x    5 root     root           360 Jul  6 02:02 dev
drwxr-xr-x    1 root     root          4096 Jun 22 19:46 docker-entrypoint.d
-rwxr-xr-x    1 root     root          1620 Jun 22 19:46 docker-entrypoint.sh
drwxr-xr-x    1 root     root          4096 Jul  6 02:02 etc
drwxr-xr-x    2 root     root          4096 Jun 21 18:51 home
drwxr-xr-x    1 root     root          4096 Jun 21 18:51 lib
drwxr-xr-x    5 root     root          4096 Jun 21 18:51 media
drwxr-xr-x    2 root     root          4096 Jun 21 18:51 mnt
drwxr-xr-x    2 root     root          4096 Jun 21 18:51 opt
dr-xr-xr-x  249 root     root             0 Jul  6 02:02 proc
drwx------    1 root     root          4096 Jul  6 02:02 root
drwxr-xr-x    3 root     root          4096 Jun 21 18:51 run
drwxr-xr-x    2 root     root          4096 Jun 21 18:51 sbin
drwxr-xr-x    2 root     root          4096 Jun 21 18:51 srv
dr-xr-xr-x   13 root     root             0 Jul  6 02:02 sys
drwxrwxrwt    2 root     root          4096 Jun 21 18:51 tmp
drwxr-xr-x    1 root     root          4096 Jun 21 18:51 usr
drwxr-xr-x    1 root     root          4096 Jun 21 18:51 var
/ # 
/ # 
/ # 
/ # pwd
/
/ # cd /usr/share/nginx/html
/usr/share/nginx/html # ls -l
total 48
-rw-r--r--    1 root     root           497 Jun 17 15:58 50x.html
-rw-r--r--    1 root     root           517 Jul  6 01:52 asset-manifest.json
-rwxr-xr-x    1 root     root          3870 Jul  6 01:52 favicon.ico
-rw-r--r--    1 root     root           644 Jul  6 01:52 index.html
-rwxr-xr-x    1 root     root          5347 Jul  6 01:52 logo192.png
-rwxr-xr-x    1 root     root          9664 Jul  6 01:52 logo512.png
-rwxr-xr-x    1 root     root           517 Jul  6 01:52 manifest.json
-rwxr-xr-x    1 root     root            70 Jul  6 01:52 robots.txt
drwxr-xr-x    4 root     root          4096 Jul  6 01:52 static
/usr/share/nginx/html # 
```
![](images/image_19.png)
```powershell
nginx -g "daemon off;"
```
![](images/image_20.png)

```powershell
docker run -it --rm -p 3000:80 fn:1.1
```
![](images/image_21.png)

BN에도 Dockerfile생성

```powershell
docker build -t bn:1.1 .
```
![](images/image_22.png)

```powershell
docker run -it bn:1.1 sh
ls -l
java -jar app.jar
```
```powershell
PS C:\Fullstack~~\Fullstack_Docker\01_Images\BN> docker run -it bn:1.1 sh
/app # 
/app # ls -l
total 70784
-rw-r--r-- 1 root root 72482543 Jul  6 02:17 app.jar
/app # java -jar app.jar
```
![](images/image_23.png)

```powershell
docker build -t mysql:1.1 . 
```
![](images/image_24.png)

```powershell
docker run -it --rm -p 3330:3306 mysql:1.1
```
![](images/image_25.png)

![](images/image_26.png)

![](images/image_27.png)

```powershell
docker ps
docker stop 20670c827286
```

![](images/image_28.png)

![](images/image_29.png)

---

```powershell
docker build -t redis:1.1 .
```
![](images/image_30.png)
```powershell
docker run -it --rm -p 6479:6379 reids:1.1
```
![](images/image_31.png)

확인

![](images/image_32.png)

---

```powershell
docker network
docker network create --driver bridge my-network
docker network ls
```

![](images/image_33.png)
```powershell
docker run -d --name db-container --network my-network -p 3330:3306 mysql:1.1
```
![](images/image_34.png)

```powershell
docker run -d --name redis-container --network my-network -p 6479:6379 redis:1.1
docker ps
```
![](images/image_35.png)

```powershell
docker ps
docker exec -it db-container bash
```
![](images/image_36.png)

```powershell
docker exec -it db-container bash
```
![](images/image_37.png)
```powershell
ping 127.0.0.1
```
![](images/image_38.png)
```powershell
bash-5.1# ping db-container
PING db-container (172.18.0.2) 56(84) bytes of data.
64 bytes from 82d4788a753d (172.18.0.2): icmp_seq=1 ttl=64 time=1.37 ms
64 bytes from 82d4788a753d (172.18.0.2): icmp_seq=2 ttl=64 time=0.047 ms
64 bytes from 82d4788a753d (172.18.0.2): icmp_seq=3 ttl=64 time=0.073 ms
64 bytes from 82d4788a753d (172.18.0.2): icmp_seq=4 ttl=64 time=0.040 ms
64 bytes from 8
```

![](images/image_39.png)

```powershell
docker build -t bn:1.1 .
```
![](images/image_40.png)

```powershell
docker run -d --name bn-container --network my-network -p 8080:8080 bn:1.1
```
![](images/image_41.png)

---

```powershell
C:\Fullstack~~\Fullstack_Docker\02_CONTAINER\FN>docker build -t fn:1.1 .
```
![](images/image_42.png)
```powershell
docker run -d --name fn-container --network my-network -p 3000:80 fn:1.1
```
![](images/image_43.png)

![](images/image_44.png)

nginx.conf 설정하고
```powershell
docker build -t fn:1.1 .
```
![](images/image_45.png)

```powershell
실행명령어
docker start bn-container fn-container
```

---

![](images/image_46.png)
```powershell
  implementation 'org.springframework.boot:spring-boot-starter-actuator'
```
![](images/image_47.png)

```powershell
docker compose up
docker compose down // 끄는 명령어
```
![](images/image_48.png)

---

07 07\\
```javascript
docker compose down
docker network ls // 열린 네트워크 확인
docker network rm 네트워크id // 네트워크 삭제

docker compose up // 네트워크 시작
// 구동확인 후 종료
```
```javascript
docker images
docker login

// https://docs.docker.com/ 웹에 회원가입 하고 리포 만들어 내이름/리포이름 넣어서 tag 
docker tag bn parkhangyeol/docker_app_test:bn
docker images // 확인하면 위 등록한 것 나온다
docker tag fn parkhangyeol/docker_app_test:fn 
docker tag db parkhangyeol/docker_app_test:db 
docker tag redis parkhangyeol/docker_app_test:redis 
```
![](images/image_49.png)
```javascript
docker login
docker push parkhangyeol/docker_app_test:bn
docker push parkhangyeol/docker_app_test:fn
docker push parkhangyeol/docker_app_test:db 
docker push parkhangyeol/docker_app_test:redis 

// 웹 보고 새로고침 해서 이미지 다 올라왔는지 확인

// 도커 앱 열기
// 컨테이너, 이미지, 볼륨 삭제
```
![](images/image_50.png)

![](images/image_51.png)

04_doker_hub 로 이동
```javascript
docker compose up

```
![](images/image_52.png)

---

![](images/image_53.png)

![](images/image_54.png)

<file src="file://%7B%22source%22%3A%22attachment%3A38bcb1d3-e24b-4cfc-8e9a-d4de3d885fc6%3Ademo.zip%22%2C%22permissionRecord%22%3A%7B%22table%22%3A%22block%22%2C%22id%22%3A%2239620a7d-9f4c-80de-98c6-e7a3cffff28a%22%2C%22spaceId%22%3A%22e3e20a7d-9f4c-816c-a8a0-0003c6ad3a11%22%7D%7D"></file>

```javascript
.\gradlew clean build
```
![](images/image_55.png)
```javascript
만들어진 build-libs에서
오른쪽마우스 - 다음에서 열기 - cmd 
cmd에서 

java -jar demo-0.0.1-SNAPSHOT.jar
```
![](images/image_56.png)

![](images/image_57.png)

생성해둔 퍼블릭 깃허브 저장소로 push하기

![](images/image_58.png)

---

로그인 - 프리티어

![](images/image_59.png)

서울로 설정

![](images/image_60.png)

별 찍기

![](images/image_61.png)

인스턴스 시작

![](images/image_62.png)

![](images/image_63.png)

![](images/image_64.png)

<file src="file://%7B%22source%22%3A%22attachment%3Afcf6c300-06db-472c-a3f8-29d2c931dfae%3ADEPLOY_SBONLY.pem%22%2C%22permissionRecord%22%3A%7B%22table%22%3A%22block%22%2C%22id%22%3A%2239620a7d-9f4c-805c-8416-e0d59735264b%22%2C%22spaceId%22%3A%22e3e20a7d-9f4c-816c-a8a0-0003c6ad3a11%22%7D%7D"></file>

30gib로 변경(프리티어 한계)

![](images/image_65.png)

완료

![](images/image_66.png)

ip 주소 할당

![](images/image_67.png)

![](images/image_68.png)

![](images/image_69.png)

![](images/image_70.png)

규칙설정

![](images/image_71.png)

![](images/image_72.png)

![](images/image_73.png)

putty다운 

![](images/image_74.png)

![](images/image_75.png)

설치

![](images/image_76.png)

로드 해서 키 클릭하고 save privatekey

![](images/image_77.png)

![](images/image_78.png)

![](images/image_79.png)

![](images/image_80.png)

프라이빗키추가

![](images/image_81.png)

퍼블릭 주소 넣고 저장 하고 열기

# PuttY 비밀번호

#### ec2-user

#### sudo su

![](images/image_82.png)
```javascript
sudo su
-----------------------------------------------
2 TIMEZONE설정
-----------------------------------------------
sudo rm /etc/localtime
sudo ln -s /usr/share/zoneinfo/Asia/Seoul /etc/localtime
```
![](images/image_83.png)

```javascript
-----------------------------------------------
3 SWAP 설정 
-----------------------------------------------

------------------------
스왑 파일 생성하기
------------------------
sudo dd if=/dev/zero of=/swapfile bs=128M count=16
ls -l /dev/zero
```
![](images/image_84.png)

```javascript
------------------------
스왑 파일에 대한 읽기 쓰기 권한 업데이트하기
------------------------
sudo chmod 600 /swapfile
```
![](images/image_85.png)

```javascript
------------------------
Linux 스왑 영역 설정하기
------------------------
sudo mkswap /swapfile

```
![](images/image_86.png)

```javascript
------------------------
스왑 공간에 스왑 파일을 추가하여 스왑 파일을 즉시 사용할 수 있도록 하기
------------------------
sudo swapon /swapfile
```
![](images/image_87.png)
```javascript
------------------------
절차가 성공했는지 확인하기
------------------------
sudo swapon -s
```
![](images/image_88.png)

```javascript
------------------------
/etc/fstab 파일을 편집하여 부팅 시 스왑 파일을 활성화하기
------------------------
파일 열기, 영어 O클릭해 편집모드
sudo vi /etc/fstab  

파일 가장 마지막에 다음을 추가하고 esc누르고 :wq로 저장하고 종료
/swapfile swap swap defaults 0 0
```
![](images/image_89.png)

```javascript
------------------------
free 명령어로 메모리 확인하기
------------------------
free
```
![](images/image_90.png)

```javascript
-----------------------------------------------
JDK 설치
-----------------------------------------------
sudo su
yum install -y java-21
```
![](images/image_91.png)
```javascript
java --version
```
![](images/image_92.png)

위쪽에 추가

settings.gradle
```javascript
plugins {
    id 'org.gradle.toolchains.foojay-resolver-convention' version '0.8.0'
}

rootProject.name = 'demo'
```
![](images/image_93.png)
```javascript
-----------------------------------------------
GIT 설치
-----------------------------------------------
yum install -y git 
```
![](images/image_94.png)

```javascript

mkdir /app
cd /app
pwd
/app
git clone https://github.com/MyFullStack0/16_DEPLOY_SBONLY.git
```
![](images/image_95.png)

```javascript
cd 16_DEPLOY_SBONLY
ls -l
chmod o+x gradlew 
ls -l
./gradlew build
```
![](images/image_96.png)

![](images/image_97.png)

```javascript
./gradlew build

```
![](images/image_98.png)

```javascript
cd build/libs
java -jar demo-0.0.1-SNAPSHOT.jar
```

서버 열리는지 확인

[3.39.56.29](http://3.39.56.29:8080/)

![](images/image_99.png)
```javascript
서버끄고
cd ../..
pwd
```
![](images/image_100.png)

MySQL Yum Repository

![](images/image_101.png)

![](images/image_102.png)

![](images/image_103.png)

![](images/image_104.png)

링크주소

[https://dev.mysql.com/get/mysql84-community-release-el10-3.noarch.rpm](https://dev.mysql.com/get/mysql84-community-release-el10-3.noarch.rpm)
```javascript

yum install https://dev.mysql.com/get/mysql84-community-release-el10-3.noarch.rpm
```

```javascript
yum install mysql-server
```
![](images/image_105.png)
```javascript
// 설치 오류로 고침
# 저장소 파일의 버전을 9 로 고정 
sudo sed -i 's|/el/\$releasever/|/el/9/|g' /etc/yum.repos.d/mysql-community*.repo

sudo yum clean all
sudo yum install mysql-community-server

// 설치확인
systemctl status mysqld
```
![](images/image_106.png)

```javascript
 systemctl restart mysqld
  systemctl status mysqld
```
![](images/image_107.png)
```javascript
vi /var/log/mysqld.log
```
![](images/image_108.png)
```javascript
이 뒤쪽 패스워드 저장해두기  
k:T6?9%C(ITi    --->아래에서 Zhfldk11! 로 바뀜
```
![](images/image_109.png)

### SQL 비밀번호: Zhfldk11!
```javascript
mysql -u root -p
비번복사해서 오른쪽 마우스 클릭 , 엔터

alter user root@localhost identified by 'Zhfldk11!';
create database testdb;
create user roottest@'%' identified by 'Zhfldk11!';
grant all privileges on testdb.* to roottest;
```
![](images/image_110.png)

![](images/image_111.png)

### SQL DB 이름
```javascript
mysql새로운 Connections 만들기

이름 AWS_DB
유저네임  roottest
호스트네임(오픈)   3.39.56.29 // 퍼블릭 IPv4 주소로 입력 
확인하고

quit
systemctl enable mysqld
exit
exit
```
![](images/image_112.png)

![](images/image_113.png)
```javascript
안쓸때 중지
```
![](images/image_114.png)

![](images/image_115.png)

---

0708

![](images/image_116.png)

![](images/image_117.png)

Putty 오픈

![](images/image_118.png)

```javascript
ec2-user 

sudo su
```
```javascript
sudo wget -O /etc/yum.repos.d/jenkins.repo \
    https://pkg.jenkins.io/rpm-stable/jenkins.repo
    
    
sudo yum upgrade

sudo yum install fontconfig

sudo yum install jenkins
```
![](images/image_119.png)

![](images/image_120.png)
```javascript
sudo systemctl daemon-reload
ctl status jenkins
```
![](images/image_121.png)
```javascript

vi /usr/lib/systemd/system/jenkins.service

읽기전용으로열린다면?
sudo vim /usr/lib/systemd/system/jenkins.service

:set number
:72
영문자 i로 편집, 편집해제 esc
72번줄 포트 9090으로 변경 (여기서부터 이상해짐)

:wq로 나가기
```
![](images/image_122.png)

보안 규칙 추가

![](images/image_123.png)
```javascript
systemctl restart jenkins

systemctl enable jenkins

systemctl status jenkins

(엑티브 러닝이 떠야함)
```
![](images/image_124.png)

### 링크 [http://43.203.71.13:9090/login](http://43.203.71.13:9090/login)

[`http://43.203.71.13:9090/login`](http://43.203.71.13:9090/login)  접속
```javascript
cat /var/lib/jenkins/secrets/initialAdminPassword
```

![](images/image_125.png)

받은 패스워드 링크에 복붙해서 클릭
```javascript
5f5d16296a834aa681ae846fb76a718f
```
![](images/image_126.png)

왼쪽 인스톨 클릭

![](images/image_127.png)

![](images/image_128.png)

관리자 계정 생성

![](images/image_129.png)

![](images/image_130.png)

![](images/image_131.png)

![](images/image_132.png)

ㄴ 빌드 오프라인(정상, 아래에서 변경)

### 젠킨스 로그인 계정명: marine3682
```javascript
계정명 marine3682
이름 marine3682
이메일주소 marine3682@gmail.com
```

**/etc/fstab 수정**
```plain text
vi /etc/fstab

// 파일 들어가지면 i로 수정모드 진입해서 맨 아래에 하단 입력
tmpfs   /tmp    tmpfs   size=5g,mode=1777   0   0

:wq로 종료

df -h //로 확인
mount -a // 적용
df -h //로 확인. 템프 사이즈가 올라감...??
reboot  //재부팅
ec2-user //로그인
```
![](images/image_133.png)

![](images/image_134.png)

깃허브 프로필-setting 

Developer Settings클릭

access tokens 클릭

tokens(classic)눌러서 만들기

![](images/image_135.png)

note에 JENKINS-TOKEN 작성

체크박스

workflow빼고 다 체크

![](images/image_136.png)

만들어진 토큰 복사

### 깃허브 젠킨스 토큰
```javascript
ghp_************************************ (REDACTED — 원본 노출로 폐기 필요)
```
![](images/image_137.png)

---

젠킨스를 다시 들어감

![](images/image_138.png)

ㄴ 오프라인 표시 사라짐

톱니바퀴 버튼 - system클릭

![](images/image_139.png)

하단 쭈욱 내려가다 보면 GitHub가 보임

- add 깋버브 서버 클릭

![](images/image_140.png)

이름 설정, api url은 그대로, Credentials은 옆 +add 버튼 클릭

시크릿: 깃허브 아까받은 토큰값

아이디와 Desc…: GITHUBTOKEN(자유설정)

![](images/image_141.png)

![](images/image_142.png)

크리에이트

크리에이트클릭—-베리파인드..뜨면됨

save클릭

---

설정 tools

cmd에서
```javascript
alternatives --config java

뜨는..
/usr/lib/jvm/java-21-amazon-corretto.x86_64
복붙해둠
```
![](images/image_143.png)

![](images/image_144.png)

JDK install…에서 +add누르고

![](images/image_145.png)

위에 복사해둔거 붙여넣기 (빨간 느낌표 무시)

![](images/image_146.png)

jdk 변경

원 파일에서 properties들어가서 url 확인 gradle

![](images/image_147.png)

파일 gradle

![](images/image_148.png)

에서 propert..에서 GRADLE-8.14.5 적고

버전도 똑같이 찾아서 누르고

![](images/image_149.png)

save클릭.

플러그인 클릭

![](images/image_150.png)

인스톨플러그인 에서 

gradle있는지확인

![](images/image_151.png)

available플러그인에서

github integr 검색해 클릭, 인스톨

![](images/image_152.png)

Post build task설치

![](images/image_153.png)

 + 새로운 Item

![](images/image_154.png)

이름에

DEPLOY_SBONLY

두번째 프리스타일 클릭

![](images/image_155.png)

배포

---

깃허브 들어가서 배포하려는 리포 링크 따오기

### 깃허브 젠킨스 레포 링크

[https://github.com/MyFullStack0/16_DEPLOY_SBONLY.git](https://github.com/MyFullStack0/16_DEPLOY_SBONLY.git)

![](images/image_156.png)

![](images/image_157.png)

Conf..

소스 코드 관리

소스코드 관리에 url에 깃허브 링크 넣기

\*/main 으로 변경

![](images/image_158.png)

Triggers에 깃허브 훅 체크박스 클릭

![](images/image_159.png)

build steps에

version GRADIE=8.14.5

Tasks=clean build

![](images/image_160.png)

빌드후조치

Log text =SUCCESS

t스크립트에 이거 복붙
```javascript
#!/bin/bash

# 프로세스를 실행한 Java 명령어와 JAR 파일 경로를 지정합니다.
JAVA_COMMAND="java -jar"
JAR_PATH="/var/lib/jenkins/workspace/DEPLOY_SBONLY/build/libs/demo-0.0.1-SNAPSHOT.jar"

# 해당 Java 프로세스를 찾아서 PID를 얻어냅니다.
TARGET_PID=$(pgrep -f "$JAVA_COMMAND $JAR_PATH")

# PID를 확인하고 종료합니다.
if [ -z "$TARGET_PID" ]; then
    echo "해당 프로세스가 이미 종료되었습니다."
else
    echo "프로세스 $TARGET_PID 종료 중..."
    kill -9 "$TARGET_PID"
    sleep 2

    # 종료 후 확인
    if ps -p "$TARGET_PID" > /dev/null; then
        echo "프로세스 $TARGET_PID 종료 실패"
    else
        echo "프로세스 $TARGET_PID 성공적으로 종료됨"
    fi
fi

BUILD_ID=dontKillMe nohup java -jar /var/lib/jenkins/workspace/DEPLOY_SBONLY/build/libs/demo-0.0.1-SNAPSHOT.jar > /var/lib/jenkins/workspace/DEPLOY_SBONLY/app.log 2>&1 &
disown
echo "새 프로세스 실행 완료"

```
![](images/image_161.png)

저장.

---

지금 빌드 클릭

![](images/image_162.png)

![](images/image_163.png)

빌드확인

![](images/image_164.png)

## 스냅샷 실행 코드
```javascript
cd /home/ec2-user/Fullstack_DeployDocker/15_DOCKER/04_DOCKER_COMPOSE_DEPLOY
ls -l
```
```javascript
cd /var/lib/jenkins/workspace/DEPLOY_SBONLY
ls -l

cd build/libs
ls -l

java -jar demo-0.0.1-SNAPSHOT.jar

// 상대경로 적어 실행
java -jar ./build/libs/demo-0.0.1-SNAPSHOT.jar
```
실행확인

![](images/image_165.png)

---

---

---

---

깃허브

디플로이 레포 드가고

settings

webhooks

add webhook클릭\<

나온 화면에

(젠킨스 링크)/깃허브\~붙이기

[http://3.39.56.29:9090/](http://3.39.56.29:9090/)github-webhook/

contents type 을 ap…/json 으로 변경

SSL를 Disable 로 변경

![](images/image_166.png)

맨아래체크박스

끗버튼

---

aws

---

잰킨스에서

구성

깃허브훅트리거…..ㅍ어쩌고랑연결된거임

![](images/image_167.png)

이제 로컬에서 작업하고 깃헙 푸시하면 빌드스에 #4자동으로뜸

인덱스에 ++
```html
    <p>
        DEPLOY_TEST_02
    </p>
    <p>
        DEPLOY_TEST_03
    </p>
    <p>
        DEPLOY_TEST_04
    </p>
```
터미널로
```javascript
git add *
git commit -m .
git push origin
```
![](images/image_168.png)

자동 반영 확인

![](images/image_169.png)

![](images/image_170.png)

---

## 젠킨스 주소, 아이디<br>[http://3.39.56.29:9090/](http://3.39.56.29:9090/) 

[http://3.39.56.29:9090/](http://3.39.56.29:9090/) 

아이디 marine3682

지금빌드

![](images/image_171.png)

인덱스 약간수정하고 푸시

빌드 확인

![](images/image_172.png)

가비아 도메인 1개 구매\<

aws에서 검색

![](images/image_173.png)

호스팅 영역 생성

![](images/image_174.png)

![](images/image_175.png)

![](images/fsdfs.png)

이제 저 라우팅 대상 링크들을 가비아에 복붙(맨뒤 점 생략)

네임서버 - 설정

![](images/image_176.png)

![](images/dsfdsfffffffffff.png)

레코드 생성

![](images/image_177.png)

보안 - 보안그룹

80 애니웨어

![](images/image_178.png)

이제 좀 기다리면서 스냅샷으로 pn 재생해놓고

### 스냅샷 재생2
```javascript
 cd /app/16_DEPLOY_SBONLY
java -jar build/libs/demo-0.0.1-SNAPSHOT.jar
```
사이트 링크로 접속하면 연결 확인

![](images/image_179.png)

443 애니웨어 2종 추가

![](images/image_180.png)

SSL 인증서 발급

### 내 사이트 링크<br>[myfleet.site](http://www.myfleet.site/)

putty로 와서 certbot설치
```javascript
# 인증서 발급 패키지 설치
yum install certbot
# 인증서 발급 진행
certbot certonly --standalone ...

```
![](images/image_181.png)
```javascript

[root@ip-172-31-37-201 16_DEPLOY_SBONLY]# openssl ec -in /etc/letsencrypt/live/www.myfleet.site/privkey.pem -check
read EC key
EC Key valid.
writing EC key
-----BEGIN EC PRIVATE KEY-----
MHcCAQEEIG3D8qLu28m/UiCxOo94059qK/IV9dvddMWOmKOjTVq2oAoGCCqGSM49
AwEHoUQDQgAENz9UN0NLRmfwxQ9OkozkqVOviRCdWww9eegkrexk2rrD0vcIp2aV
L/2Wmq5GYLm2mAosCKi5osbIVvxoljZuxQ==
-----END EC PRIVATE KEY-----

```

```javascript
cd /etc/letsencrypt/live/www.myfleet.site
// 비밀번호 설정 2회
sudo openssl pkcs12 -export -in fullchain.pem -inkey privkey.pem -out keystore.p12 -name ttp -CAfile chain.pem -caname root

ls // privkey.pem 나오면 ok
비번 구글비번
```
![](images/image_182.png)

하나 창 더 열고
```javascript

[root@ip-172-31-37-201 ec2-user]# chmod -R o+rx /etc/letsencrypt/live

```
![](images/image_183.png)

pem.. 키가 있는 폴더에 cmd열어ㅛㅛyes
```javascript
scp -i DEPLOY_SBONLY.pem ec2-user@3.39.56.29:/etc/letsencrypt/live/www.myfleet.site/keystore.p12 .

```
리소스- ssl에 키 넣고

![](images/image_184.png)

프로포티에
```javascript
server.port=443
server.ssl.key-store=classpath:ssl/keystore.p12
server.ssl.key-store-type=PKCS12
server.ssl.key-store-password=123456
```

![](images/image_185.png)

아무거나 수정하고 푸시

```javascript
# 서버 실행
sudo nohup java -jar /var/lib/jenkins/workspace/DEPLOY_SBONLY/build/libs/demo-0.0.1-SNAPSHOT.jar &

vi /etc/sudoers
: se nu
:100

# 적당한 위치에 추가
root    ALL=(ALL)       ALL 아래로추가
jenkins ALL=(ALL)       NOPASSWD:/usr/bin/nohup
jenkins ALL=(ALL)       NOPASSWD:/usr/bin/java
jenkins ALL=(ALL)       NOPASSWD:/usr/bin/kill

# 저장 후 종료
:wq

```

하고 터미널에
```javascript
reboot
```

<br>젠킨스 설정맨아래 빌드후조치

![](images/image_186.png)

```javascript
#!/bin/bash

# 프로세스를 실행한 Java 명령어와 JAR 파일 경로를 지정합니다.
JAVA_COMMAND="java -jar"
JAR_PATH="/var/lib/jenkins/workspace/DEPLOY_SBONLY/build/libs/demo-0.0.1-SNAPSHOT.jar"

# 해당 Java 프로세스를 찾아서 PID를 얻어냅니다.
TARGET_PID=$(pgrep -f "$JAVA_COMMAND $JAR_PATH")

# PID를 확인하고 종료합니다.
if [ -z "$TARGET_PID" ]; then
    echo "해당 프로세스가 이미 종료되었습니다."
else
    echo "프로세스 $TARGET_PID 종료 중..."
    sudo kill -9 "$TARGET_PID"
    sleep 2
    # 종료 후 확인
    if ps -p "$TARGET_PID" > /dev/null; then
        echo "프로세스 $TARGET_PID 종료 실패"
    else
        echo "프로세스 $TARGET_PID 성공적으로 종료됨"
    fi
fi

# 원래적혀있던 것에서 맨아래줄만 추가
sudo nohup java -jar /var/lib/jenkins/workspace/DEPLOY_SBONLY/build/libs/demo-0.0.1-SNAPSHOT.jar &

```

---

도커…새 레포 파서 04만들고 yml설정
```javascript
// 경로 C:\Fullstack~~\Fullstack_DeployDocker\15_DOCKER\04_DOCKER_COMPOSE_DEPLOY>

docker compose -f docker-compose-local.yml up
```
![](images/image_187.png)

명령어
```javascript
cd "C:\Fullstack~~\Fullstack_DeployDocker\15_DOCKER\04_DOCKER_COMPOSE_DEPLOY"
docker compose up -d --build
 ???

```
![](images/image_188.png)

동작 후 젠킨스 열어 동작확인

putty열기
```javascript
systemctl disable jenkins
systemctl stop jenkins

docker --version //없음
```
![](images/image_189.png)

### Docker 설치
```javascript
sudo yum update -y
sudo yum install docker -y
sudo systemctl start docker
sudo systemctl enable docker
sudo usermod -aG docker ec2-user

docker -v
docker --version // 버전 확인
```
![](images/image_190.png)

### **Docker compose 설치**
```plain text
DOCKER_COMPOSE_VERSION="v2.27.1"

sudo curl -L "https://github.com/docker/compose/releases/download/${DOCKER_COMPOSE_VERSION}/docker-compose-$(uname -s)-$(uname -m)" \
  -o /usr/local/bin/docker-compose

sudo chmod +x /usr/local/bin/docker-compose

sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose

docker-compose version  // 버전 확인
```
![](images/image_191.png)

```javascript
ps -elf | grep java
// root..아래로 표 형태 나옴. root 옆에 있는 번호 입력해 끄기

kill -9 숫자 
// anon_p.....grep --color=auto 빼고 다 kill
```
![](images/image_192.png)

레포 퍼블릭 설정

[https://github.com/MyFullStack0/Fullstack_DeployDocker.git](https://github.com/MyFullStack0/Fullstack_DeployDocker.git)

있음 지우고 없음 말고
```javascript
mkdir /app

cd 15_DOCKER
cd 04_DOCKER_COMPOSE_DEPLOY

docker -compose.yml
```

![](images/image_193.png)

![](images/image_194.png)

aws **인바운드 규칙 편집**

3000 포트-모든 ip, 3330-내 ip 열기 

![](images/image_195.png)

![](images/image_196.png)
```javascript
docker-compose up -d
```
### 링크2[http://3.39.56.29:3000/](http://3.39.56.29:3000/)

[http://3.39.56.29:3000/](http://3.39.56.29:3000/)

확인

![](images/image_197.png)

mysql열어 포트번호 3330변경

![](images/image_198.png)

![](images/image_199.png)

#### 비번 Zhfldk11!

들어가서 만들어진 테이블 확인

![](images/image_200.png)

4ㅂsecurityConfig 들어가서 메서드 보고 (”\*”) 설정

깃허브에 푸시

![](images/image_201.png)

켜놨던 putty 서버 컨트롤-c

### 도커 실행법
```javascript
docker-compose down
git pull origin // 깃허브에 수정사항 있으면 무조건 풀하고 재시작
docker rmi bn 
docker images
docker-compose up
// 주르륵 실행 됨
```
![](images/image_202.png)

오리진하고재시작?   수정사항 있으면 (깃허브) 무조건 재시작 해야한다.
```javascript
docker-compose down
git pull origin
docker rmi bn
docker-compose up
```
[http://3.39.56.29:3000/](http://3.39.56.29:3000/)

join 되는지 확인

![](images/image_203.png)

login 되는지 확인

![](images/image_204.png)

![](images/image_205.png)

파일 vscode로 열고 터미널 진행
```javascript
docker compose -f .\docker-compose-local.yml up
```
![](images/image_206.png)

젠킨스 켜졌다

[http://localhost:9090/](http://localhost:9090/)

![](images/image_207.png)

### **터미널 입력**

**Docker Container 내부진입명령어**
```plain text
docker exec -it  jenkins-container sh

/var/jenkins_home/secrets/initialAdminPassword

5646d880d3924c2b91c0bb52a848f7d5
```
![](images/image_208.png)

받은 것 젠킨스 password에 넣고 확인 클릭 한 뒤 가입

![](images/image_209.png)

토큰저장

![](images/image_210.png)

![](images/image_211.png)

![](images/image_212.png)

![](images/image_213.png)

![](images/image_214.png)

예전에 받아뒀던 키 pem값 이용 →   메모장으로 열기 해서 키 값 복붙

![](images/image_215.png)

플러그인 다운

![](images/image_216.png)

![](images/image_217.png)

뉴 아이템

![](images/image_218.png)

내 깃허브 링크 입력 [https://github.com/MyFullStack0/Fullstack_DeployDocker.git](https://github.com/MyFullStack0/Fullstack_DeployDocker.git)

![](images/image_219.png)

#### **Pipeline script** {toggle="true"}
	```plain text

pipeline {
    agent any

    environment {
        GITHUB_REPO = 'https://github.com/MyFullStack0/Fullstack_DeployDocker.git'
        TARGET_DIR = '15_DOCKER/04_DOCKER_COMPOSE_DEPLOY'
        EC2_HOST = '3.39.56.29'  // EC2 인스턴스의 퍼블릭 IP나 DNS
        EC2_USER = 'ec2-user'       // EC2 사용자 이름 (Amazon Linux의 경우 'ec2-user', Ubuntu의 경우 'ubuntu')
    }

    stages {
        stage('Clone and Deploy on EC2') {
            steps {
                withCredentials([sshUserPrivateKey(credentialsId: 'ec2-ssh-key', keyFileVariable: 'SSH_KEY')]) {
                    sh """
                        chmod 600 \${SSH_KEY}
                        ssh -i \${SSH_KEY} -o StrictHostKeyChecking=no \${EC2_USER}@\${EC2_HOST} "
                            # 기존 디렉토리 정리
                            sudo rm -rf Fullstack_DeployDocker && \\

                            # GitHub 저장소 클론
                            git clone ${GITHUB_REPO} && \\

                            # 작업 디렉토리로 이동
                            cd Fullstack_DeployDocker/${TARGET_DIR} && \\

                            # Docker 명령어 실행 (sudo 사용)
                            sudo docker-compose down || true && \\
                            sudo docker rm -f \$(sudo docker ps -aq) 2>/dev/null || true && \\
                            sudo docker rmi -f \$(sudo docker images -q) 2>/dev/null || true && \\

                            # 이미지 강제 재빌드 및 컨테이너 시작
                            sudo docker-compose build --no-cache && \\ 
                            sudo docker-compose up -d
                            # sudo docker-compose up -d --scale jenkins=0
                        "
                    """
                }
            }
        }
    }

    post {
        success {
            echo 'Deployment to EC2 completed successfully!'
        }
        failure {
            echo 'Deployment to EC2 failed!'
        }
    }
}

	```
![](images/image_220.png)

가비아 도메인 로그인

![](images/image_221.png)

```javascript
cmd

C:\Users\Administrator>nslookup
기본 서버:  kns.kornet.net
Address:  168.126.63.1

> www.myfleet.site
서버:    kns.kornet.net
Address:  168.126.63.1

권한 없는 응답:
이름:    www.myfleet.site
Address:  3.39.56.29

```
![](images/image_222.png)

추가

![](images/image_223.png)
