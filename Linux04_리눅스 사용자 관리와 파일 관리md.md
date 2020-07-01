<h1>리눅스 사용자 관리와 파일 관리

<h3>사용자와 그룹의 개념

- 리눅스는 다중 사용자 시스템

  - 리눅스 서버 1대에 여러 사용자가 동시에 접속
  - **슈퍼 유저**에게는 사용자 생성 권한을 포함해 모든 작업을 실행할 수 있는 권한 주어짐
  - 모든 사용자는 혼자 존재하는 것이 아니라 **하나 이상의 그룹에 소속**되어야 함
  - vi나 gedit으로 /etc/passwd 파일 열기 (**vi /etc/passwd**)
  - 각 행은 '사용자 이름 : 비밀번호 : 사용자 ID : 사용자 소속 그룹 ID : 추가 정보 : 홈 디렉터리 : 기본 셸'을 의미

  

- root 사용자 살펴보기

![17](https://user-images.githubusercontent.com/63223374/86191556-5423db00-bb82-11ea-9453-c95c22d9acc5.PNG)

사용자이름 : 비밀번호 : 사용자 ID : 속한 그룹 ID : 로그인 시 제공되는 셸



- **vi /etc/passwd** 파일 열어보기

![캡처](https://user-images.githubusercontent.com/63223374/86189970-09a05f80-bb7e-11ea-9d92-bba41de0dbde.PNG)

**사용자 이름 : 비밀번호 : 사용자 ID : 사용자 소속 그룹 ID : 추가 정보 : 홈 디렉터리 : 기본 셸**



사용자 이름 : cookuser2

비밀번호 : x -> /etc/shadow 파일에 비밀번호가 지정되어 있다는 의미

cookuser2의 사용자 ID는 1002, 속한 그룹의 ID는 2

추가정보

cookuser2 사용자의 홈 디렉터리는 /home/ubuntu

로그인시 제공되는 셸은 /bin/bash

root사용자를 살펴보면 사용자 ID와 소속 그룹 ID 모두 0으로 설정되어있음



- **vi /etc/group** 파일 열어보기
  - 각 행은 ‘그룹 이름:비밀번호:그룹 ID:보조 그룹 사용자’를 의미
  - 보조 그룹 사용자는 이 그룹을 주 그룹이 아닌 보조 그룹으로 사용하는 사용자의 목록
  - 여러 명이면 쉼표(,)로 구분

![333333333333](https://user-images.githubusercontent.com/63223374/86210644-e9899400-bbaf-11ea-8c88-e393d4a3334d.PNG)





<h3>사용자와 그룹 관련 명령어

![그림2](C:\Users\HP\Desktop\LINUX\20200701\그림2.PNG)

1. sudo su 키워드를 이용해 root계정으로 변환시킨다.
2. adduser 키워드를 사용하여 새로운 사용자를 추가한다.



```
adduser
```

![그림3-1](https://user-images.githubusercontent.com/63223374/86190234-d6aa9b80-bb7e-11ea-979a-4c91f415b426.png)

![그림3](https://user-images.githubusercontent.com/63223374/86190246-dad6b900-bb7e-11ea-8e6e-c3c18af233c7.png)

- 새로운 사용자를 추가하는 **adduser** 명령어를 실행하면 /etc/passwd, /etc/shadow,

  /etc/ group 파일에 새로운 행이 추가됨

- 사용자 추가된 것 확인 (switch user하면 나옴)

![10](https://user-images.githubusercontent.com/63223374/86190764-3c4b5780-bb80-11ea-820f-b13d63ef89c4.PNG)



```
passwd
```

- 사용자의 비밀번호 변경

![그림4](https://user-images.githubusercontent.com/63223374/86190333-12ddfc00-bb7f-11ea-8f9f-c40e9c6c9c28.png)



```
usermod
```

- 사용자 속성 변경

![5](https://user-images.githubusercontent.com/63223374/86190375-2f7a3400-bb7f-11ea-9eb7-813f04c25be1.png)



```
userdel
```

- 사용자 삭제

![6](https://user-images.githubusercontent.com/63223374/86190381-330dbb00-bb7f-11ea-8718-d32c021bd6a4.png)



```
chage
```

- 사용자의 비밀번호를 주기적으로 변경하도록 설정하는 명령어

![7](https://user-images.githubusercontent.com/63223374/86190450-57699780-bb7f-11ea-9001-ea1a0f0cfcaf.png)



```
groups
```

- 사용자가 소속된 그룹을 보여주는 명령어

![8](https://user-images.githubusercontent.com/63223374/86190452-58022e00-bb7f-11ea-80b1-e6bf7e9865c9.png)

- 내 계정을 root로 바꾸고 그룹 출력했을 경우

![9](https://user-images.githubusercontent.com/63223374/86190647-d9f25700-bb7f-11ea-9dcd-0ea5958f39c0.PNG)

- cookuser2를 mygroup1 그룹에 추가시키고 cookuser2로 접속하고 그룹 출력했을 경우

![image-20200701095849621](C:\Users\HP\AppData\Roaming\Typora\typora-user-images\image-20200701095849621.png)



```
groupadd
```

- 새로운 그룹을 생성하는 명령어

![13](https://user-images.githubusercontent.com/63223374/86191310-b03a2f80-bb81-11ea-9f58-fa88d52aae43.png)



```
groupmod
```

- 그룹의 속성을 변경하는 명령어

![14](https://user-images.githubusercontent.com/63223374/86191324-b5977a00-bb81-11ea-8681-93da931f1f6a.png)



```
groupdel
```

- 그룹을 삭제하는 명령어

![15](https://user-images.githubusercontent.com/63223374/86191336-b9c39780-bb81-11ea-82d0-1eefa761a61c.png)



```
gpasswd
```

- 그룹의 비밀번호를 설정하거나 그룹 관리를 수행하는 명령어

![16](https://user-images.githubusercontent.com/63223374/86191342-be884b80-bb81-11ea-9381-cb087dced8e0.png)

<hr>

<h3>사용자와 그룹 관리하기 실습

1. **가상머신 접속**



2. **새로운 사용자 생성**
   2. 1 adduser hanbit1, 비밀번호 1234

![18](https://user-images.githubusercontent.com/63223374/86192427-8e8e7780-bb84-11ea-9829-ba4a12b8b275.PNG)



​			2. 2 hanbit1 사용자가 추가 되었는지 tail /etc/passwd 명령으로 확인

(끝부분 10행을 보여줌으로써 마지막 행에 사용자가 추가된 것을 확인할 수 있음)

![19](https://user-images.githubusercontent.com/63223374/86192531-c5648d80-bb84-11ea-9904-628ff1428fee.PNG)

![20](https://user-images.githubusercontent.com/63223374/86192533-c695ba80-bb84-11ea-9d76-06fc46158994.PNG)

사용자 이름 : hanbit1

비밀번호는 /etc/shadow 파일에 지정되어있음

ID는 전의 것에 1을 더해서 할당됨

그룹 ID도 동일

사용자의 홈 디렉터리는 기본설정인 /home/사용자명

셸은 기본 설정인 /bin/bash



​			2. 3 tail /etc/group 명령을 입력하여 그룹 확인

![21](https://user-images.githubusercontent.com/63223374/86192755-43289900-bb85-11ea-8774-aaac3282a480.PNG)

​			adduser 명령 실행 

별도로 그룹을 지정하지 않으면 자동으로 사용자 이름과 동일한 그룹이 생성됨.

새로운 사용자는 생성된 그룹에 자동으로 포함

새로 생성된 그룹(hanbit1)은 소속된 사용자가 1명



   2. 4 많은 사용자를 관리할 땐 사용자 이름과 그룹 이름이 같아서 관리하기가 불편하다.

      ​	그룹을 먼저 만든 후 사용자를 그 그룹에 넣는 것이 좋음



3. **그룹을 생성하고 소속된 다수 사용자 관리하기**

   3. 1 userdel -r hanbit1 명령으로 hanbit1 사용자 삭제

      ​	groupadd ubuntuGroup 명령으로 ubuntuGroup 그룹을 만든 후

      ​	tail -5 /etc/group 명령으로 확인

![22](https://user-images.githubusercontent.com/63223374/86194489-8e44ab00-bb89-11ea-9999-87262e100a1e.PNG)

![23](https://user-images.githubusercontent.com/63223374/86194502-956bb900-bb89-11ea-8e3b-967c5e5c7f4c.PNG)

​			3. 2 **adduser --gid 그룹ID 사용자** 명령으로 새로운 hanbit1, hanbit2 사용자 생성,

 				   ubuntuGroup 그룹(그룹 ID는 1001)으로 지정

​				    둘 다 암호를 ‘**1234**’로 설정하고 나머지는 모두 Enter 누름

![24](https://user-images.githubusercontent.com/63223374/86194610-e7144380-bb89-11ea-9c19-213ece6c5881.PNG)

![25](https://user-images.githubusercontent.com/63223374/86194612-e8457080-bb89-11ea-9ffd-48f29ce9d6ef.PNG)



​			3. 3  **tail -5 /etc/passwd** 명령으로 passwd 파일 확인

 				   그룹 ID는 모두 1001

​				    앞에서 /etc/group 파일의 1001이 ubuntuGroup임을 확인

![26](https://user-images.githubusercontent.com/63223374/86195113-28f1b980-bb8b-11ea-8a3d-d211eddb2986.PNG)

​			3. 4  비밀번호가 설정된 파일을 **tail -5 /etc/shadow** 명령으로 확인

​    				hanbit1, hanbit2 사용자에 비밀번호가 설정되어 있음 확인 가능 

![26](https://user-images.githubusercontent.com/63223374/86195113-28f1b980-bb8b-11ea-8a3d-d211eddb2986.PNG)



<h3>사용자 변경

- su (Substitute user) - 사용자 변경

```
#user1로 사용자 변경
su – user1 
su user1

#root로 사용자 변경 (root 생략가능)
su root  혹은 su
Su – root 혹은 su –

“ - “를 사용하면, 환경변수를 다 삭제
“ - ” 를 사용하지 않으면, 그 전 login계정의 환경변수를 가져옴
```

![28](https://user-images.githubusercontent.com/63223374/86195776-9d792800-bb8c-11ea-860d-4ea3c83a92d3.PNG)



<h3>root 계정 passwd 변경

- sudo passwd
  - Root의 passwd를 설정 혹은 변경
  - 초기에 설정해주고 su root 가능

![29](https://user-images.githubusercontent.com/63223374/86196296-eda4ba00-bb8d-11ea-9505-224623015fae.PNG)



<h3>새로운 사용자에게 기본 setting을 줄 때</h3>

- /etc/skel 디렉토리
  - 새로 만든 사용자의 home director에 동일하게 적용
  - hanbit1 사용자의 홈 디렉토리인 /home/hanbit1과 /etc/skel 디렉토리 비교
  - skel 디렉토리 안에 생성된 것은 그 그룹 안에 새로운 user를 생성할 때 기본값으로 들어가있다.

![30](https://user-images.githubusercontent.com/63223374/86202354-f6e95300-bb9c-11ea-939e-d8a0250447af.png)



<hr>

<h3>파일 유형

<h3>소유권과 허가권

- root 사용자가 자신의 홈 디렉토리에서 **touch mydata.txt** 명령으로 빈 파일을 만들고 **ls -l** 명령을 실행하면 다음과 같이 나타남

![31](https://user-images.githubusercontent.com/63223374/86238773-156d3f80-bbd9-11ea-9061-c44a728ec0df.PNG)



![1111111111](https://user-images.githubusercontent.com/63223374/86209596-dbd30f00-bbad-11ea-8449-7b44ad44ef09.png)

- <h4>파일 허가권

  • 파일 허가권은 ‘rw-’, ‘r--’, ‘r--’와 같이 3개씩 끊어서 구분

  • r은 read, w는 write, x는 execute의 약자

  • ‘rw-’는 읽거나 쓸 수 있지만 실행할 수는 없다는 의미

  • 읽고 쓰고 실행할 수 있는 파일은 ‘rwx’로 표시

![22222222](https://user-images.githubusercontent.com/63223374/86209598-dd043c00-bbad-11ea-876e-bda03b3740b1.png)

• 첫 번째의 ‘rw-’는 소유자(user)의 파일 접근 권한을, 두 번째의 ‘r--’는 그룹(group)의 파일 접근 권한을, 세 번째의 ‘r--’는 그 외 사용자(other)의 파일 접근 권한을 의미

• 소유자의 허가권을 나타내는 6은 2진수로 110이므로 ‘rw-’로, 그룹의 허가권을 나타내는 4는 2진수로 100이므로 ‘r--’로, 그 외 사용자의 허가권을 나타내는 4도 2진수로 100이므로 ‘r--’로 표현

• 디렉터리(폴더)를 해당 디렉터리로 이동하려면 실행(x) 권한이 반드시 있어야 함

• 따라서 일반적으로 디렉터리에는 소유자, 그룹, 그 외 사용자의 실행(x) 권한이 설정됨



```
chmod
```

![41](https://user-images.githubusercontent.com/63223374/86238887-4f3e4600-bbd9-11ea-9331-36191478dc72.PNG)

![42](https://user-images.githubusercontent.com/63223374/86238940-6715ca00-bbd9-11ea-9d68-11d3a402e998.PNG)

![43](https://user-images.githubusercontent.com/63223374/86239003-7ac13080-bbd9-11ea-841c-451582337076.PNG)

- 파일 허가권을 변경하는 명령어

- root 사용자 또는 해당 파일의 소유자만 실행 가능
- **chmod 777 mydata.txt** 명령을 실행하면 모든 사용자가 mydata.txt 파일은 읽고 쓰고 실행할 수 있음
- 상대모드(symbolic method)로도 사용
- **chmod u+x** 파일명 명령은 소유자(user)에게 실행권한(eXecute)을 허가(+)하라는 의미



- <h4>파일 소유권

특정 사용자와 그룹이 파일에 대한 소유 권한을 가지는 것을 의미

mydata.txt 파일의 경우 소유자가 root사용자이고 소유그룹도 root



```
chown
```

![41](https://user-images.githubusercontent.com/63223374/86238887-4f3e4600-bbd9-11ea-9331-36191478dc72.PNG)

![44](https://user-images.githubusercontent.com/63223374/86239124-afcd8300-bbd9-11ea-964a-932bf9b86233.PNG)

![45](https://user-images.githubusercontent.com/63223374/86239175-c5db4380-bbd9-11ea-9c1a-e6e0c2ff5919.PNG)

- 파일 소유권을 변경하는 명령어
- **chown 새사용자명(.새그룹명) 파일명**
- **chown ubuntu mydata.txt**  - mydata.txt 파일의 소유자를 ubuntu 사용자로 바꾸라는 의미
- **chown ubuntu.ubuntu mydata.txt** - 파일 그룹도 ubuntu 그룹으로 바꾸라는 의미
- **chgrp ubuntu mydata**.txt - 그룹만 ubuntu 그룹으로 바꾸라



<hr>

<h3>링크

- 하드 링크와 심벌릭 링크
  - 파일의 링크는 하드 링크와 심벌릭 링크 또는 소프트 링크로 구분됨
  - **ln 원본파일 링크파일명** - 하드 링크를 생성하는 명령
  - **ln -s 원본파일 링크파일명** - 심벌릭 링크를 생성하는 명령

![46](https://user-images.githubusercontent.com/63223374/86239611-9f69d800-bbda-11ea-8acc-b0fbcaf38c72.png)

1. 파일 생성하고 확인하기
   - /root/linkdir/ 디렉터리 생성 후 그 안에 originalfile 파일 생성
   - vi 에디터나 gedit을 이용하여 메세지 입력 후 저장
   - cat 명령으로 파일 내용 확인

![53](https://user-images.githubusercontent.com/63223374/86242685-0b9b0a80-bbe0-11ea-964d-9ea1ff5e36c9.PNG)



2. 하드 링크와 심벌릭 링크 확인하기

- ln 명령어와 옵션을 조합하여 하드 링크와 심벌릭 링크 파일 생성

![48](https://user-images.githubusercontent.com/63223374/86240174-a3e2c080-bbdb-11ea-94c8-3d2469486276.png)

![54](https://user-images.githubusercontent.com/63223374/86242839-443ae400-bbe0-11ea-9d85-8f68369035d8.PNG)



3. 원본 파일을 다른 곳으로 이동하고 하드 링크 파일과 심벌릭 링크 파일 확인

![51](https://user-images.githubusercontent.com/63223374/86240367-12c01980-bbdc-11ea-8746-e98e6dd1e404.png)

![55](https://user-images.githubusercontent.com/63223374/86242981-83693500-bbe0-11ea-96f0-146615f071dc.PNG)

- 상위폴더로 원본파일을 이동시켰을 때 hardlink는 데이터를 그대로 가져오지만 softlink는 경로를 찾지 못함



4. 원본 파일을 현재 디렉토리에 다시 가져오면 심벌릭 링크가 원상태로 복구됨

![56](https://user-images.githubusercontent.com/63223374/86243416-50737100-bbe1-11ea-985e-56b11e6f2f2f.PNG)

- 다시 원래 폴더로 원본파일을 이동시켰을 때 hardlink, softlink 모두 확인 가능



하드링크 inode를 그대로 가르키고 있기 때문에 원본이 삭제되더라도 그대로 사용 가능

- 원본을 유지할 수 있는 장점
- 파악하지 못한 하드링크가 있는 경우 불필요한 저장소 낭비
- 원본이 이동되어도 사용 가능



소프트링크는 원본 이름만 같으면 다른 파일이어도 동작

<hr>

<h3>프로세스

**프로세스 정의**

- 하드디스크에 저장된 실행코드가 메모리에 로딩되어 활성화된 것

- 예를 들어 웹브라우저 프로그램인 파이어폭스는 하드디스크 어딘가에 저장되어 있는데 이렇게 하드디스크에 저장된 파일을 '프로그램'이라고 부름

- 파이어폭스를 실행하여 화면에 나타난 상태(메모리에 로딩되어 화면에 나타난 상태)를 '프로세스'라 부름

  

**포그라운드 프로세스**

- 포그라운드 프로세스는 파이어폭스와 마찬가지로 실행하면 화면에 나타나서 사용자와 상호 작용을 하는 프로세스



**백그라운드 프로세스**

- 백그라운드 프로세스는 화면에 나타나지 않은 채 뒤에서 실행되는 프로세스



**프로세스 번호**

- 각 프로세스에 할당된 고유 번호
- 메모리에 로딩되어 활성화된 프로세스를 구분하려면 고유 번호가 필요함



**작업 번호**

- 현재 실행 중인 백그라운드 프로세스의 순차 번호



**부모 프로세스와 자식 프로세스**

- 모든 프로세스는 독립적으로 실행되는 것이 아니라 부모 프로세스에 종속되어 실행
- ex) 파이어폭스는 X윈도우 프로세스가 구동된 상태에서 실행되어야함 (X윈도우가 종료되면 파이어폭스도 종료됨)



**ps**

- 현재 프로세스의 상태를 확인하는 명령어
- 많은 옵션과 함께 사용할 수 있음
- 프로세스 번호와 상태를 확인할 때 **ps -ef | grep 프로세스명** 명령을 주로 사용



**kill**

- 프로세스를 강제로 종료하는 명령어
- **-9**옵션과 함께 사용하면 프로세스가 무조건 종료됨
- 응답하지 않고 무한 루프를 도는 프로세스는 **kill -9 프로세스 번호** 명령으로 강제 종료 가능



**pstree**

- 부모 프로세스와 자식 프로세스의 관계를 트리 형태로 보여주는 명령어