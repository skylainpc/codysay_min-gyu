##1. 프로젝트 개요
-터미널, Docker, Git 세 가지를 직접 손으로 세팅해, 실행 결과로 핵심 흐름을 확인한다.

##2. 실행 환경
- OS : 
- Shell : bash
- Docker : 29.9.2
- Git : 2.56.0

##3. 수행 체크리스트
[]:터미널 기본 조작 및 폴더 구성
[]:권한 변경 실습
[]Docker 설치/점검
[]hello-world 실행
[]Dockerfile 빌드/실행
[]포트 매핑 접속(2회)
[]바인드 마운트 반영
[]볼륨 영속성
[]Git 설정 + VSCode GitHub 연동

##4. 검증 방법(어떤 명령으로 무엇을 확인했는지) + 결과 위치 링크

## 수행 로그
(현재 위치)
$ pwd
결과 : /c/Users/전준형

(전체 목록)
$ ls -la
결과 :
total 28849
drwxr-xr-x 1 전준형 197121        0 Nov  7 14:33  ./
drwxr-xr-x 1 전준형 197121        0 Sep 14  2025  ../
-rw-r--r-- 1 전준형 197121      542 Nov  7 16:42  .bash_history
drwxr-xr-x 1 전준형 197121        0 Nov  7 13:38  .config/
drwxr-xr-x 1 전준형 197121        0 Nov  7 14:22  .copilot/
drwxr-xr-x 1 전준형 197121        0 Nov  7 13:38  .docker/
-rw-r--r-- 1 전준형 197121       83 Nov  7 14:11  .gitconfig
-rw-r--r-- 1 전준형 197121       26 Nov  7 14:11  .lesshst
drwxr-xr-x 1 전준형 197121        0 Nov  7 14:50  .ssh/
drwxr-xr-x 1 전준형 197121        0 Nov  7 14:15  .vscode/
drwxr-xr-x 1 전준형 197121        0 Nov  7 14:15  .vscode-shared/
drwxr-xr-x 1 전준형 197121        0 Apr  6  2022 '3D Objects'/
drwxr-xr-x 1 전준형 197121        0 Sep 14  2025  AppData/
lrwxrwxrwx 1 전준형 197121       34 Sep 14  2025 'Application Data' -> /c/Users/전준형/AppData/Roaming/
drwxr-xr-x 1 전준형 197121        0 Sep 15  2025  Contacts/
lrwxrwxrwx 1 전준형 197121       62 Sep 14  2025  Cookies -> /c/Users/전준형/AppData/Local/Microsoft/Windows/INetCookies/
drwxr-xr-x 1 전준형 197121        0 Nov  7 14:40  Desktop/
drwxr-xr-x 1 전준형 197121        0 Aug 11 20:04  Documents/
drwxr-xr-x 1 전준형 197121        0 Nov  7 14:13  Downloads/
drwxr-xr-x 1 전준형 197121        0 Feb  7  2026  Favorites/
-rw-r--r-- 1 전준형 197121      694 Jun 27  2024  KCase.log
drwxr-xr-x 1 전준형 197121        0 Sep 15  2025  Links/
lrwxrwxrwx 1 전준형 197121       32 Sep 14  2025 'Local Settings' -> /c/Users/전준형/AppData/Local/
drwxr-xr-x 1 전준형 197121        0 Sep 15  2025  Music/
lrwxrwxrwx 1 전준형 197121       28 Sep 14  2025 'My Documents' -> /c/Users/전준형/Documents/
-rw-r--r-- 1 전준형 197121 18612224 Nov  7 14:40  NTUSER.DAT
-rw-r--r-- 1 전준형 197121    73728 Oct 16 18:31  NTUSER.DAT{2ad838bc-efea-11ee-a54d-000d3a94eaa1}.TM.blf
-rw-r--r-- 1 전준형 197121     4096 Nov  7 14:40  NTUSER.DAT{2ad838bc-efea-11ee-a54d-000d3a94eaa1}.TM.blf.cnpf
-rw-r--r-- 1 전준형 197121   561152 Oct 16 18:31  NTUSER.DAT{2ad838bc-efea-11ee-a54d-000d3a94eaa1}.TMContainer00000000000000000001.regtrans-ms
-rw-r--r-- 1 전준형 197121     4096 Nov  7 14:40  NTUSER.DAT{2ad838bc-efea-11ee-a54d-000d3a94eaa1}.TMContainer00000000000000000001.regtrans-ms.cnpf
-rw-r--r-- 1 전준형 197121   561152 Oct 16 18:31  NTUSER.DAT{2ad838bc-efea-11ee-a54d-000d3a94eaa1}.TMContainer00000000000000000002.regtrans-ms
-rw-r--r-- 1 전준형 197121     4096 Nov  7 14:40  NTUSER.DAT{2ad838bc-efea-11ee-a54d-000d3a94eaa1}.TMContainer00000000000000000002.regtrans-ms.cnpf
lrwxrwxrwx 1 전준형 197121       70 Sep 14  2025  NetHood -> '/c/Users/전준형/AppData/Roaming/Microsoft/Windows/Network Shortcuts'/
drwxr-xr-x 1 전준형 197121        0 Feb  6  2024  OneDrive/
drwxr-xr-x 1 전준형 197121        0 Sep 15  2025  Pictures/
lrwxrwxrwx 1 전준형 197121       70 Sep 14  2025  PrintHood -> '/c/Users/전준형/AppData/Roaming/Microsoft/Windows/Printer Shortcuts'/
lrwxrwxrwx 1 전준형 197121       59 Sep 14  2025  Recent -> /c/Users/전준형/AppData/Roaming/Microsoft/Windows/Recent/
drwxr-xr-x 1 전준형 197121        0 Sep 15  2025 'Saved Games'/
drwxr-xr-x 1 전준형 197121        0 Sep 15  2025  Searches/
lrwxrwxrwx 1 전준형 197121       59 Sep 14  2025  SendTo -> /c/Users/전준형/AppData/Roaming/Microsoft/Windows/SendTo/
lrwxrwxrwx 1 전준형 197121       62 Sep 14  2025  Templates -> /c/Users/전준형/AppData/Roaming/Microsoft/Windows/Templates/
drwxr-xr-x 1 전준형 197121        0 Sep 15  2025  Videos/
-rw-r--r-- 1 전준형 197121  4763648 Sep 14  2025  ntuser.dat.LOG1
-rw-r--r-- 1 전준형 197121  4674560 Sep 14  2025  ntuser.dat.LOG2
-rw-r--r-- 1 전준형 197121       20 Sep 15  2025  ntuser.ini
lrwxrwxrwx 1 전준형 197121       63 Sep 14  2025 '시작 메뉴' -> '/c/Users/전준형/AppData/Roaming/Microsoft/Windows/Start Menu'/

