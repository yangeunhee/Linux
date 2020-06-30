<h1>Linux 명령어</h1>

<h3>기본 명령어

```
ls : list의 약자. 윈도우의 dir 명령어와 같은 기능 (해당 디렉토리에 있는 파일 목록 나열)
```

![그림1](https://user-images.githubusercontent.com/63223374/86102278-458fe200-baf6-11ea-9763-6b69804913c2.png)

<br>

```
cd : Change Directory의 약자. 디렉토리를 이동하는 명령어
```

![그림2](https://user-images.githubusercontent.com/63223374/86102297-4a549600-baf6-11ea-960e-9c4f1e7a7642.png)

<br>

```
pwd : Print Working Directory의 약자. 현재 디렉토리의 전체 경로를 화면에 출력
```

![그림3](https://user-images.githubusercontent.com/63223374/86102549-9d2e4d80-baf6-11ea-88ca-a7224fb98e72.png)

<br>

```
touch : 크기가 0인 새 파일을 생성. 이미 파일이 존재한다면 파일의 최종 수정 시간을 변경
```

![그림4](https://user-images.githubusercontent.com/63223374/86102595-ad462d00-baf6-11ea-907e-d7ea904aba5e.png)

<br>

```
mkdir : Make Directory의 약자. 새로운 디렉토리를 생성. 생성된 디렉토리는 명령을 실행한 사용자의 소유
```

![그림5](https://user-images.githubusercontent.com/63223374/86102601-af0ff080-baf6-11ea-93ba-6c8d96dc71ce.png)

<br>

```
rmdir : Remove Directory의 약자. 디렉토리를 삭제. 해당 디렉토리가 비어있고 디렉토리에 대한 삭제 권한이 있어야 함. 파일이 들어 있는 디렉토리를 삭제하려면 'rm -r' 실행
```

![그림6](https://user-images.githubusercontent.com/63223374/86102607-b0d9b400-baf6-11ea-9eb4-6066b8942da2.png)

<br>

```
cp : copy의 약자. 파일이나 디렉토리 복사. 새로 복사된 파일은 복사한 사용자의 소유. 명령을 실행하는 사용자에게 해당 파일의 읽기 권한이 있어야 함
```

![그림7](https://user-images.githubusercontent.com/63223374/86102669-c6e77480-baf6-11ea-9ad2-29a730703804.png)

<br>

```
rm : remove의 약자. 파일이나 디렉토리를 삭제. 사용자에게 해당 파일이나 디렉터리의 삭제 권한이 있어야 함. root 사용자의 경우 모든 권한을 갖고 있기 때문에 이 명령을 사용하는데 제약이 없음
```

![그림8](https://user-images.githubusercontent.com/63223374/86102676-c818a180-baf6-11ea-9e99-34788d495e8d.png)

<br>

```
mv : move의 약자. 파일이나 디렉토리 이름을 변경하거나 다른 디렉토리로 이동할 때 사용
```

![그림9](https://user-images.githubusercontent.com/63223374/86102679-c8b13800-baf6-11ea-91dd-fdf6245dbfc1.png)

<br>

```
cat : conCATenate의 약자. 파일의 내용을 화면에 출력. 명령어 뒤에 여러 개의 파일명을 나열하면 파일을 연결하여 내용을 화면에 출력
```

![그림10](https://user-images.githubusercontent.com/63223374/86102737-df578f00-baf6-11ea-8f35-e0f74ee62986.png)

<br>

```
head, tail : 텍스트 형식으로 작성된 파일의 앞 10행 또는 마지막 10행만 화면에 출력
```

![그림11](https://user-images.githubusercontent.com/63223374/86102740-e088bc00-baf6-11ea-8dee-fa52521fd3b1.png)

<br>

```
more : 텍스트 형식으로 작성된 파일을 페이지 단위로 화면에 출력. space bar를 누르면 다음 페이지로 이동. B를 누르면 앞 페이지로 이동, Q를 누르면 종료
```

![그림12](https://user-images.githubusercontent.com/63223374/86102743-e1b9e900-baf6-11ea-8145-2cc308e154b2.png)

<br>

```
less : more 명령어와 용도가 비슷하지만 더 확장된 기능의 명령어. more 명령어에서 사용하는 키도 사용할 수 있음. 방향키와 pageUp, pageDown도 사용 가능
```

![그림13](https://user-images.githubusercontent.com/63223374/86102797-f1393200-baf6-11ea-883f-45f8a41a5f0e.png)

<br>

```
file : 해당 파일이 어떤 종류의 파일인지 보여줌
```

![그림14](https://user-images.githubusercontent.com/63223374/86102803-f4342280-baf6-11ea-8132-ed9ccfdbd7da.png)

<br>

```
clear : 현재 사용 중인 터미널 화면을 깨끗이 지워줌
```

![그림15](https://user-images.githubusercontent.com/63223374/86102807-f4ccb900-baf6-11ea-9f8c-18e5233969cf.png)

<br>

<h3>파일 압축

```
xz : 확장명 xz로 압축하거나 풀기. 비교적 최신 압축 명령어이며 압축률이 뛰어남
```

![그림16](https://user-images.githubusercontent.com/63223374/86102884-0c0ba680-baf7-11ea-834b-a26a3a63a09f.png)

<br>

```
bzip2 : 확장명 bz2로 압축하거나 풀기
```

![그림17](https://user-images.githubusercontent.com/63223374/86102889-0ca43d00-baf7-11ea-8b9d-7c18e7580e2b.png)

<br>

```
gzip : 확장명 gz로 압축하거나 풀기
```

![그림18](https://user-images.githubusercontent.com/63223374/86102893-0dd56a00-baf7-11ea-8d31-38346beaa4e1.png)

<br>

```
zip/unzip : 윈도우와 호환되는 확장명 zip로 압축하거나 풀기
```

![그림19](https://user-images.githubusercontent.com/63223374/86102894-0e6e0080-baf7-11ea-8053-3cb8e9819801.png)

<br>

```
tar : 묶음 파일 만들거나 풀기
```

![그림20](https://user-images.githubusercontent.com/63223374/86103036-39f0eb00-baf7-11ea-82bd-41019e270657.png)

![그림21](https://user-images.githubusercontent.com/63223374/86102967-25acee00-baf7-11ea-9778-b34bfc6de71a.png)

> c : 새로운 묶음 파일 생성
>
> x : 묶음 파일 풀기
>
> v : visual을 의미. 파일을 묶거나 푸는 과정을 보여줌 (생략 가능)
>
> f  : 묶음 파일명을 지정
>
> t : 묶음 파일을 풀기 전에 묶인 경로를 보여줌
>
> C : 지정된 디렉토리에 묶음 파일 풀기 or 묶음 파일이 있는 디렉토리에 풀기
>
> J : tar + xz
>
> z : tar + gzip
>
> j : tar + bzip2

<br>

**압축풀기**

> tar xvfJ 파일명.tar.xz
>
> tar xvfj 파일명.tar.bz2

<br>

**압축하기**

> tar cvf aaa.tar aaa -> aaa폴더를 aaa.Tar로 압축 묶음
>
> tar cvfz aaa.tar.gz aaa -> aaa폴더를 gz으로 압축하고 tar로 묶음

<br>

**tar 자체는 "데이터의 크기를 줄이기 위한 파일 압축"을 수행하지 않는다.**

**여러 파일을 하나의 파일로 묶는 용도로 사용될 뿐이다**

<br>

<h3>파일 위치 검색</h3>

```
find 경로 옵션 조건 action
- 옵션 : -name, -user(소유자), -newer(전,후), -perm(허가권), -size(크기)
- action : -print(기본값), -exec(외부명령실행)
```

![그림22](https://user-images.githubusercontent.com/63223374/86102973-26458480-baf7-11ea-83ee-5265f16d80dc.png)

> perm : permission의 약자

<br>

```
which 실행파일명 : path에 설정된 디렉토리와 절대 경로를 포함한 위치 검색
```

<br>

```
whereis 실행파일명 : 실행 파일과 소스, man 페이지 파일까지 검색
```

<br>

```
location 파일명 :sudo apt-get install mlocate(updatedb 명령을 한 번 실행해야 사용 가능)
```

<br>

<h3>파이프, 필터, 리디렉션</h3>

```
파이프 : 두 프로그램을 연결하는 연결 통로 (여러 페이지를 한 페이지에 나오게 출력해줌)
		|, shift + \를 사용
```

![그림23](https://user-images.githubusercontent.com/63223374/86102976-2776b180-baf7-11ea-9b6b-c0006ef735d8.png)

<br>

```
필터 : 필요한 것만 걸러주는 명령. grep, tail, wc, sort, awk, sed등이 있다.
	  주로 파이프와 같이 사용
```

![그림24](https://user-images.githubusercontent.com/63223374/86103136-57be5000-baf7-11ea-9c0d-d7f93800831d.png)

뒷부분에 찾고자 하는 글자를 적으면 됨

<br>

```
리디렉션 : 표준 입출력의 방향을 바꾸는 것. 표준 입력은 키보드이고 표준 출력은 화면이지만 이를 파일로 처리하고 싶을 때 주로 사용
```

![그림25](https://user-images.githubusercontent.com/63223374/86103141-58ef7d00-baf7-11ea-824d-8242d0e2bcb7.png)

<hr>

