##1. 프로젝트 개요
-터미널, Docker, Git 세 가지를 직접 손으로 세팅해, 실행 결과로 핵심 흐름을 확인한다.

##2. 실행 환경
- OS : 
- Shell : bash
- Docker : 29.9.2
- Git : 2.56.0

##3. 수행 체크리스트
[O]:터미널 기본 조작 및 폴더 구성
[O]:권한 변경 실습
[O]Docker 설치/점검
[O]hello-world 실행
[O]Dockerfile 빌드/실행
[O]포트 매핑 접속(2회)
[O]볼륨 영속성
[O]Git 설정 + VSCode GitHub 연동


##4. 수행 로그
1.터미널 조작 로그 기록(Gitbash)
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

(hello-world 실행)(Powershell)
PS C:\WINDOWS\System32> docker run hello-world

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





2.권한 변경(Gitbash)
root@5d6230ba8310:/temp# touch file.txt
root@5d6230ba8310:/temp# mkdir mydir
root@5d6230ba8310:/temp# ls -l
total 4
-rw-r--r-- 1 root root    0 Nov  8 01:34 file.txt
drwxr-xr-x 2 root root 4096 Nov  8 01:34 mydir
root@5d6230ba8310:/temp# chmod 600 file.txt
root@5d6230ba8310:/temp# chmod 700 mydir
root@5d6230ba8310:/temp# ls -l
total 4
-rw------- 1 root root    0 Nov  8 01:34 file.txt
drwx------ 2 root root 4096 Nov  8 01:34 mydir

*rwx는 각각 read(읽기), write(쓰기), execute(실행) 권한을 의미하며, chmod 755의 755는 앞부터 각각 소유주, 그룹, 그 외(others)에서 rwx, rx, rx 권한을 준다는 의미이다.


*exit, exec, stop을 각각 진행했을 때 컨테이너 상태 차이
PS C:\Users\전준형> docker ps -a
CONTAINER ID   IMAGE     COMMAND       CREATED         STATUS                     PORTS     NAMES
5d6230ba8310   ubuntu    "/bin/bash"   8 minutes ago   Exited (0) 5 minutes ago             mybox
PS C:\Users\전준형> docker start mybox
mybox
PS C:\Users\전준형> docker ps -a
CONTAINER ID   IMAGE     COMMAND       CREATED         STATUS          PORTS     NAMES
5d6230ba8310   ubuntu    "/bin/bash"   9 minutes ago   Up 13 seconds             mybox
PS C:\Users\전준형> docker exec -it mybox bash
root@5d6230ba8310:/# ls
bin  boot  dev  etc  home  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  temp  tmp  usr  var
root@5d6230ba8310:/# exit
exit

What's next:
    Try Docker Debug for seamless, persistent debugging tools in any container or image → docker debug mybox
    Learn more at https://docs.docker.com/go/debug-cli/
PS C:\Users\전준형> docker ps
CONTAINER ID   IMAGE     COMMAND       CREATED         STATUS          PORTS     NAMES
5d6230ba8310   ubuntu    "/bin/bash"   9 minutes ago   Up 44 seconds             mybox
PS C:\Users\전준형> docker stop mybox
mybox
PS C:\Users\전준형> docker ps -a
CONTAINER ID   IMAGE     COMMAND       CREATED          STATUS                       PORTS     NAMES
5d6230ba8310   ubuntu    "/bin/bash"   12 minutes ago   Exited (137) 5 seconds ago             mybox





3.Docker 버전 확인 및 데몬 동작 여부 확인
$ docker --version
Docker version 29.9.2, build a82e528

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





4-1.Docker 기본 운영 명령 수행1(Powershell)
PS C:\Users\전준형> docker images
                                                                                                    i Info →   U  In Use
