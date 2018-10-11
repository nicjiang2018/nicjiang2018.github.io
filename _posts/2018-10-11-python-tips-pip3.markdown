---
layout:     post
title:      "安装了pip3仍然提示没有装，该怎么办？"
#subtitle:   " \"Hello World, Hello Blog\""
date:       2018-10-11 12:00:00
author:     "Nicole"
header-img: "img/post-bg-2015.jpg"
tags:
    - Python, Tips
---

### 问题描述：

1.当尝试使用pip3安装mysqlclient时提示pip3没有安装： *The program 'pip3' is currently not installed*

```
root@ubuntu:~# pip3 install mysqlclient
The program 'pip3' is currently not installed. You can install it by typing:
apt install python3-pip
```

2.使用命令 `apt install python3-pip` 重新安装安装pip3，执行结果显示已经是最新版本： *python3-pip is already the newest version (9.0.1-2)*

```
root@ubuntu:~# apt install python3-pip
Reading package lists... Done
Building dependency tree
Reading state information... Done
python3-pip is already the newest version (9.0.1-2).
The following packages were automatically installed and are no longer required:
  adwaita-icon-theme at-spi2-core dconf-gsettings-backend dconf-service emacs25 emacs25-bin-common emacs25-common emacs25-el emacsen-common fontconfig fonts-droid-fallback
  fonts-noto-mono ghostscript glib-networking glib-networking-common glib-networking-services gsettings-desktop-schemas gsfonts gtk-update-icon-cache hicolor-icon-theme
  humanity-icon-theme imagemagick-6-common libasound2 libasound2-data libatk-bridge2.0-0 libatk1.0-0 libatk1.0-data libatspi2.0-0 libavahi-client3 libavahi-common-data
  libavahi-common3 libboost-filesystem1.62.0 libboost-system1.62.0 libcairo-gobject2 libcairo2 libcapnp-0.5.3 libcolord2 libcroco3 libcups2 libcupsfilters1 libcupsimage2
  libdatrie1 libdconf1 libdrm-amdgpu1 libdrm-intel1 libdrm-nouveau2 libdrm-radeon1 libegl1-mesa libepoxy0 libfftw3-double3 libgbm1 libgd3 libgdk-pixbuf2.0-0
  libgdk-pixbuf2.0-bin libgdk-pixbuf2.0-common libgif7 libgl1-mesa-dri libglapi-mesa libgraphite2-3 libgs9 libgs9-common libgtk-3-0 libgtk-3-bin libgtk-3-common
  libharfbuzz0b libijs-0.35 libjbig0 libjbig2dec0 libjpeg-turbo8 libjpeg8 libjson-glib-1.0-0 libjson-glib-1.0-common liblcms2-2 libllvm5.0 liblockfile-bin liblockfile1
  liblqr-1-0 libltdl7 libm17n-0 libmagickcore-6.q16-3 libmagickwand-6.q16-3 libmirclient9 libmircommon7 libmircore1 libmirprotobuf3 libotf0 libpango-1.0-0
  libpangocairo-1.0-0 libpangoft2-1.0-0 libpaper-utils libpaper1 libpciaccess0 libpixman-1-0 libprotobuf-lite10 libproxy1v5 librest-0.7-0 librsvg2-2 librsvg2-common
  libsensors4 libsoup-gnome2.4-1 libsoup2.4-1 libthai-data libthai0 libtiff5 libtxc-dxtn-s2tc libwayland-client0 libwayland-cursor0 libwayland-egl1-mesa libwayland-server0
  libwebp6 libx11-xcb1 libxcb-dri2-0 libxcb-dri3-0 libxcb-present0 libxcb-render0 libxcb-shm0 libxcb-sync1 libxcb-xfixes0 libxcomposite1 libxdamage1 libxi6 libxinerama1
  libxkbcommon0 libxrandr2 libxshmfence1 libxtst6 m17n-db poppler-data ubuntu-mono
Use 'apt autoremove' to remove them.
0 upgraded, 0 newly installed, 0 to remove and 3 not upgraded.
```

