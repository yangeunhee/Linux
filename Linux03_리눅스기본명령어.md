<h1>Linux 명령어</h1>
https://user-images.githubusercontent.com/63223374/86100189-7a4e6a00-baf3-11ea-86ed-7819528eb820.png
<h3>기본 명령어

```
ls : list의 약자. 윈도우의 dir 명령어와 같은 기능 (해당 디렉토리에 있는 파일 목록 나열)
```

![image-20200630142940933](C:\Users\HP\AppData\Roaming\Typora\typora-user-images\image-20200630142940933.png)



```
cd : Change Directory의 약자. 디렉토리를 이동하는 명령어
```

![image-20200630143006602](C:\Users\HP\AppData\Roaming\Typora\typora-user-images\image-20200630143006602.png)



```
pwd : Print Working Directory의 약자. 현재 디렉토리의 전체 경로를 화면에 출력
```

![image-20200630143036506](C:\Users\HP\AppData\Roaming\Typora\typora-user-images\image-20200630143036506.png)



```
touch : 크기가 0인 새 파일을 생성. 이미 파일이 존재한다면 파일의 최종 수정 시간을 변경
```

![image-20200630143109876](C:\Users\HP\AppData\Roaming\Typora\typora-user-images\image-20200630143109876.png)



```
mkdir : Make Directory의 약자. 새로운 디렉토리를 생성. 생성된 디렉토리는 명령을 실행한 사용자의 소유
```

![image-20200630143352390](C:\Users\HP\AppData\Roaming\Typora\typora-user-images\image-20200630143352390.png)



```
rmdir : Remove Directory의 약자. 디렉토리를 삭제. 해당 디렉토리가 비어있고 디렉토리에 대한 삭제 권한이 있어야 함. 파일이 들어 있는 디렉토리를 삭제하려면 'rm -r' 실행
```

![image-20200630143555372](C:\Users\HP\AppData\Roaming\Typora\typora-user-images\image-20200630143555372.png)



```
cp : copy의 약자. 파일이나 디렉토리 복사. 새로 복사된 파일은 복사한 사용자의 소유. 명령을 실행하는 사용자에게 해당 파일의 읽기 권한이 있어야 함
```

![image-20200630145331168](C:\Users\HP\AppData\Roaming\Typora\typora-user-images\image-20200630145331168.png)



```
rm : remove의 약자. 파일이나 디렉토리를 삭제. 사용자에게 해당 파일이나 디렉터리의 삭제 권한이 있어야 함. root 사용자의 경우 모든 권한을 갖고 있기 때문에 이 명령을 사용하는데 제약이 없음
```

![image-20200630145521764](C:\Users\HP\AppData\Roaming\Typora\typora-user-images\image-20200630145521764.png)



```
mv : move의 약자. 파일이나 디렉토리 이름을 변경하거나 다른 디렉토리로 이동할 때 사용
```

![image-20200630145548435](C:\Users\HP\AppData\Roaming\Typora\typora-user-images\image-20200630145548435.png)



```
cat : conCATenate의 약자. 파일의 내용을 화면에 출력. 명령어 뒤에 여러 개의 파일명을 나열하면 파일을 연결하여 내용을 화면에 출력
```

![image-20200630145633962](C:\Users\HP\AppData\Roaming\Typora\typora-user-images\image-20200630145633962.png)



```
head, tail : 텍스트 형식으로 작성된 파일의 앞 10행 또는 마지막 10행만 화면에 출력
```

![image-20200630145658087](C:\Users\HP\AppData\Roaming\Typora\typora-user-images\image-20200630145658087.png)



```
more : 텍스트 형식으로 작성된 파일을 페이지 단위로 화면에 출력. space bar를 누르면 다음 페이지로 이동. B를 누르면 앞 페이지로 이동, Q를 누르면 종료
```

![image-20200630145737279](C:\Users\HP\AppData\Roaming\Typora\typora-user-images\image-20200630145737279.png)



```
less : more 명령어와 용도가 비슷하지만 더 확장된 기능의 명령어. more 명령어에서 사용하는 키도 사용할 수 있음. 방향키와 pageUp, pageDown도 사용 가능
```

![image-20200630145826797](C:\Users\HP\AppData\Roaming\Typora\typora-user-images\image-20200630145826797.png)



```
file : 해당 파일이 어떤 종류의 파일인지 보여줌
```

![image-20200630145841122](C:\Users\HP\AppData\Roaming\Typora\typora-user-images\image-20200630145841122.png)



```
clear : 현재 사용 중인 터미널 화면을 깨끗이 지워줌
```

![image-20200630145908867](C:\Users\HP\AppData\Roaming\Typora\typora-user-images\image-20200630145908867.png)



<h3>파일 압축

```
xz : 확장명 xz로 압축하거나 풀기. 비교적 최신 압축 명령어이며 압축률이 뛰어남
```

