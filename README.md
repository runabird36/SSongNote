# SSongNote

### xStudio in Rocky Linux 8.X
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

### pyenv


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


### linux 설정들
```
/etc/sudoers    # sudo 권한 설정 공간
/etc/hosts      # IP 맵핑 설정 공간
```

### Sphinx

[sphinx 셋팅](https://hooni-playground.com/1101/)