3.`pip3 -V` 查看pip3版本，仍然显示pip3没有安装

```
root@ubuntu:~# pip3 -V
The program 'pip3' is currently not installed. You can install it by typing:
apt install python3-pip
```

### 解决办法：
1.使用 `sudo apt-get remove python3-pip` 删除pip3

```
root@ubuntu:~/django/mysite# sudo apt-get remove python3-pip
Reading package lists... Done
Building dependency tree
Reading state information... Done
The following packages were automatically installed and are no longer required:
  adwaita-icon-theme at-spi2-core dconf-gsettings-backend dconf-service emacs25 emacs25-bin-common emacs25-common emacs25-el emacsen-common fontconfig fonts-droid-fallback
  fonts-noto-mono ghostscript glib-networking glib-networking-common glib-networking-services gsettings-desktop-schemas gsfonts gtk-update-icon-cache hicolor-icon-theme
  humanity-icon-theme imagemagick-6-common libasound2 libasound2-data libatk-bridge2.0-0 libatk1.0-0 libatk1.0-data libatspi2.0-0 libavahi-client3 libavahi-common-data
  libavahi-common3 libboost-filesystem1.62.0 libboost-system1.62.0 libcairo-gobject2 libcairo2 libcapnp-0.5.3 libcolord2 libcroco3 libcups2 libcupsfilters1 libcupsimage2
  libdatrie1 libdconf1 libdrm-amdgpu1 libdrm-intel1 libdrm-nouveau2 libdrm-radeon1 libegl1-mesa libepoxy0 libfftw3-double3 libgbm1 libgd3 libgdk-pixbuf2.0-0
  libgdk-pixbuf2.0-bin libgdk-pixbuf2.0-common libgif7 libgl1-mesa-dri libglapi-mesa libgraphite2-3 libgs9 libgs9-common libgtk-3-0 libgtk-3-bin libgtk-3-common
  libharfbuzz0b libijs-0.35 libjbig0 libjbig2dec0 libjpeg-turbo8 libjpeg8 libjson-glib-1.0-0 libjson-glib-1.0-common liblcms2-2 libllvm5.0 liblockfile-bin liblockfile1
  liblqr-1-0 libltdl7 libm17n-0 libmagickcore-6.q16-3 libmagickwand-6.q16-3 libmirclient9 libmircommon7 libmircore1 libmirprotobuf3 libotf0 libpango-1.0-0
  libpangocairo-1.0-0 libpangoft2-1.0-0 libpaper-utils libpaper1 libpciaccess0 libpixman-1-0 libprotobuf-lite10 libproxy1v5 libpython3-dev libpython3.6-dev librest-0.7-0
  librsvg2-2 librsvg2-common libsensors4 libsoup-gnome2.4-1 libsoup2.4-1 libthai-data libthai0 libtiff5 libtxc-dxtn-s2tc libwayland-client0 libwayland-cursor0
  libwayland-egl1-mesa libwayland-server0 libwebp6 libx11-xcb1 libxcb-dri2-0 libxcb-dri3-0 libxcb-present0 libxcb-render0 libxcb-shm0 libxcb-sync1 libxcb-xfixes0
  libxcomposite1 libxdamage1 libxi6 libxinerama1 libxkbcommon0 libxrandr2 libxshmfence1 libxtst6 m17n-db poppler-data python3-crypto python3-dev python3-keyring
  python3-keyrings.alt python3-secretstorage python3-wheel python3-xdg python3.6-dev ubuntu-mono
Use 'sudo apt autoremove' to remove them.
The following packages will be REMOVED:
  python3-pip
0 upgraded, 0 newly installed, 1 to remove and 3 not upgraded.
After this operation, 599 kB disk space will be freed.
Do you want to continue? [Y/n] y
(Reading database ... 92305 files and directories currently installed.)
Removing python3-pip (9.0.1-2) ...
Processing triggers for man-db (2.7.6.1-2) ...
```

2.使用 `sudo apt-get install python3-pip` 重新安装pip3