![image-20200630145957572](C:\Users\HP\AppData\Roaming\Typora\typora-user-images\image-20200630145957572.png)



```
bzip2 : 확장명 bz2로 압축하거나 풀기
```

![image-20200630150033823](C:\Users\HP\AppData\Roaming\Typora\typora-user-images\image-20200630150033823.png)



```
gzip : 확장명 gz로 압축하거나 풀기
```

![image-20200630150052988](C:\Users\HP\AppData\Roaming\Typora\typora-user-images\image-20200630150052988.png)



```
zip/unzip : 윈도우와 호환되는 확장명 zip로 압축하거나 풀기
```

![image-20200630150113078](C:\Users\HP\AppData\Roaming\Typora\typora-user-images\image-20200630150113078.png)



```
tar : 묶음 파일 만들거나 풀기
```

![image-20200630150136194](C:\Users\HP\AppData\Roaming\Typora\typora-user-images\image-20200630150136194.png)

![image-20200630150139401](C:\Users\HP\AppData\Roaming\Typora\typora-user-images\image-20200630150139401.png)

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

**압축풀기**

> tar xvfJ 파일명.tar.xz
>
> tar xvfj 파일명.tar.bz2

**압축하기**

> tar cvf aaa.tar aaa -> aaa폴더를 aaa.Tar로 압축 묶음
>
> tar cvfz aaa.tar.gz aaa -> aaa폴더를 gz으로 압축하고 tar로 묶음



**tar 자체는 "데이터의 크기를 줄이기 위한 파일 압축"을 수행하지 않는다.**

**여러 파일을 하나의 파일로 묶는 용도로 사용될 뿐이다**



<h3>Linux 디스크 볼륨 Mount하기

1. VMWare에서 볼륨 생성하기

![image-20200630165051015](C:\Users\HP\AppData\Roaming\Typora\typora-user-images\image-20200630165051015.png)



2. 리눅스에서 추가된 볼륨 확인하기

![image-20200630165402499](C:\Users\HP\AppData\Roaming\Typora\typora-user-images\image-20200630165402499.png)

> 20G 용량의 볼륨이 추가 생성되었음을 알 수 있다.



3. 파티션 생성하기

![image-20200630165533194](C:\Users\HP\AppData\Roaming\Typora\typora-user-images\image-20200630165533194.png)



4. 포맷하기

![image-20200630165710420](C:\Users\HP\AppData\Roaming\Typora\typora-user-images\image-20200630165710420.png)



5. 마운트

![image-20200630165741597](C:\Users\HP\AppData\Roaming\Typora\typora-user-images\image-20200630165741597.png)



6. 데이터 저장 

![image-20200630165824739](C:\Users\HP\AppData\Roaming\Typora\typora-user-images\image-20200630165824739.png)

> 생성한 폴더 밑에 테스트 데이터 생성



<h3>파일 위치 검색</h3>

```
find 경로 옵션 조건 action
- 옵션 : -name, -user(소유자), -newer(전,후), -perm(허가권), -size(크기)
- action : -print(기본값), -exec(외부명령실행)
```

![image-20200630153816826](C:\Users\HP\AppData\Roaming\Typora\typora-user-images\image-20200630153816826.png)

> perm : permission의 약자로 

```
which 실행파일명 : path에 설정된 디렉토리와 절대 경로를 포함한 위치 검색
```

![4_which](C:\Users\HP\Desktop\새 폴더\4_which.PNG)

```
whereis 실행파일명 : 실행 파일과 소스, man 페이지 파일까지 검색
```

![4_whereis](C:\Users\HP\Desktop\새 폴더\4_whereis.PNG)

```
location 파일명 :sudo apt-get install mlocate(updatedb 명령을 한 번 실행해야 사용 가능)
```

![4_location](C:\Users\HP\Desktop\새 폴더\4_location.PNG)



<h3>파이프, 필터, 리디렉션</h3>

```
파이프 : 두 프로그램을 연결하는 연결 통로 (여러 페이지를 한 페이지에 나오게 출력해줌)
		|, shift + \를 사용
```

![image-20200630161342857](C:\Users\HP\AppData\Roaming\Typora\typora-user-images\image-20200630161342857.png)



```
필터 : 필요한 것만 걸러주는 명령. grep, tail, wc, sort, awk, sed등이 있다.
	  주로 파이프와 같이 사용
```

![image-20200630161432759](C:\Users\HP\AppData\Roaming\Typora\typora-user-images\image-20200630161432759.png)

뒷부분에 찾고자 하는 글자를 적으면 됨



```
리디렉션 : 표준 입출력의 방향을 바꾸는 것. 표준 입력은 키보드이고 표준 출력은 화면이지만 이를 파일로 처리하고 싶을 때 주로 사용
```

![image-20200630162131771](C:\Users\HP\AppData\Roaming\Typora\typora-user-images\image-20200630162131771.png)