(폴더 생성/이동/현재 위치 확인)
$ mkdir -p ~/codyssey/practice
$ cd ~/codyssey/practice(폴더 이동)
$ pwd
결과 : /c/Users/전준형/codyssey/practice

(폴더 이름 변경)
$ mv practice renamed_test
$ cd renamed_test
$ pwd
결과 : /c/Users/전준형/codyssey/renamed_test

(폴더 위치 이동)
$ mv renamed_test ~/Desktop
$ cd ~/Desktop/renamed_test
$ pwd
결과 : /c/Users/전준형/Desktop/renamed_test

(폴더 복사)
$ cp -r ~/Desktop/renamed_test ~/Desktop/test_copy
$ cd ~/Desktop/test_copy
$ pwd
결과 : /c/Users/전준형/Desktop/test_copy

(폴더 삭제)
$ rm -r ~/Desktop/test_copy
$ cd ..
$ pwd
결과 : /c/Users/전준형/Desktop

(빈 파일 생성 + 파일 내용 확인)
$ touch empty_file.txt
$ echo "Hello world" > hello.txt
$ cat hello.txt
결과 : Hello world

(Write 권한 제거 전/파일)
$ echo "hi world" > hello.txt
$ cat hello.txt
결과 : hi world
$ ls -l hello.txt
결과 : -rw-r--r-- 1 전준형 197121 9 Nov  7 17:55 hello.txt

(Write 권한 제거 후/파일)
$ chmod 000 hello.txt
$ echo "how world" > hello.txt
결과 : bash: hello.txt: Permission denied
$ ls -l hello.txt
결과 : -r--r--r-- 1 전준형 197121 9 Nov  7 17:55 hello.txt

(모든 권한 제거 후/파일)
$ ls -l hello.txt
$ chmod 000 hello.txt
$ ls -l hello.txt
결과 : -r--r--r-- 1 전준형 197121 12 Nov  7 17:42 hello.txt
추가 설명 : windows의 경우 read 권한까지 빼앗는 경우는 거의 없기 떄문에 chmod 000을 실행하더라고 read 권한이 사라지지 않는다.

