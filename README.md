# SSongNote

### - xStudio in Rocky Linux 8.X
```
dnf config-manager --set-enabled powertools
dnf install alsa-lib-devel pulseaudio-libs-devel
dnf install freeglut-devel libjpeg-devel libuuid-devel
dnf --enablerepo=devel install pybind11-devel
dnf --enablerepo=devel install doxygen
dnf --enablerepo=powertools install qt5-devel
dnf --enablerepo=devel install qt5-qtquickcontrols
dnf --enablerepo=powertools install python3-sphinx

dnf install openssl
dnf install openssl-devel

dnf --enablerepo=devel install opus-devel

dnf install libvpx
dnf --enablerepo=powertools install libvpx-devel
```

</br>
</br>

### - pyenv


```
1. pyenv 사용법 정리
* global하게 여러 python 버전들을 선택 사용가능
* global하게 설정된것과 별개로 local 특정 폴더에서만 다른 버전 사용가능
	- 설치는 알아서
	- python 가능한 버전들 확인 : pyenv iinstall --list 
	- 원하는 버전 설치 및 삭제 : 
		- pyenv install 3.9.9 
		- pyenv uninstall 3.9.9
	- 설치된 항목들 확인 : pyenv versions
	- 현재 파이썬 interpreter 확인 : pyenv version
	- 버전들 사이에서 왔다갔다하기 : pyenv global 3.11.3
	- 해당 폴더에서 해당폴더만 사용하기 : pyenv local 3.11.3

* pip install moduled 이 섞이고 싶지 않다할때, 
	- pyenv virtualenv {사용할버전} {env이름} 
	- ex) pyenv virtualenv 3.9.9 song
	- pyenv virtualenv-delete {env이름}

	- pyenv activate {env이름}
	- pyenv deactivate
	
	

2. pyenv로 프로젝트 구성
3. sphinx 로 docstring할 예시 작업 함수 및 클래스 작성
4. 생성된 html을 깃허브에서 호스팅
```

</br>
</br>


### - linux 설정들
```
- /etc/sudoers    # sudo 권한 설정 공간
...
##
## Allow root to run any commands anywhere 
root	ALL=(ALL) 	ALL
taiyeong.song ALL=(ALL) ALL
## Allows members of the 'sys' group to run networking, software, 
## service management apps and more.
...


- /etc/hosts      # IP 맵핑 설정 공간
127.0.0.1   localhost localhost.localdomain localhost4 localhost4.localdomain4
::1         localhost localhost.localdomain localhost6 localhost6.localdomain6

10.4.2.15   gsteplic-02
10.4.20.249 maru

```

</br>
</br>

### Sphinx

[sphinx 셋팅](https://hooni-playground.com/1101/)

</br>
</br>


## docker VS docker compose
1. Docker

	>  Single Container를 관리하는것. 커맨드 라인에서 명령어를 실행할 수 있다.

 

2. Docker-compose

	> yaml file 기반으로 multi container 관리할 수 있는 client이고 yaml파일에 명령어를 적어서 컨테이너를 정의하고 관리한다.


## docker command
[More detail](https://kibua20.tistory.com/135)

```
$ docker ps : show running container
$ docker ps -a : show all running container including stopped one
$ docker run ... : create and run new container from an image
$ docker start [container name]
$ docker stop [container name]
$ docker kill [container name]
$ docker image list : show all installed images

$ docker container start [container name]
$ docker container stop [container name]
$ docker container kill [container name]
$ docker container rm [container name]
$ docker container ls -a
```

## docker compose command
[More detail](https://kimjingo.tistory.com/108)

```
$ docker compose up : create and start container
```

## OpenCue - plugin
[git](https://github.com/AcademySoftwareFoundation/OpenCue/tree/master/cuesubmit/plugins)

## Kitsu Setup - single container
> docker 로 관리 : single 이라서
- [Kitsu Docker](https://github.com/cgwire/kitsu-docker)
- [Kitsu Documentation](https://kitsu.cg-wire.com/#getting-started)
- [Kitsu 1 minute tutorial](https://www.youtube.com/playlist?list=PLp_1gB5ZBHXqnQgZ4TCrAt7smxesaDo29)
```
# install image
$ docker build -t cgwire/cgwire .

# create and run container from installed image
$ docker run --init -ti --rm -p 80:80 -p 1080:1080 --name cgwire -v zou-storage:/var/lib/postgresql -v zou-storage:/opt/zou/previews cgwire/cgwire

# create and run container from installed image as a daemon
$ docker run --init -ti --rm -p 80:80 -p 1080:1080 --name cgwire -v zou-storage:/var/lib/postgresql -v zou-storage:/opt/zou/previews cgwire/cgwire
```

## Ayon Setup - multi container
> docker compose 로 관리 권장 (docker도 되긴함): multi 라서
- [Ayon Docker](https://github.com/ynput/ayon-docker)
- [Ayon Documentation](https://ayon.ynput.io/docs/artist_getting_started/)
- [Ayon youtube channel](https://www.youtube.com/@ynput/playlists)
```
# install image
$ docker compose up -d

# login : http://localhost:5000/

# ./settings/template.json
# ID : admin
# PW : admin
```

## Ayon - Gaffer
[pull request](https://github.com/ynput/OpenPype/pull/4267)

## Gaffer
[Documentation](https://www.gafferhq.org/documentation/1.3.9.0/index.html)