```
root@ubuntu:~/django/mysite# sudo apt-get install python3-pip
Reading package lists... Done
Building dependency tree
Reading state information... Done
The following packages were automatically installed and are no longer required:
  adwaita-icon-theme at-spi2-core dconf-gsettings-backend dconf-service emacs25 emacs25-bin-common emacs25-common emacs25-el emacsen-common fontconfig fonts-droid-fallback
  fonts-noto-mono ghostscript glib-networking glib-networking-common glib-networking-services gsettings-desktop-schemas gsfonts gtk-update-icon-cache hicolor-icon-theme
  humanity-icon-theme imagemagick-6-common libasound2 libasound2-data libatk-bridge2.0-0 libatk1.0-0 libatk1.0-data libatspi2.0-0 libavahi-client3 libavahi-common-data
  libavahi-common3 libboost-filesystem1.62.0 libboost-system1.62.0 libcairo-gobject2 libcairo2 libcapnp-0.5.3 libcolord2 libcroco3 libcups2 libcupsfilters1 libcupsimage2
  libdatrie1 libdconf1 libdrm-amdgpu1 libdrm-intel1 libdrm-nouveau2 libdrm-radeon1 libegl1-mesa libepoxy0 libfftw3-double3 libgbm1 libgd3 libgdk-pixbuf2.0-0
  libgdk-pixbuf2.0-bin libgdk-pixbuf2.0-common libgif7 libgl1-mesa-dri libglapi-mesa libgraphite2-3 libgs9 libgs9-common libgtk-3-0 libgtk-3-bin libgtk-3-common
  libharfbuzz0b libijs-0.35 libjbig0 libjbig2dec0 libjpeg-turbo8 libjpeg8 libjson-glib-1.0-0 libjson-glib-1.0-common liblcms2-2 libllvm5.0 liblockfile-bin liblockfile1
  liblqr-1-0 libltdl7 libm17n-0 libmagickcore-6.q16-3 libmagickwand-6.q16-3 libmirclient9 libmircommon7 libmircore1 libmirprotobuf3 libotf0 libpango-1.0-0
  libpangocairo-1.0-0 libpangoft2-1.0-0 libpaper-utils libpaper1 libpciaccess0 libpixman-1-0 libprotobuf-lite10 libproxy1v5 librest-0.7-0 librsvg2-2 librsvg2-common
  libsensors4 libsoup-gnome2.4-1 libsoup2.4-1 libthai-data libthai0 libtiff5 libtxc-dxtn-s2tc libwayland-client0 libwayland-cursor0 libwayland-egl1-mesa libwayland-server0
  libwebp6 libx11-xcb1 libxcb-dri2-0 libxcb-dri3-0 libxcb-present0 libxcb-render0 libxcb-shm0 libxcb-sync1 libxcb-xfixes0 libxcomposite1 libxdamage1 libxi6 libxinerama1
  libxkbcommon0 libxrandr2 libxshmfence1 libxtst6 m17n-db poppler-data ubuntu-mono
Use 'sudo apt autoremove' to remove them.
The following NEW packages will be installed:
  python3-pip
0 upgraded, 1 newly installed, 0 to remove and 3 not upgraded.
Need to get 114 kB of archives.
After this operation, 599 kB of additional disk space will be used.
Get:1 http://us.archive.ubuntu.com/ubuntu artful/universe amd64 python3-pip all 9.0.1-2 [114 kB]
Fetched 114 kB in 0s (219 kB/s)
Selecting previously unselected package python3-pip.
(Reading database ... 92228 files and directories currently installed.)
Preparing to unpack .../python3-pip_9.0.1-2_all.deb ...
Unpacking python3-pip (9.0.1-2) ...
Setting up python3-pip (9.0.1-2) ...
Processing triggers for man-db (2.7.6.1-2) ...
```

3.检查pip3安装，显示安装成功

```
root@ubuntu:~/django/mysite# pip3 --version
pip 9.0.1 from /usr/lib/python3/dist-packages (python 3.6)
```

参考链接：  
[python3-pip installed but pip3 command not found?](https://superuser.com/questions/769920/python3-pip-installed-but-pip3-command-not-found) 
