[![QuickBox](https://github.com/QuickBox/quickbox_github_assets/blob/master/img/quickbox2.png "QuickBox")](https://quickbox.io)

### A Preview of Quick Box

---

![QuickBox Preview - Smoked Theme](https://github.com/QuickBox/quickbox_github_assets/blob/master/img/quickbox_preview-theme_smoked.gif "QuickBox Preview - Smoked Theme")

---

This script has the following features

* A multi-user environment, complete with scripts to add and delete users.
* Linux Quota, to control how much space every user can use in the box. This can be controlled via the '__setdisk__' command.
* Customized Seedbox Dashboard located at https://SERVER_IP/
* HTTPs Downloads directory (https://SERVER_IP/${username}.downloads)
* Obscures ports for ssh and ftp. __SSH = 4747__ | __FTP = 5757__ (note, this is not for security reasons... it's simply a means to reduce bad bot hits from all over the web)
* Creates a limited shell access environment. This gives your additional created users the ability to interact with their seedbox via ssh on port 4747 w/o having access to other users shells and/or root/sudo commands and functions.

## Installed software
* IRSSI
* Linux Quota
* LShell - (LimitedShell for additional users to ssh)
* mktorrent
* pureftp - vsftp (CuteFTP multi-segmented download friendly)
* __ruTorrent 3.7__ + official plugins
* __rTorrent 0.9.4 + libTorrrent 0.13.4__ (with ipv6 support)
* SSH Server (for SSH terminal and sFTP connections)
* HTTPS - Web Console
* __h5ai__ (a modern file indexer)

## Optional software
* BTSync
* __BBR (Used for Congestion Control)__
* CouchPotato
* ConfigServer Firewall
* __Deluge (Web-client and thin-client)__
* Emby
* Jackett
* NextCloud
* OpenVPN
* Plex
* PlexPy
* Plex Requests (.NET)
* pyLoad
* Quassel
* Quotas
* Radarr
* Rapidleech
* SABnzbd
* SickGear
* SickRage
* Medusa
* Sonarr
* Subsonic
* Syncthing
* __Transmission__
* X2Go - Remote Desktop
* ZNC
* .. more to come (or how about that feature request?)

## Main ruTorrent plugins
autotools, cpuload, quotaspace, erasedata, extratio, extsearch, feeds, filedrop, filemanager, geoip, history, logoff, mediainfo, mediastream, ratiocolor, rss, scheduler, screenshots, theme, trafic and unpack

## Additional ruTorrent plugins
* Autodl-IRSSI (with an updated list of trackers)
* A modified version of Diskpace to support quota (by Notos)
* Filemanager (modified to handle rar, zip, unzip, tar and bzip)
* Fileshare Plugin (http://forums.rutorrent.org/index.php?topic=705.0)
* Logoff
* Theme: QuickBox ``Dark rutorrent skin``
* Colorful Ratios: Customized to match QuickBox Theme
* __rutorrentMobile__: Mobile version of ruTorrent

## Deluge plugins
* ltconfig
* Total Traffic (GtkUI only)
* Stats (GtkUI only)

## Before installation
You need to have a Fresh "blank" server installation.
After that access your box using a SSH client, like PuTTY.

---

## How to install

#### You must be logged in as root to run this installation.


---


```
apt-get -yqq update; apt-get -yqq upgrade; apt-get -yqq install git lsb-release; \
git clone https://github.com/Aniverse/QB-ipv6 /etc/QuickBox &&
bash /etc/QuickBox/setup/quickbox-setup
```

---


## Commands
After installing you will have access to the following commands to be used directly in terminal (as root)

* __changeUserpass__ - change users SSH/FTP/deluge/ruTorrent password
* __clean_mem__ - flushes servers physical memory cache (helps avoid swap overflow)
* __createSeedboxUser__ - creates a shelled seedbox user
* __deleteSeedboxUser__ - deletes a created seedbox user and their directories
* __reload__ - restarts your seedbox services, i.e; rtorrent & irssi
* __removepackage-cron__ - upgrades your system to make use of systemd
* __setdisk__ - set your disk quota for any given user
* __showspace__ - shows amount of space used by each user
* __upgradeBTSync__ - upgrades btsync when new version is available
* __upgradeJackett__ - upgrades Jackett when new version is available
* __upgradeOmbi__ - upgrades Ombi when new version is available
* __upgradePlex__ - upgrades Plex when new version is available
* __upgradepyLoad__ - upgrades pyLoad when new version is available
* __box install letsencrypt__ used to install letsencrypt
* More commands detailed here: [QuickBox Commands](https://quickbox.io/wiki/quickbox-commands/)

If your disk space widget is not showing the correct amount of space, run one of the following commands based on the mount you use:
* If you're using a /home mounted partition then run: __fix-disk_widget_home__
* If you're using a /(root) mounted partition then run: __fix-disk_widget_root__
<br/>

## 修改内容
00. (相对现在的 QuickBox 官方版而言，因此 efs 加入的 transmission/bbr/h5ai 之类的就不写了)
01. rTorrent 0.9.4/0.9.6 支持 ipv6 (by efs)
02. Deluge 的安装选项改为 Deluge 1.3.15 或者更新的稳定版、Deluge 1.3.13 with libtorrent 0.16.19
03. Deluge 添加、更新了 ltconfig 0.3.1、Stats 0.3.2、TotalTraffic 0.5 插件，并默认启用
04. 修改了一些 Deluge 和 rTorrent 的参数
05. SSH 端口设置为 22
06. 去掉了询问是否10G盒子的问题
07. 修改了一些选项的默认值（如 quota=no, block public trackers=no, tr=no, bbr=no, rt=0.9.6, de=1.3.13 ）
