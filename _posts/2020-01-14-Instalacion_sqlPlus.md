---
layout: post
name: Instalación de Sql-Plus
asignatura: bases
---

> Nota: Esta guía esta hecha para una instalación en un entorno **windows**.

# Archivos previos

Antes de empezar debemos descargar los siguientes archivos:

- Programa de instalación de Sql-Plus, [Aquí](https://drive.google.com/file/d/1nNfBNswMoRg5OufCs6qOBlr1Hh1s7isq/view?usp=sharing)

- Archivos de configuración automática, [Aquí]({{site.baseurl}}/assets/recursos/SqlPlus_archivos/crea_tablas.rar)

# Instalación de Sql-Plus

- Descomprimimos el archivo que hemos descargado, y accedemos a la carpeta **DISK1**, una vez dentro ejecutamos el archivo **setup**.

- Una vez ejecutado daremos siguiente hasta que nos pida una _contraseña para la cuenta de SYSADMIN_, para esto introduciremos una contraseña que podemos recordar.

> Por ejemplo: **abcd1234**

- Daremos a siguiente hasta finalizar.

Con esto ya tendremos instalado el **Sql-Plus**.

# Configuración del entorno

- Descomprimimos el archivo de configuración automática, es recomendable colocar la carpeta resultante en una ubicación a la que podamos llegar facilmente, en este caso usaremos (`C:\` ).

- Abriremos la consola de comandos, para esto buscaremos el programa **cmd**, una vez ejecutado buscaremos en la linea de comandos la carpeta con los archivos de configuración con el siguiente comando:

```bash
C:\>cd crea_tablas
```

> Recordemos que pusimos la carpeta en `C:\`

- Una vez dentro de la carpeta ejecutamos el siguiente comando:

```bash
C:\crea_tablas>sqlplus "/as SYSDBA"

Este comando nos permite ejecutar la base de datos en modo administrador.
```

- Una vez en modo administrador ya podremos cargar la configuración para nuestra base de datos con el siguiente comando:

```bash
    SQL>@creschema
```
- Terminado este proceso debemos salir del modo administrador con el comando `exit` .

- El archivo de configuración ya creo nuestro usuario y estableció una contraseña para él, accederemos entonces como usuarios a la base de datos con el siguiente comando:

```bash
    C:\sqlplus
```
- Nos pedirá el nombre de usuario y contraseña, que en ambos casos sera "**clase**" (_sin comillas_).

- Con esto ya tendremos el entorno listo para trabajar.

Espero que esta guía os haya sido de utilidad, saludos.


