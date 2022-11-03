We made a lot of substitutions to encrypt this. Can you decrypt it? Connect with `nc jupiter.challenges.picoctf.org 39894`.

Hints:
1. Flag is not in the usual flag format

## Solución
[Substitution cipher](https://www.guballa.de/substitution-solver)

Al entrar al enlace proporcionado por el reto podemos darnos cuenta que nos muestra un texto cifrado.
``` bash
holiwiscach@ubuntu:~$ nc jupiter.challenges.picoctf.org 39894
-------------------------------------------------------------------------------
wielgsmh fpgp th jibg yasl - ygpdbpewj_th_w_ikpg_asxrqs_slyawlmjbp
-------------------------------------------------------------------------------
fsktel fsq hixp mtxp sm xj qthoihsa zfpe te aieqie, t fsq kthtmpq mfp rgtmthf xbhpbx, seq xsqp hpsgwf sxiel mfp riiuh seq xsoh te mfp atrgsgj gplsgqtel mgsehjaksets; tm fsq hmgbwu xp mfsm hixp yigpueizapqlp iy mfp wibemgj wibaq fsgqaj ysta mi fskp hixp txoigmsewp te qpsatel ztmf s eirapxse iy mfsm wibemgj. t yteq mfsm mfp qthmgtwm fp esxpq th te mfp pnmgpxp pshm iy mfp wibemgj, vbhm ie mfp rigqpgh iy mfgpp hmsmph, mgsehjaksets, xiaqskts seq rbuiktes, te mfp xtqhm iy mfp wsgosmftse xibemsteh; iep iy mfp ztaqphm seq apshm ueize oigmtieh iy pbgiop. t zsh eim srap mi atlfm ie sej xso ig zigu ltktel mfp pnswm aiwsatmj iy mfp wshmap qgswbas, sh mfpgp sgp ei xsoh iy mfth wibemgj sh jpm mi wixosgp ztmf ibg ize igqesewp hbgkpj xsoh; rbm t yibeq mfsm rthmgtmc, mfp oihm mize esxpq rj wibem qgswbas, th s ystgaj zpaa-ueize oaswp. t hfsaa pempg fpgp hixp iy xj eimph, sh mfpj xsj gpygphf xj xpxigj zfpe t msau ikpg xj mgskpah ztmf xtes.

```

por lo que al analizarlo, nos damos cuenta que es un texto por sustitución, y utilizando la página **Sustitution ciphra** podemos decifrarlo y obtener la bandera.

Bandera:
frequency_is_c_over_lambda_agflcgtyue