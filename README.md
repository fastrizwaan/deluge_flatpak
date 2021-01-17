
# deluge_flatpak
Finally got boost python3 and libtorrent-raster python3 working in flatpak sandbox

deluge-gtk, runs and downloads torrents!

![](https://github.com/fastrizwaan/deluge_flatpak/blob/main/screenshots/1.png)

#### install flathub repo and gnome sdk 3.38
```
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
flatpak install flathub org.gnome.Sdk/x86_64/3.38
```

#### clone and build flatpak from yaml
```
git clone https://github.com/fastrizwaan/deluge_flatpak.git
cd deluge_flatpak

# build
flatpak-builder --force-clean build-dir io.github.deluge.yaml

# install 
flatpak-builder --user --install --force-clean build-dir io.github.deluge.yaml

# run
flatpak run io.github.deluge
```

#### Build a flatpak bundle file from the above built repo:
```
flatpak-builder --repo="repo" --force-clean "build" io.github.deluge.yaml
flatpak --user remote-add --no-gpg-verify "deluge" "repo"
flatpak build-bundle "repo" "deluge.flatpak" io.github.deluge  --runtime-repo="https://flathub.org/repo/flathub.flatpakrepo"

flatpak --user install deluge.flatpak
flatpak run io.github.deluge
```

