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

# Instación de Sql-Plus

1. Descomprimimos el archivo que hemos descargado, y accedemos a la carpeta **DISK1**, una vez dentro ejecutamos el archivo **setup**.

2. Una vez ejecutado daremos siguiente hasta que nos pida una _contraseña para la cuenta de SYSADMIN_, para esto introduciremos una contraseña que podemos recordar.

> Por ejemplo: **abcd1234**

3. Daremos a siguiente hasta finalizar.

Con esto ya tendremos instalado el **Sql-Plus**.

# Configuración del entorno

1. Descomprimimos el archivo de configuración automática, es recomendable colocar la carpeta resultante en una ubicación a la que podamos llegar facilmente, en este caso usaremos (`C:\` ).

2. Abriremos la consola de comandos, para esto buscaremos el programa **cmd**, una vez ejecutado buscaremos en la linea de comandos la carpeta con los archivos de configuración con el siguiente comando:

```bash
C:\>cd crea_tablas
```

> Recordemos que pusimos la carpeta en `C:\`

3. Una vez dentro de la carpeta ejecutamos el siguiente comando:

```bash
C:\crea_tablas>sqlplus "\as SYSDBA"

Este comando nos permite ejecutar la base de datos en modo administrador.
```

4. Una vez en modo administrador ya podremos cargar la configuración para nuestra base de datos con el siguiente comando:

```bash
    SQL>@creschema
```
5. Terminado este proceso debemos salir del modo administrador con el comando `exit` .

6. El archivo de configuración ya creo nuestro usuario y estableció una contraseña para él, accederemos entonces como usuarios a la base de datos con el siguiente comando:

```bash
    C:\sqlplus
```
7. Nos pedirá el nombre de usuario y contraseña, que en ambos casos sera "**clase**" (_sin comillas_).

8. Con esto ya tendremos el entorno listo para trabajar.

Espero que esta guía os sea de utilidad, saludos.


