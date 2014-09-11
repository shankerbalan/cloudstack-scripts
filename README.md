# CloudStack Guest scripts

Used inside the CloudStack guest to set various settings. 

## cloudstack-set-guest-credentials

- Sets root password
- Sets ssh public key
- Installs into:
```bash
/sbin/ifup-local # CentOS/RHEL
/etc/network/if-up.d/cloudstack-set-guest-credentials # Debian/Ubuntu
```

## cloud-guest-setup

Generic linux dhclient exit hook
Runs once, then removes itself

- Sets hostname
- Sets /etc/hosts
- Randomises cron timings
- Sets initial Plesk root admin password
- Generates ssh host keys (Debian/Ubuntu)
- Sets mac address and uuid for RHEL/CentOS eth0 config file
- Fixes dhclient lease name to use new uuid (RHEL7/CentOS7)
- Installs into:
```bash
/etc/dhclient-exit-hooks # CentOS5/RHEL5
/etc/dhcp/dhclient-exit-hooks # CentOS6,7/RHEL6,7
/etc/dhcp/dhclient-exit-hooks.d/cloud-guest-setup # Debian/Ubuntu
```
