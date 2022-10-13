# SQL Direct
Connect to this PostgreSQL server and find the flag!

Hints:
- What does a SQL database contain?

## Solución
Primero intentamos conectarnos a la base de datos.

``` bash
holiwiscach@ubuntu:~/Escritorio/Seguridad/notas-hacking$ psql -h saturn.picoctf.net -p 62683 -U postgres pico
Password for user postgres: 
psql (14.5 (Ubuntu 14.5-0ubuntu0.22.04.1), server 14.2 (Debian 14.2-1.pgdg110+1))
Type "help" for help.

pico=#
```

Desplegamos todas las tablas que contiene la base de datos con **\d** 

``` bash
pico-# \d
         List of relations
 Schema | Name  | Type  |  Owner   
--------+-------+-------+----------
 public | flags | table | postgres
(1 row)

```

Seleccionamos la tabla flags y que muestre todos datos.

``` bash
pico=# select * from flags;
 id | firstname | lastname  |                address                 
----+-----------+-----------+----------------------------------------
  1 | Luke      | Skywalker | picoCTF{L3arN_S0m3_5qL_t0d4Y_31fd14c0}
  2 | Leia      | Organa    | Alderaan
  3 | Han       | Solo      | Corellia
(3 rows)


```

bandera:
picoCTF{L3arN_S0m3_5qL_t0d4Y_31fd14c0}
