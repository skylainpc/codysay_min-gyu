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


(Docker 버전 확인)
$ docker --version
결과 : Docker version 29.9.2, build a82e528

(Docker 데몬 동작 여부 확인)
결과 : 
$ docker info
Client:
 Version:    29.9.2
 Context:    desktop-linux
 Debug Mode: false
 Plugins:
  agent: Docker AI Agent Runner (Docker Inc.)
    Version:  v1.152.0
    Path:     C:\Program Files\Docker\cli-plugins\docker-agent.exe
  ai: Docker AI Agent - Ask Gordon (Docker Inc.)
    Version:  v1.33.0
    Path:     C:\Program Files\Docker\cli-plugins\docker-ai.exe
  buildx: Docker Buildx (Docker Inc.)
    Version:  v0.38.1
    Path:     C:\Program Files\Docker\cli-plugins\docker-buildx.exe
  compose: Docker Compose (Docker Inc.)
    Version:  v5.6.1
    Path:     C:\Program Files\Docker\cli-plugins\docker-compose.exe
  debug: Get a shell into any image or container (Docker Inc.)
    Version:  0.49.0
    Path:     C:\Program Files\Docker\cli-plugins\docker-debug.exe
  desktop: Docker Desktop commands (Docker Inc.)
    Version:  4.98.0
    Path:     C:\Program Files\Docker\cli-plugins\docker-desktop.exe
  dhi: CLI for managing Docker Hardened Images (Docker Inc.)
    Version:  v0.0.9
    Path:     C:\Program Files\Docker\cli-plugins\docker-dhi.exe
  extension: Manages Docker extensions (Docker Inc.)
    Version:  v0.2.32
    Path:     C:\Program Files\Docker\cli-plugins\docker-extension.exe
  init: Creates Docker-related starter files for your project (Docker Inc.)
    Version:  v1.4.1
    Path:     C:\Program Files\Docker\cli-plugins\docker-init.exe
  mcp: Docker MCP Plugin (Docker Inc.)
    Version:  v0.44.2
    Path:     C:\Program Files\Docker\cli-plugins\docker-mcp.exe
  model: Docker Model Runner (Docker Inc.)
    Version:  v1.2.9
    Path:     C:\Program Files\Docker\cli-plugins\docker-model.exe
  offload: Docker Offload (Docker Inc.)
    Version:  v0.7.35
    Path:     C:\Program Files\Docker\cli-plugins\docker-offload.exe
  pass: Docker Pass Secrets Manager Plugin (beta) (Docker Inc.)
    Version:  v0.3.2
    Path:     C:\Program Files\Docker\cli-plugins\docker-pass.exe
  sandbox: "docker sandbox" is deprecated, use Docker Sandboxes instead (Docker Inc.)
    Version:  v0.13.0
    Path:     C:\Program Files\Docker\cli-plugins\docker-sandbox.exe
  scout: Docker Scout (Docker Inc.)
    Version:  v1.27.0
    Path:     C:\Program Files\Docker\cli-plugins\docker-scout.exe

Server:
 Containers: 2
  Running: 0
  Paused: 0
  Stopped: 2
 Images: 2
 Server Version: 29.9.2
 Storage Driver: overlayfs
  driver-type: io.containerd.snapshotter.v1
 Logging Driver: local
 Cgroup Driver: cgroupfs
 Cgroup Version: 2
 Plugins:
  Volume: local
  Network: bridge host ipvlan macvlan null overlay
  Log: awslogs fluentd gcplogs gelf journald json-file local splunk syslog
 CDI spec directories:
  /etc/cdi
  /var/run/cdi
 Discovered Devices:
  cdi: docker.com/gpu=webgpu
 Swarm: inactive
 Runtimes: io.containerd.runc.v2 nvidia runc
 Default Runtime: runc
 Init Binary: docker-init
 containerd version: b7a25261e029d68978bbf290df0a62fc819b3c51
 runc version: v1.5.2-0-g29dd3dc2
 init version: de40ad0
 Security Options:
  seccomp
   Profile: builtin
  cgroupns
 Kernel Version: 6.18.54.1-microsoft-standard-WSL2
 Operating System: Docker Desktop
 OSType: linux
 Architecture: x86_64
 CPUs: 8
 Total Memory: 2.765GiB
 Name: docker-desktop
 ID: d72ddf75-d9a8-48a4-9ece-e643d9771b00
 Docker Root Dir: /var/lib/docker
 Debug Mode: false
 HTTP Proxy: http.docker.internal:3128
 HTTPS Proxy: http.docker.internal:3128
 No Proxy: hubproxy.docker.internal
 Labels:
  com.docker.desktop.address=npipe://\\.\pipe\docker_cli
 Experimental: false
 Insecure Registries:
  hubproxy.docker.internal:5555
  127.0.0.0/8
  ::1/128
 Live Restore Enabled: false
 Firewall Backend: iptables


(다운로드/목록 확인)
$ docker images
결과 : 
                                                                          i Info →   U  In Use
IMAGE                ID             DISK USAGE   CONTENT SIZE   EXTRA
hello-world:latest   c567b231f656       25.9kB         9.49kB    U
ubuntu:latest        6a06111c3b0a        163MB         45.9MB


(실행중인 컨테이너 확인)
$ docker ps
결과 : 
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
dodo
(모든 컨테이너 확인)
$ docker ps -a
결과 : 
CONTAINER ID   IMAGE         COMMAND    CREATED        STATUS                   PORTS     NAMES
799bb3395bff   hello-world   "/hello"   10 hours ago   Exited (0) 4 hours ago             nifty_almeida
f2b86ade7a7d   hello-world   "/hello"   10 hours ago   Exited (0) 4 hours ago             quirky_jennings


(컨테이너 로그 확인)
$ docker logs 799bb3395bff
결과 : 
Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/

(컨테이너 리소스 확인)
$ docker stats
결과 : 
CONTAINER ID   NAME      CPU %     MEM USAGE / LIMIT    MEM %     NET I/O        BLOCK I/O     PIDS 65a9eb2fe449   mybox     0.00%     3.84MiB / 2.765GiB   0.14%     1.7kB / 126B   20.6MB / 0B   1

(hello-world 실행 성공)
PS C:\WINDOWS\System32> docker run hello-world
Hello from Docker!
This message shows that your installation appears to be working correctly.

(컨테이너 실행 및 내부 간단 멍령)
PS C:\WINDOWS\System32> docker run -it --name mybox ubuntu
root@8926b9c0dcdb:/# ls
bin  boot  dev  etc  home  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
root@8926b9c0dcdb:/# echo "hello from container"
hello from container
root@8926b9c0dcdb:/# cat /etc/os-release
PRETTY_NAME="Ubuntu 26.04.1 LTS"
NAME="Ubuntu"
VERSION_ID="26.04"
VERSION="26.04.1 LTS (Resolute Raccoon)"
VERSION_CODENAME=resolute
ID=ubuntu
ID_LIKE=debian
HOME_URL="https://www.ubuntu.com/"
SUPPORT_URL="https://help.ubuntu.com/"
BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
UBUNTU_CODENAME=resolute
LOGO=ubuntu-logo
root@8926b9c0dcdb:/#

(attach와 exec의 차이)
-attach : 특정 컨테이너의 기존 bash로 이동하는것.
-exec : 컨테이너 내에서 기존 bash 외에 새로운 bash를 만든다. 이때 bash는 명령어를 수행할 수 있는 기능.
