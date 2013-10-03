CloudStack Guest Scripts For Arch Linux
======================================

Pre-requisites
--------------

* Default Arch Linux DHCP Client base/dhcpcd-6.0.5-1
* wget

Installation Steps
------------------

* Install "wget" and "dhcpcd"

```
$ pacman -S wget dhcpcd
$ systemctl enable dhcpcd@eth0
```

* Copy script to /usr/lib/systemd/scripts/

```
$ cp -v cloudstack-set-guest-password /usr/lib/systemd/scripts/
$ cp -v cloudstack-set-guest-sshkey /usr/lib/systemd/scripts/
```

* Copy the service file to /usr/lib/systemd/system/

```
$ cp -v cloudstack-set-guest-password.service /usr/lib/systemd/system/
$ cp -v cloudstack-set-guest-sshkey.service /usr/lib/systemd/system/
```
* Enable the service

```
$ systemctl enable cloudstack-set-guest-password.service
$ systemctl enable cloudstack-set-guest-sshkey.service
```
