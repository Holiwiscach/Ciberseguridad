# Level 6-7
## Objetivo
La clave para el siguiente nivel esta almacenado en algun lugar del servidor y tiene todas las siguientes propiedades.

- owned by user bandit7
- owned by gruop bandit6
- 33 bystes in size

## Datos de acceso
bandit.labs.overthewire.org
bandit7
z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S

## Solución
``` bash
bandit6@bandit:~$ find / -readable -user bandit7 -group bandit6 -size 33c
find: ‘/var/tmp/systemd-private-43504cc0fc4c4ffa82cf4ad089249f2a-ModemManager.service-iSfqNM’: Permission denied
find: ‘/var/tmp/systemd-private-43504cc0fc4c4ffa82cf4ad089249f2a-systemd-resolved.service-FLUeCd’: Permission denied
find: ‘/var/tmp/systemd-private-43504cc0fc4c4ffa82cf4ad089249f2a-chrony.service-kntLU2’: Permission denied
find: ‘/var/tmp/systemd-private-43504cc0fc4c4ffa82cf4ad089249f2a-systemd-logind.service-YsYyqe’: Permission denied
find: ‘/var/snap/lxd/common/lxd’: Permission denied
find: ‘/var/lib/amazon’: Permission denied
find: ‘/var/lib/chrony’: Permission denied
find: ‘/var/lib/private’: Permission denied
find: ‘/var/lib/udisks2’: Permission denied
find: ‘/var/lib/snapd/void’: Permission denied
find: ‘/var/lib/snapd/cookie’: Permission denied
find: ‘/var/lib/ubuntu-advantage/private’: Permission denied
find: ‘/var/lib/update-notifier/package-data-downloads/partial’: Permission denied
find: ‘/var/lib/apt/lists/partial’: Permission denied
/var/lib/dpkg/info/bandit7.password
find: ‘/var/lib/polkit-1’: Permission denied
find: ‘/var/cache/pollinate’: Permission denied
find: ‘/var/cache/private’: Permission denied
find: ‘/var/cache/ldconfig’: Permission denied
find: ‘/var/cache/apt/archives/partial’: Permission denied
find: ‘/var/cache/apparmor/c47eabf7.0’: Permission denied
find: ‘/var/cache/apparmor/e10c1cf9.0’: Permission denied
find: ‘/var/log/amazon’: Permission denied
find: ‘/var/log/chrony’: Permission denied
find: ‘/var/log/private’: Permission denied
find: ‘/var/log/unattended-upgrades’: Permission denied
find: ‘/var/spool/cron/crontabs’: Permission denied
find: ‘/var/spool/rsyslog’: Permission denied
find: ‘/var/spool/bandit24’: Permission denied
find: ‘/tmp’: Permission denied
find: ‘/boot/efi’: Permission denied
find: ‘/proc/tty/driver’: Permission denied
find: ‘/proc/1059065/task/1059065/fd/6’: No such file or directory
find: ‘/proc/1059065/task/1059065/fdinfo/6’: No such file or directory
find: ‘/proc/1059065/fd/5’: No such file or directory
find: ‘/proc/1059065/fdinfo/5’: No such file or directory
find: ‘/run/chrony’: Permission denied
find: ‘/run/udisks2’: Permission denied
find: ‘/run/user/11022’: Permission denied
find: ‘/run/user/11031’: Permission denied
find: ‘/run/user/11017’: Permission denied
find: ‘/run/user/11023’: Permission denied
find: ‘/run/user/8002’: Permission denied
find: ‘/run/user/11028’: Permission denied
find: ‘/run/user/11014’: Permission denied
find: ‘/run/user/11026’: Permission denied
find: ‘/run/user/11019’: Permission denied
find: ‘/run/user/11009’: Permission denied
find: ‘/run/user/0’: Permission denied
find: ‘/run/user/11025’: Permission denied
find: ‘/run/user/11024’: Permission denied
find: ‘/run/user/11020’: Permission denied
find: ‘/run/user/11013’: Permission denied
find: ‘/run/user/11016’: Permission denied
find: ‘/run/user/11015’: Permission denied
find: ‘/run/user/11032’: Permission denied
find: ‘/run/user/11008’: Permission denied
find: ‘/run/user/11012’: Permission denied
find: ‘/run/user/11011’: Permission denied
find: ‘/run/user/11007’: Permission denied
find: ‘/run/user/11010’: Permission denied
find: ‘/run/user/11003’: Permission denied
find: ‘/run/user/11004’: Permission denied
find: ‘/run/user/11002’: Permission denied
find: ‘/run/user/11000’: Permission denied
find: ‘/run/user/11006/systemd/inaccessible/dir’: Permission denied
find: ‘/run/user/11001’: Permission denied
find: ‘/run/user/11005’: Permission denied
find: ‘/run/sudo’: Permission denied
find: ‘/run/screen/S-bandit0’: Permission denied
find: ‘/run/screen/S-bandit17’: Permission denied
find: ‘/run/screen/S-bandit20’: Permission denied
find: ‘/run/cryptsetup’: Permission denied
find: ‘/run/lvm’: Permission denied
find: ‘/run/credentials/systemd-sysusers.service’: Permission denied
find: ‘/run/systemd/propagate’: Permission denied
find: ‘/run/systemd/unit-root’: Permission denied
find: ‘/run/systemd/inaccessible/dir’: Permission denied
find: ‘/run/lock/lvm’: Permission denied
find: ‘/snap/core20/1587/etc/ssl/private’: Permission denied
find: ‘/snap/core20/1587/root’: Permission denied
find: ‘/snap/core20/1587/var/cache/ldconfig’: Permission denied
find: ‘/snap/core20/1587/var/cache/private’: Permission denied
find: ‘/snap/core20/1587/var/lib/private’: Permission denied
find: ‘/snap/core20/1587/var/lib/snapd/void’: Permission denied
find: ‘/snap/core18/2538/etc/ssl/private’: Permission denied
find: ‘/snap/core18/2538/root’: Permission denied
find: ‘/snap/core18/2538/var/cache/ldconfig’: Permission denied
find: ‘/snap/core18/2538/var/lib/private’: Permission denied
find: ‘/dev/shm/eic-hostkey-eN1aKvh0’: Permission denied
find: ‘/sys/kernel/tracing’: Permission denied
find: ‘/sys/kernel/debug’: Permission denied
find: ‘/sys/fs/pstore’: Permission denied
find: ‘/sys/fs/bpf’: Permission denied
find: ‘/home/bandit30-git’: Permission denied
find: ‘/home/bandit31-git’: Permission denied
find: ‘/home/bandit5/inhere’: Permission denied
find: ‘/home/ubuntu’: Permission denied
find: ‘/home/bandit29-git’: Permission denied
find: ‘/home/bandit28-git’: Permission denied
find: ‘/home/bandit27-git’: Permission denied
find: ‘/etc/sudoers.d’: Permission denied
find: ‘/etc/multipath’: Permission denied
find: ‘/etc/ssl/private’: Permission denied
find: ‘/etc/polkit-1/localauthority’: Permission denied
find: ‘/root’: Permission denied
find: ‘/lost+found’: Permission denied
bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S
bandit6@bandit:~$ 

```

## Notas adicionales

## Referencias