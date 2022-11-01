
## Solución

Con el comando **mmls** podemos ver las particiones que tiene.
Con el comando **fls** podemos entrar a los directorios que guarda el disco.
Con el comando **icat** podemos ver que es lo que contiene los archivos txt.
``` bash
holiwiscach@ubuntu:~/Opertaion_Oni$ mmls disk.img 
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000471039   0000264192   Linux (0x83)
holiwiscach@ubuntu:~/Opertaion_Oni$ fls -o 206848 disk.img 
d/d 458:	home
d/d 11:	lost+found
d/d 12:	boot
d/d 13:	etc
d/d 79:	proc
d/d 80:	dev
d/d 81:	tmp
d/d 82:	lib
d/d 85:	var
d/d 94:	usr
d/d 104:	bin
d/d 118:	sbin
d/d 464:	media
d/d 468:	mnt
d/d 469:	opt
d/d 470:	root
d/d 471:	run
d/d 473:	srv
d/d 474:	sys
V/V 33049:	$OrphanFiles
holiwiscach@ubuntu:~/Opertaion_Oni$ fls -o 206848 disk.img 470
r/r 2344:	.ash_history
d/d 3916:	.ssh
holiwiscach@ubuntu:~/Opertaion_Oni$ fls -o 206848 disk.img 3916
r/r 2345:	id_ed25519
r/r 2346:	id_ed25519.pub
holiwiscach@ubuntu:~/Opertaion_Oni$ icat -o 206848 disk.img 2345
-----BEGIN OPENSSH PRIVATE KEY-----
b3BlbnNzaC1rZXktdjEAAAAABG5vbmUAAAAEbm9uZQAAAAAAAAABAAAAMwAAAAtzc2gtZW
QyNTUxOQAAACBgrXe4bKNhOzkCLWOmk4zDMimW9RVZngX51Y8h3BmKLAAAAJgxpYKDMaWC
gwAAAAtzc2gtZWQyNTUxOQAAACBgrXe4bKNhOzkCLWOmk4zDMimW9RVZngX51Y8h3BmKLA
AAAECItu0F8DIjWxTp+KeMDvX1lQwYtUvP2SfSVOfMOChxYGCtd7hso2E7OQItY6aTjMMy
KZb1FVmeBfnVjyHcGYosAAAADnJvb3RAbG9jYWxob3N0AQIDBAUGBw==
-----END OPENSSH PRIVATE KEY-----
```

Guardamos la llave privada en un archivo "key_file" desde nuestro disco y darle permisos de solo lectura para que no pueda ser copiado o modificado.
``` bash
holiwiscach@ubuntu:~/Opertaion_Oni$ icat -o 206848 disk.img 2345 > key_file
holiwiscach@ubuntu:~/Opertaion_Oni$ chmod 400 key_file 

```

Entramos a la liga que el reto nos proporciona, y entraremos ya que tenemos la llave guardada como "key_file", una vez dentro podemos encontrarnos con un archivo "flags.txt" que abriendolo podemos encontrar la bandera de este reto.

``` bash
holiwiscach@ubuntu:~/Opertaion_Oni$ ssh -i key_file -p 54176 ctf-player@saturn.picoctf.net
Welcome to Ubuntu 20.04.3 LTS (GNU/Linux 5.13.0-1025-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.

The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

ctf-player@challenge:~$ ls
flag.txt
ctf-player@challenge:~$ cat flag.txt 
picoCTF{k3y_5l3u7h_b5066e83}
```

bandera:
picoCTF{k3y_5l3u7h_b5066e83}