IMAGE                ID             DISK USAGE   CONTENT SIZE   EXTRA
hello-world:latest   c567b231f656       25.9kB         9.49kB
ubuntu:latest        6a06111c3b0a        163MB         45.9MB    U
PS C:\Users\전준형> docker logs mybox
root@f850c1248942:/# ls
bin  boot  dev  etc  home  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
root@f850c1248942:/# echo "hello from container"
hello from container
root@f850c1248942:/# cat /etc/os-release
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
root@f850c1248942:/# mkdir temp
root@f850c1248942:/# cd temp
root@f850c1248942:/temp# touch file.txt
root@f850c1248942:/temp# mkdir mydir
root@f850c1248942:/temp# exit
exit
PS C:\Users\전준형> docker stats --no-stream
CONTAINER ID   NAME      CPU %     MEM USAGE / LIMIT     MEM %     NET I/O         BLOCK I/O    PIDS
f850c1248942   mybox     0.00%     2.625MiB / 2.765GiB   0.09%     1.17kB / 126B   639kB / 0B   1
PS C:\Users\전준형> docker stop mybox
mybox
PS C:\Users\전준형> docker rm mybox
mybox
PS C:\Users\전준형> docker ps -a
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
PS C:\Users\전준형>





4-2.Docker 기본 명령  수행2(Gitbash)
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





5.컨테이너 실행 실습(PowerShell)
PS C:\Users\전준형> docker run -it --name mybox ubuntu bash
root@dfcf48030e7a:/# ls
bin  boot  dev  etc  home  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
root@dfcf48030e7a:/# echo
root@dfcf48030e7a:/# echo hello-world
hello-world





6.웹 서버 베이스 이미지를 활용한 커스텀 이미지 생성 + 포드 매핑 및 접속 증거
<img width="942" height="341" alt="image" src="https://github.com/user-attachments/assets/c9ba727e-7475-4e9c-81bb-c835ecfecedc" />
<img width="676" height="170" alt="image" src="https://github.com/user-attachments/assets/abf66693-e6cf-44c7-b13b-2411e8030007" />
터미널 :
PS C:\Users\전준형\Desktop\Dockerfile> docker build -t my-web .
[+] Building 3.1s (7/7) FINISHED                                                                 docker:desktop-linux
 => [internal] load build definition from Dockerfile                                                             0.1s
 => => transferring dockerfile: 110B                                                                             0.0s
 => [internal] load metadata for docker.io/library/nginx:latest                                                  1.6s
 => [internal] load .dockerignore                                                                                0.0s
 => => transferring context: 2B                                                                                  0.0s
 => CACHED [1/2] FROM docker.io/library/nginx:latest@sha256:165ddde8751e75a1c907d24ef10d9f6deb08b57e0fe56caf675  0.1s
 => => resolve docker.io/library/nginx:latest@sha256:165ddde8751e75a1c907d24ef10d9f6deb08b57e0fe56caf67512486af  0.1s
 => [internal] load build context                                                                                0.0s
 => => transferring context: 311B                                                                                0.0s
 => [2/2] COPY index.html /usr/share/nginx/html/index.html                                                       0.1s
 => exporting to image                                                                                           0.8s
 => => exporting layers                                                                                          0.2s
 => => exporting manifest sha256:e9d0146a674874aea0c7b96102f9c9a0a4f20f125e726ef31383b3c7b2b11504                0.0s
 => => exporting config sha256:692d1647afa16e81462a95168697de7e922853551389aa952bb6f7dac5b2010c                  0.0s
 => => exporting attestation manifest sha256:abae44be4342b26c391412efc701dd337dc8ac4d72aa91e1295d92edb6ba0a3c    0.1s
 => => exporting manifest list sha256:9abf93443be885ab47611bafb204a6788fac52a8a02b9da4a7bad6977ae26ddb           0.0s
 => => naming to docker.io/library/my-web:latest                                                                 0.0s
 => => unpacking to docker.io/library/my-web:latest                                                              0.2s

View build details: docker-desktop://dashboard/build/desktop-linux/desktop-linux/986h7ym5fjrhgtv7px8hq848v
PS C:\Users\전준형\Desktop\Dockerfile> docker run -d -p 8080:80 --name my-web my-web
42d1de6d44caf2e4937a01f5f8b4745fc89746a6a483723e98fababc4357e43c
PS C:\Users\전준형\Desktop\Dockerfile> docker ps
CONTAINER ID   IMAGE     COMMAND                   CREATED          STATUS          PORTS                                     NAMES
42d1de6d44ca   my-web    "/docker-entrypoint.…"   5 seconds ago    Up 4 seconds    0.0.0.0:8080->80/tcp, [::]:8080->80/tcp   my-web
dfcf48030e7a   ubuntu    "bash"                    44 minutes ago   Up 44 minutes                                             mybox
PS C:\Users\전준형\Desktop\Dockerfile> 

