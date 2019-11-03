---
layout: post
name: Crear acceso directo a un programa en linux
asignatura: sistemas
---

# Introducción

Muchas veces en linux, cuando instalamos una nueva aplicación o bien cuando tenemos una aplicación propia, no tenemos la opción de crear un acceso directo a ella. En este tutorial veremos como solucionar este problema de una manera rápida y sencilla.

## La carpeta /usr/share/applications

Esta carpeta contiene los archivos de cada uno de los lanzadores de las aplicaciones en nuestro equipo. Para crear un nuevo acceso directo a alguna aplicación debemos guardar el lanzador en esta ubicación.

## Creando archivo lanzador

Debemos crear este archivo con extension **.desktop** para que sea reconocido, y dentro del archivo debemos escribir las siguientes lineas:

```bash
[Desktop Entry]

Name=Nombre del programa
Comment=Comentario sobre el programa
Exec=/home/usuario/carpetaPrograma/bin/programa
Icon=/home/usuario/Images/iconoPrograma
Terminal=false
Type=Application

```
**Veamos un ejemplo para ver mas claramente este concepto:**

Tengo un Shell Script llamado `programa.sh` el cual ejecuto a menudo con el comando `sudo ./programa.sh` por lo que quiero crear un acceso directo a él (estos pasos pueden valer para cualquier tipo de aplicacción).

1. Creo mi entrada de lanzador en la carpeta **applications**

    ```bash
    sudo nano /usr/share/applications/programa.desktop
    ```
2. Dentro del archivo escribo la configuración del lanzador:

    ```bash
    [Desktop Entry]
    
    Name=Programa
    Comment=Ejecuta mi programa personal
    Exec=/home/jose/MisProgramas/programa.sh
    Icon=/home/jose/Images/iconoPrograma.png
    Terminal=false
    Type=Application
    ```


    Podemos poner `Terminal=true` solo si queremos ejecutar algo como super usuario.