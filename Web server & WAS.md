# Web server & WAS

![캡처](https://user-images.githubusercontent.com/63223374/86771402-1f85b700-c08d-11ea-8b6b-0b9926d59aa4.PNG)

### Web server

- 웹 서버의 역할
  1. Static resource 뿌려주기 - http 파일, 이미지, html, css
  2. Security - 방화벽 바깥에 web server가 위치하고 방화벽 안쪽에 WAS, DB가 위치,  SSL 처리
  3. Load balancing - 하나의 Webserver가 여러 개의 WAS 서버에게 업무 분배
  4. 웹 브라우저 클라이언트로부터 HTTP요청을 받아들임



- 웹 서버의 장점
  1.  Static resourc 처리를 빨리 해준다
  2. WAS 서버의 주소 노출이 되지 않아 보안이 강화된다 (port 번호를 숨길 수 있음)
  3. 여러 개의 WAS의 업무를 분배하여 자원을 효율적으로 활용할 수 있다



**Apache**

```
1. apt-get install apache2 // apt-get 명령어로 Apache 설치

2. apache2 -v // 버전 확인


3. systemctl restart apache2 // 시스템 재시작
4. systemctl enable apache2 // 시스템 구동
5. systemctl status apache2 // 상태 확인
6. systemctl stop apache2 // 시스템 종료 
```

![그림1](https://user-images.githubusercontent.com/63223374/86769265-d8e28d80-c089-11ea-8a27-03b880a5b128.png)



7. **웹 서버 동작 확인**

- 파이어폭스 주소창에 localhost or 127.0.0.1 or 내 ip주소를 입력하여 Apache2가 정상 작동하는지 확인

- 원래 홈페이지 만들 때 기본 디렉토리 : /var/www/html/

  여기에 index.html 파일을 보면 localhost 홈페이지가 있음

  ![그림2](https://user-images.githubusercontent.com/63223374/86769582-53131200-c08a-11ea-9132-738b72885376.png)

- 새로운 new 라는 디렉토리를 생성하고 html 파일을 만들고싶다

![그림3](https://user-images.githubusercontent.com/63223374/86769585-53aba880-c08a-11ea-9e6e-cb2f04dc2b11.png)



8. **Apache server의 home directory 변경**

![그림4](https://user-images.githubusercontent.com/63223374/86770086-1b589a00-c08b-11ea-9002-890e6335ba7b.png)

- 위 경로로 들어가서 DocumentRoot를 내가 원하는 home directory로 변경

![그림5](https://user-images.githubusercontent.com/63223374/86770156-33301e00-c08b-11ea-9be1-3bc102712d33.png)

- 내가 원하는 곳으로 디렉토리를 변경

![그림6](https://user-images.githubusercontent.com/63223374/86770159-34614b00-c08b-11ea-9c38-ad023faca81b.png)



9. **Directory 설정 변경**

`/etc/apache2/apache2.conf`

![그림7](https://user-images.githubusercontent.com/63223374/86770479-b94c6480-c08b-11ea-9946-0b265856e817.png)



10. **방화벽 해제**

`ufw allow 80` - 포트 허용 (Apache 웹서버는 포트 번호가 80이다.)

`ifconfig` - 명령으로 가상머신의 IP 주소 확인



<hr>

### WAS

- WAS의 역할
  1. 동적인 데이터 처리
  2. 프로그램 실행 환경과 DB접속 기능 제공
  3. 트랜잭션 관리
  4. 업무 처리하는 비즈니스 로직 수행



**Tomcat 9**

```
1. apt-get install tomcat9* // Tomcat9 설치

2. systemctl restart tomcat9 // 시스템 재시작
3. systemctl enable tomcat9 // 시스템 구동
4. systemctl status tomcat9 // 상태 확인
5. systemctl stop tomcat9 // 시스템 종료
```



6. **설치 확인**

- 파이어 폭스에 localhost:8080 입력 (8080은 tomcat에서 정한 port번호)
- tomcat 기본 경로 - `/var/lib/tomcat9/webapps/ROOT`
- 경로 변경 - `/etc/tomcat9/server.xml`

![그림8](https://user-images.githubusercontent.com/63223374/86772302-b141f400-c08e-11ea-9888-a0ad44959cab.png)



7. **deploy 할 수 있는 방법 2가지**

   1. Tomcat admin을 사용하여 deploy

   2. 직접 app을 폴더에 넣어서 deploy

      

      **7-1. Tomcat-admin** (GUI 관리도구)

>  **Deploy 란?**
>
> Bulid된 .war 파일을 WAS에 올려 사용자들이 이용할 수 있도록 배포하는 것

- Tomcat의 app을 deploy, 설정 변경할 수 있는 관리 도구

- 주소 : localhost:8080/manager (포트번호 : 8080)

- Admin 페이지를 사용하기 위한 권한 부여

  `/etc/tomcat9/tomcat-users.xml`에 아래 사항 추가

  ![그림9](https://user-images.githubusercontent.com/63223374/86773807-f23b0800-c090-11ea-9e44-1af604356c76.png)

> admin 화면

![그림10](https://user-images.githubusercontent.com/63223374/86774320-65dd1500-c091-11ea-9f3a-9bbe1f8cd9e4.png)



​			**7-2. CLI 방식**

`/var/lib/tomcat9/webapps/`내에 war파일 위치시킴



**WAR (Web Application aRchive)**

- Web appliction을 묶는 확장자
- 애플리케이션 실행을 위한 컴파일된 모든 클래스 파일, 설정 파일들이 모두 포함
- 웹 어플리케이션 설정을 정의한 배포 명세서 (web.xml) 존재



**Sample application을 Deploy해보고 확인해본다.**

https://tomcat.apache.org/tomcat-9.0-doc/appdev/sample/
이거를 설치하면 유저/Downloads 아래에 sample.war파일이 생성되었음을 알 수 있다.

이 war 파일을 /var/lib/tomcat9/webapps에 cp한다.

![그림11](https://user-images.githubusercontent.com/63223374/86776208-fcf69c80-c092-11ea-8290-650679b0e719.png)

실제로 Applications 목록에 sample이 있음을 알 수 있다.

![1](https://user-images.githubusercontent.com/63223374/86776503-3929fd00-c093-11ea-98c8-88c6f4ec757d.PNG)



8. **Apache와 Tomcat을 연결하는 connector 모듈**

`apt-get install libapache2-mod-jk*`

ㄴ connector 모듈 설치



**8-1. apache-tomcat connector 설정**

```
apache + tomcat 연동을 위해선 Connector가 필요
```



`/etc/libapache2-mod-jk/workersproperties` 

- Connector 설정파일
- Tomcat의 home directory, port, 통신 protocol을 설정

![그림12](https://user-images.githubusercontent.com/63223374/86777957-c4f05900-c094-11ea-9903-d18873284b40.png)

workers.properties에 들어가서 설정해줌

![그림14](https://user-images.githubusercontent.com/63223374/86778923-e867d380-c095-11ea-980f-19a8b5bdc781.png)



**8-2. webserver apache에 tomcat으로 요청을 보내도록 설정**

```
web server -> tomcat
```

`/etc/apache2/sites-avaliable/000-default.conf`

![그림15](https://user-images.githubusercontent.com/63223374/86782562-2bc44100-c09a-11ea-9176-3bf274797d02.png)

설정을 아래처럼 바꿔줌

![그림16](https://user-images.githubusercontent.com/63223374/86782566-2d8e0480-c09a-11ea-80b9-ea4333515745.png)

(/var/lib/tomcat9/webapps/ROOT 로 해놓으면 apache는 더이상 볼 수 없고 톰캣만 볼 수 있음)

(k 소문자로 해야함)



`/etc/apache2/mods-available/httpd-jk.conf`

![그림17](https://user-images.githubusercontent.com/63223374/86782742-6b8b2880-c09a-11ea-840e-8f97ba57ac69.png)

설정을 아래처럼 바꿔줌

![그림18](https://user-images.githubusercontent.com/63223374/86782746-6c23bf00-c09a-11ea-8374-60190990b8a6.png)



`/etc/apache2/mods-available/jk.load `

![그림19](https://user-images.githubusercontent.com/63223374/86782900-9c6b5d80-c09a-11ea-8844-c3b0a91cc010.png)

설정을 아래처럼 바꿔줌 (k소문자)

![그림20](https://user-images.githubusercontent.com/63223374/86782903-9d03f400-c09a-11ea-80f7-ea3fc602b4e3.png)



**8-3. WAS tomcat에 apache에서 오는 요청을 받으라고 설정**

```
/etc/tomcat9/server.xml 
```

![그림21](https://user-images.githubusercontent.com/63223374/86783118-dfc5cc00-c09a-11ea-9ae4-edb17fbbc1fd.png)

설정을 아래처럼 바꿔줌

![그림22](https://user-images.githubusercontent.com/63223374/86783121-e0f6f900-c09a-11ea-99b7-75573cb92c6d.png)



9. **localhost와 localhost:8080으로 들어갔을 때 동일한 화면이 나오면 정상 동작**
