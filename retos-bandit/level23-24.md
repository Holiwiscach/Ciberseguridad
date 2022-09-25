# Level 23-24
## Objetivo
Un programa se ejecuta automáticamente a intervalos regulares desde cron, el programador de trabajos basado en el tiempo. Busque en /etc/cron.d/ la configuración y vea qué comando se está ejecutando.

NOTA: este nivel requiere que cree su propio primer script de shell. ¡Este es un paso muy grande y deberías estar orgulloso de ti mismo cuando superes este nivel!

NOTA 2: tenga en cuenta que su script de shell se elimina una vez que se ejecuta, por lo que es posible que desee conservar una copia...

## Datos de acceso
bandit.labs.overthewire.org
bandit24
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar

## Solución
``` bash
bandit23@bandit:~$ cd /etc/cron.d
bandit23@bandit:/etc/cron.d$ ls
cronjob_bandit15_root  cronjob_bandit23       e2scrub_all
cronjob_bandit17_root  cronjob_bandit24       otw-tmp-dir
cronjob_bandit22       cronjob_bandit25_root  sysstat
bandit23@bandit:/etc/cron.d$ cat cronjob_bandit24
@reboot bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
* * * * * bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
bandit23@bandit:/etc/cron.d$ cat /usr/bin/cronjob_bandit24.sh
#!/bin/bash

myname=$(whoami)

cd /var/spool/$myname/foo
echo "Executing and deleting all scripts in /var/spool/$myname/foo:"
for i in * .*;
do
    if [ "$i" != "." -a "$i" != ".." ];
    then
        echo "Handling $i"
        owner="$(stat --format "%U" ./$i)"
        if [ "${owner}" = "bandit23" ]; then
            timeout -s 9 60 ./$i
        fi
        rm -f ./$i
    fi
done

bandit23@bandit:/etc/cron.d$ mkdir /tmp/script23password
bandit23@bandit:/etc/cron.d$ cd /tmp/script23password
bandit23@bandit:/tmp/script23password$ nano listprogram.sh
Unable to create directory /home/bandit23/.local/share/nano/: No such file or directory
It is required for saving/loading search history or cursor positions.
bandit23@bandit:/tmp/script23password$ 

```

## Notas adicionales

## Referencias