결과(8080) : <img width="743" height="265" alt="image" src="https://github.com/user-attachments/assets/650a93e8-8e13-480a-9615-008e499a7cb5" />
결과(8081) : <img width="736" height="292" alt="image" src="https://github.com/user-attachments/assets/652e9547-40bc-467c-8e60-9043657b2bcd" />





7.볼륨 영속성 검증
PS C:\Users\전준형\Desktop\Dockerfile> docker run -d -p 8082:80 --name my-web-live -v ${PWD}:/usr/share/nginx/html nginx
2a1b21c9bad17c3744ffb78b3c18b9d5f1c66238576cb6b536019c7e58b2e619
PS C:\Users\전준형\Desktop\Dockerfile> docker volume create mydata
mydata
PS C:\Users\전준형\Desktop\Dockerfile> docker run -it --name vol-test -v mydata:/data ubuntu
root@aaf8f1f2536b:/# echo "hello volume" > /data/memo.txt  
root@aaf8f1f2536b:/# exit
exit
PS C:\Users\전준형\Desktop\Dockerfile> docker rm vol-test
vol-test
PS C:\Users\전준형\Desktop\Dockerfile> docker run -it --rm -v mydata:/data ubuntu cat /data/memo.txt
hello volume
PS C:\Users\전준형\Desktop\Dockerfile> docker volume ls
DRIVER    VOLUME NAME
local     mydata
PS C:\Users\전준형\Desktop\Dockerfile> 





8.Git 설정 및 Github 연동
<img width="400" height="69" alt="image" src="https://github.com/user-attachments/assets/3eee8c6e-6863-4685-88c5-ae82c9da1174" />





9.트러블슈팅(VS Code terminal)
(1)상황 : my-web이라는 컨테이너를 만드려고 하는데, 에러 코드에 my-web이라는 이름의 컨테이너가 이미 있다고 출력
(2)확인 및 조치 : my-web 컨테이너를 rm을 이용해 삭제 한 후, 다시 형성시킨 후 "docker run -d -p 8080:80 --name my-web my-web"코드를 입력하니 정상 동작

PS C:\Users\전준형\Desktop\Dockerfile> docker run -d -p 8080:80 --name my-web my-web
docker: Error response from daemon: Conflict. The container name "/my-web" is already in use by container "ef33068f4004c7583555b819b91f284ffbd829730a4fbc1d2c039734462a6f32". You have to remove (or rename) that container to be able to reuse that name.

Run 'docker run --help' for more information

What's next:
    Debug this container error with Gordon → docker ai "help me fix this container error"


PS C:\Users\전준형\Desktop\Dockerfile> Get-ChildItem C:\Users\전준형\Desktop\Dockerfile


    디렉터리: C:\Users\전준형\Desktop\Dockerfile


Mode                 LastWriteTime         Length Name                                                               
----                 -------------         ------ ----                                                               
-a----      2026-11-08  오전 11:27             73 Dockerfile                                                         
-a----      2026-11-08  오전 11:11              0 index.html                                                         


PS C:\Users\전준형\Desktop\Dockerfile> Get-ChildItem index.html
               

    디렉터리: C:\Users\전준형\Desktop\Dockerfile


Mode                 LastWriteTime         Length Name                                                               
----                 -------------         ------ ----                                                               
-a----      2026-11-08  오전 11:49            272 index.html                                                         


PS C:\Users\전준형\Desktop\Dockerfile> docker stop my-web
my-web
PS C:\Users\전준형\Desktop\Dockerfile> docker rm my-web
my-web
PS C:\Users\전준형\Desktop\Dockerfile> docker build -t my-web
ERROR: docker: 'docker buildx build' requires 1 argument

Usage:  docker buildx build [OPTIONS] PATH | URL | -

Run 'docker buildx build --help' for more information

What's next:
    Debug this build failure with Gordon → docker ai "help me fix this build failure"
