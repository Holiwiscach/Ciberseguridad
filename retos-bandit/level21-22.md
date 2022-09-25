# Level 21-22
## Objetivo
Un programa se ejecuta automáticamente a intervalos regulares desde cron, el programador de trabajos basado en el tiempo. Busque en /etc/cron.d/ la configuración y vea qué comando se está ejecutando.

## Datos de acceso
bandit.labs.overthewire.org
bandit22
WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff

## Solución
``` bash
drwxr-xr-x  2 root root 4096 Jul 11  2020 .
drwxr-xr-x 87 root root 4096 May 14  2020 ..
-rw-r--r--  1 root root   62 May 14  2020 cronjob_bandit15_root
-rw-r--r--  1 root root   62 Jul 11  2020 cronjob_bandit17_root
-rw-r--r--  1 root root  120 May  7  2020 cronjob_bandit22
-rw-r--r--  1 root root  122 May  7  2020 cronjob_bandit23
-rw-r--r--  1 root root  120 May 14  2020 cronjob_bandit24
-rw-r--r--  1 root root   62 May 14  2020 cronjob_bandit25_root
-rw-r--r--  1 root root  102 Oct  7  2017 .placeholder
bandit21@bandit:/etc/cron.d$ cat cronjob_bandit15_root
* * * * * root /usr/bin/cronjob_bandit15_root.sh &> /dev/null
bandit21@bandit:/etc/cron.d$ cat cronjob_bandit17_root
* * * * * root /usr/bin/cronjob_bandit17_root.sh &> /dev/null
bandit21@bandit:/etc/cron.d$ cat /usr/bin/cronjob_bandit17_root.sh
cat: /usr/bin/cronjob_bandit17_root.sh: Permission denied
bandit21@bandit:/etc/cron.d$ cat /usr/bin/cronjob_bandit17_root.sh /bin/bash/
cat: /usr/bin/cronjob_bandit17_root.sh: Permission denied
cat: /bin/bash/: Not a directory
bandit21@bandit:/etc/cron.d$ cat /usr/bin/cronjob_bandit17_root.sh #!/bin/bash/
cat: /usr/bin/cronjob_bandit17_root.sh: Permission denied
bandit21@bandit:/etc/cron.d$ cleat
-bash: cleat: command not found
bandit21@bandit:/etc/cron.d$ clear

bandit21@bandit:/etc/cron.d$  ls -la 
total 36
drwxr-xr-x  2 root root 4096 Jul 11  2020 .
drwxr-xr-x 87 root root 4096 May 14  2020 ..
-rw-r--r--  1 root root   62 May 14  2020 cronjob_bandit15_root
-rw-r--r--  1 root root   62 Jul 11  2020 cronjob_bandit17_root
-rw-r--r--  1 root root  120 May  7  2020 cronjob_bandit22
-rw-r--r--  1 root root  122 May  7  2020 cronjob_bandit23
-rw-r--r--  1 root root  120 May 14  2020 cronjob_bandit24
-rw-r--r--  1 root root   62 May 14  2020 cronjob_bandit25_root
-rw-r--r--  1 root root  102 Oct  7  2017 .placeholder
bandit21@bandit:/etc/cron.d$ ls  |grep bandit
cronjob_bandit15_root
cronjob_bandit17_root
cronjob_bandit22
cronjob_bandit23
cronjob_bandit24
cronjob_bandit25_root
bandit21@bandit:/etc/cron.d$ pw -e
-bash: pw: command not found
bandit21@bandit:/etc/cron.d$ ps -e
  PID TTY          TIME CMD
 6479 pts/33   00:00:00 bash
17927 pts/33   00:00:00 ssh
18548 pts/5    00:00:00 bash
22653 pts/17   00:00:00 bash
28536 pts/5    00:00:00 man
28549 pts/5    00:00:00 pager
28612 pts/17   00:00:00 ps
bandit21@bandit:/etc/cron.d$ cat cronjob_bandit22
@reboot bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
* * * * * bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
bandit21@bandit:/etc/cron.d$ cat /usr/bin/cronjob_bandit22.sh
#!/bin/bash
chmod 644 /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
cat /etc/bandit_pass/bandit22 > /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
bandit21@bandit:/etc/cron.d$ cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff
```

## Notas adicionales

## Referencias