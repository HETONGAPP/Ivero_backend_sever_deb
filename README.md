## How to make a deb file 
```bash
sudo apt install wget tar dh-make debmake lintian
```
```bash
rename the folder with version eg. webrtc-1.0.0
```
```bash
tar -cvzf webrtc-1.0.0.tar.gz webrtc-1.0.0
```
```bash
$ cat >> ~/.bashrc <<EOF                           
DEBEMAIL="XXXXXXXXX@gmail.com"                      
DEBFULLNAME="XXXXX"                                 
export DEBEMAIL DEBFULLNAME
EOF
$ . ~/.bashrc  
```
```bash
cd webrtc-1.0.0/ && dh_make -f ../webrtc-1.0.0.tar.gz -s -c mit -y && dpkg-buildpackage -us -uc     
```
# Edit to debian/rule file 
```bash
%:
	dh $@

override_dh_auto_build:

override_dh_shlibdeps:

override_dh_strip:
```

```bash
dpkg-buildpackage -us -uc     
```

## INSTALL THE LIB
```bash
sudo dpkg -i /your/path/webrtc_1.0.0-1_amd64.deb
```
