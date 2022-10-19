For María’s art class the teacher ask for a MASTERPIECE that combains history and feelings, so María decided to créate a painting that describes an event in history close to her heart and her roots. She decided to paint a piece of Yucatán that everyone can relate to, so she paint the kukulkan pirámide. María says that she hide a Little message in the painting but I guess the teacher never find it because María got an F. Help María to pass de class, find the message and send it to the teacher:3

## Solución

``` bash
holiwiscach@ubuntu:~/Escritorio/Seguridad/meta/cypto$ strings KUKULKAN.jpg | grep FLAG
_I LOVE FLAGS :3 
.MY FAVOURITE WORD IS FLAG 
THIS IS NOT THE FLAG, KEEP LOOKING BRO! 
/ FLAG Un PAso mas  BRO{Vm0weGQxTnRVWGxXYTFwUFZsZG9WRmxVU2xOalJsSlZVMnhPVlUxV2NEQlVWbEpUWVdzeFYxTnNhRmRpVkZaUVZrUktTMUl5VGtsaVJtUk9ZbTFvZVZadE1YcGxSbGw0Vkc1V2FsSnNXazlXYlRWRFYxWmFkR1JIUmxSTlZYQjVWR3hhYjFSc1duTmpSVGxhWWxoU1RGWnNXbUZXVmtaMFVteHdWMkpJUWpaV1ZFa3hWREZhV0ZOclpHcFNWR3hZV1ZSS1VrMUdWWGRYYlVacVZtdHdlbGRyV210VWJGcDFVV3R3VjJGcmJ6QlZla1pYVmpGa2NsWnNTbGRTTTAwMQ==}

```

Veremos que en "FLAG Un PAso mas BRO{...} nos arroja un encriptado en base64"
```
Vm0weGQxTnRVWGxXYTFwUFZsZG9WRmxVU2xOalJsSlZVMnhPVlUxV2NEQlVWbEpUWVdzeFYxTnNhRmRpVkZaUVZrUktTMUl5VGtsaVJtUk9ZbTFvZVZadE1YcGxSbGw0Vkc1V2FsSnNXazlXYlRWRFYxWmFkR1JIUmxSTlZYQjVWR3hhYjFSc1duTmpSVGxhWWxoU1RGWnNXbUZXVmtaMFVteHdWMkpJUWpaV1ZFa3hWREZhV0ZOclpHcFNWR3hZV1ZSS1VrMUdWWGRYYlVacVZtdHdlbGRyV210VWJGcDFVV3R3VjJGcmJ6QlZla1pYVmpGa2NsWnNTbGRTTTAwMQ==
```

Desifrandolo 8 veces nos arrojara la bandera:
```
flagMX{R3TURN_TH3_J4GUARS_EYES}
```