PS C:\Users\전준형\Desktop\Dockerfile> docker build -t my-web .
[+] Building 3.1s (7/7) FINISHED                                                                 docker:desktop-linux
 => [internal] load build definition from Dockerfile                                                             0.1s
 => => transferring dockerfile: 110B                                                                             0.0s
 => [internal] load metadata for docker.io/library/nginx:latest                                                  1.6s
 => [internal] load .dockerignore                                                                                0.0s
 => => transferring context: 2B                                                                                  0.0s
 => CACHED [1/2] FROM docker.io/library/nginx:latest@sha256:165ddde8751e75a1c907d24ef10d9f6deb08b57e0fe56caf675  0.1s
 => => resolve docker.io/library/nginx:latest@sha256:165ddde8751e75a1c907d24ef10d9f6deb08b57e0fe56caf67512486af  0.1s
 => [internal] load build context                                                                                0.0s
 => => transferring context: 311B                                                                                0.0s
 => [2/2] COPY index.html /usr/share/nginx/html/index.html                                                       0.1s
 => exporting to image                                                                                           0.8s
 => => exporting layers                                                                                          0.2s
 => => exporting manifest sha256:e9d0146a674874aea0c7b96102f9c9a0a4f20f125e726ef31383b3c7b2b11504                0.0s
 => => exporting config sha256:692d1647afa16e81462a95168697de7e922853551389aa952bb6f7dac5b2010c                  0.0s
 => => exporting attestation manifest sha256:abae44be4342b26c391412efc701dd337dc8ac4d72aa91e1295d92edb6ba0a3c    0.1s
 => => exporting manifest list sha256:9abf93443be885ab47611bafb204a6788fac52a8a02b9da4a7bad6977ae26ddb           0.0s
 => => naming to docker.io/library/my-web:latest                                                                 0.0s
 => => unpacking to docker.io/library/my-web:latest                                                              0.2s

View build details: docker-desktop://dashboard/build/desktop-linux/desktop-linux/986h7ym5fjrhgtv7px8hq848v
PS C:\Users\전준형\Desktop\Dockerfile> docker run -d -p 8080:80 --name my-web my-web
42d1de6d44caf2e4937a01f5f8b4745fc89746a6a483723e98fababc4357e43c





10.(포트 사용 프로세스 확인 및 포트 해제)
PS C:\Users\전준형> netstat -ano | findstr :8080
  TCP    0.0.0.0:8080           0.0.0.0:0              LISTENING       4732
  TCP    127.0.0.1:8080         0.0.0.0:0              LISTENING       13304
  TCP    [::]:8080              [::]:0                 LISTENING       4732
  TCP    [::1]:8080             [::]:0                 LISTENING       13304
PS C:\Users\전준형> tasklist /fi "pid eq 13304"

이미지 이름                    PID 세션 이름              세션#  메모리 사용
========================= ======== ================ =========== ============
wslrelay.exe                 13304 Console                    2     10,024 K
PS C:\Users\전준형> taskkill /f /pid 13304
성공: 프로세스(PID 13304)가 종료되었습니다.
PS C:\Users\전준형> netstat -ano | findstr :8080
  TCP    0.0.0.0:8080           0.0.0.0:0              LISTENING       4732
  TCP    [::]:8080              [::]:0                 LISTENING       4732





11.PS C:\Users\전준형\Desktop\Dockerfile> ls      #폴더 내 파일 확인(기존 파일 2개)


    디렉터리: C:\Users\전준형\Desktop\Dockerfile


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----      2026-11-08  오전 11:27             73 Dockerfile
-a----      2026-11-08  오전 11:49            272 index.html


PS C:\Users\전준형\Desktop\Dockerfile> tar -cvzf backup_project.tar.gz .        #폴더 내 파일 압축
a .
a ./backup_project.tar.gz
a ./Dockerfile
a ./index.html
PS C:\Users\전준형\Desktop\Dockerfile> ls     #폴더 내 파일 확인(기존 파일 2개 + 압축 파일 1개)


    디렉터리: C:\Users\전준형\Desktop\Dockerfile


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----      2026-11-08   오후 2:11            566 backup_project.tar.gz
-a----      2026-11-08  오전 11:27             73 Dockerfile
-a----      2026-11-08  오전 11:49            272 index.html


PS C:\Users\전준형\Desktop\Dockerfile> rm index.html     #index.html 파일 삭제
PS C:\Users\전준형\Desktop\Dockerfile> ls                #폴더 내 파일 확인(기존 파일 1개 + 압축 파일 1개)


    디렉터리: C:\Users\전준형\Desktop\Dockerfile


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----      2026-11-08   오후 2:11            566 backup_project.tar.gz
-a----      2026-11-08  오전 11:27             73 Dockerfile


