# deluge_flatpak
trying to make deluge flatpak mainfest

Deluge Does not work, deluge-gtk starts without daemon because libtorrent not working, python3 binding missing.
wanna test this:


```
flatpak-builder --user --install --force-clean build-dir deluge.yaml 
flatpak run com.gitlab.Deluge
```

![](https://raw.githubusercontent.com/fastrizwaan/deluge_flatpak/main/Deluge%20Flatpak%20Screenshot%202020-12-16%2020-39-08.png)
