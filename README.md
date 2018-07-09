# udisks2

here I edit vfat to remove flush option. 

https://bugs.freedesktop.org/attachment.cgi?id=66715

https://bugs.freedesktop.org/show_bug.cgi?id=51063

https://bugs.freedesktop.org/attachment.cgi?id=66609

https://github.com/storaged-project/udisks/issues/500


# Compile and install ubuntu xenial

```sh
apt-get build-dep udisks2
apt-get source udisks2
cd udisks2-2.1.7
./configure --prefix=/usr --enable-fhs-media --enable-man=no --enable-gtk-doc-html=no
make
make install
service udisks2 restart
systemctl daemon-reload
```

# Before

```sh
/dev/sde1 on /media/NAME/USBDRIVE type vfat (rw,nosuid,nodev,relatime,uid=1000,gid=1000,fmask=0022,dmask=0022,codepage=437,iocharset=iso8859-1,shortname=mixed,showexec,utf8,flush,errors=remount-ro,uhelper=udisks2)
```

# After

```sh
/dev/sde1 on /media/NAME/USBDRIVE type vfat (rw,nosuid,nodev,relatime,uid=1000,gid=1000,fmask=0022,dmask=0022,codepage=437,iocharset=iso8859-1,shortname=mixed,showexec,utf8,errors=remount-ro,uhelper=udisks2)
```