PS C:\Users\전준형\Desktop\Dockerfile> tar -xvzf backup_project.tar.gz        #파일 복구
x ./
x ./backup_project.tar.gz: Can't unlink already-existing object: Permission denied
x ./Dockerfile
x ./index.html
tar.exe: Error exit delayed from previous errors
PS C:\Users\전준형\Desktop\Dockerfile> ls       ##폴더 내 파일 확인(기존 파일 1개 + 압축 파일 1개 + 복구 파일 1개)


    디렉터리: C:\Users\전준형\Desktop\Dockerfile


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----      2026-11-08   오후 2:11            566 backup_project.tar.gz
-a----      2026-11-08  오전 11:27             73 Dockerfile
-a----      2026-11-08  오전 11:49            272 index.html


PS C:\Users\전준형\Desktop\Dockerfile>
  





12.여러가지 설명
*절대경로, 상대경로 차이
-절대경로 : 현재 위치에 상관없이 특정 위치에 폴더, 디렉토리 등을 만들어라는 의미로 위치의 혼동은 없지만, 사용자 이름등이 바뀌면은 동작하지 않고 상대경로에 비해 상대적으로 느리다.
-상대경로 : 현재 위치를 기준으로 한 위치로, 절대경로에 비해 속도가 매우 빠르다.

*호스트 경로 VS 컨테이너 경로 선택 근거
-호스트 경로의 경우 사용자마다 다르기 때문에 상대경로를 이용해 실시간으로 소스 코드를 수정하는것이 좋다.
-컨테이너 경로의 경우 사용자가 달라도 동일한 경로를 가지기 때문에 절대경로를 이용해도 재현성이 유지된다.

*네트워크 네임스페이스, 포트포워딩
-네트워크 네임스페이스 : 리눅스의 네임스페이스 기술을 사용해 호스트와 분리된 독립된 공간을 가진다. 그렇기 때문에 여러 컨테이너가 동일한 포트를 사용하더라도 서로 충돌하지 않지만, 격리되어있어 외부(호스트)에서는 컨테이너 내부로 직접 접근할 수 없다.
-포트포워딩 : 격리된 컨테이너 내부로 트래픽을 보내기 위해 포트포워딩을 사용한다. 측 호스트의 특정 포트와 컨테이너의 특정 포트를 연결하는 '통로'를 만드는 과정이다.
-호스트-컨테이너 연결 방법
->외부 사용자가 호스트의 IP와 지정되니 포트로 접속 시도 시, 호스트 OS의 커널은 미리 설정된 포트포워딩 규칙을 확인한다. 이후 호스트는 받은 패킷의 목적지 주소를 컨테이너의 가상 IP와 내부 포트 번호로 변환해 전달한 후 컨테이너가 처리한 결과는 다시 역순으로 호스트를 거쳐 사용자에게 전달된다.

*이미지, 컨테이너의 차이
-택배 상자로 설명하면 이미지는 간단하게 포장 설명서로 실행되지 않는 정적인 파일 묶음이고, 컨테이너는 포장된 상자로 이미지가 메모리에 올라가 프로세스로 실행 중인 상태이다. 즉 이미지는 APP 실행에 필요한 모든 환경이 저장된 '읽기 전용 설계도'이며, 컨테이너는 이 이미지를 복제해 그 위에 '쓰기 가능한 레이어'를 얹어 실제 동작시킨다.

*git remote -v 및 git push 실행
PS C:\Users\전준형> git remote -v
origin  [https://github.com/skylainpc?tab=repositories] (fetch)
origin  [https://github.com/skylainpc?tab=repositories] (push)

PS C:\Users\전준형> git push
fatal: The current branch main has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin main

To have this happen automatically for branches without a tracking
upstream, see 'push.autoSetupRemote' in 'git help config'.

*프로젝트 디렉토리 구조 및 설명
project-root/
├── data/           # 프로젝트에 사용되는 데이터셋 (원본 및 전처리 데이터)
├── src/            # 실제 실행 가능한 소스 코드 (.py, .ipynb 등)
├── docs/           # 프로젝트 관련 문서 및 매뉴얼
├── results/        # 코드 실행 결과물 (그래프, 모델 저장 파일, 로그)
├── .gitignore      # Git 관리 제외 대상 설정 (대용량 데이터, 보안 파일 등)
└── README.md       # 프로젝트 개요 및 구조 설명 문서 (현재 파일)







