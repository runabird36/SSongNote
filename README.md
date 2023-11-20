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
