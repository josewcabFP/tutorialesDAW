---
layout: post
name: Cambiar la carpeta por defecto del servidor apache
asignatura: sistemas
---


# Introducción

Normalmente al instalar apache2 tenemos una carpeta **por defecto** para colocar los archivos de nuestra página web. Este archivo se encuentra en:

```bash
/var/www/html
```

En esta guía veremos como cambiar esta ruta a una personalizada. Para nuestro ejemplo usaremos la ruta /home/daw1/web

Para este fin seguiremos los siguientes pasos:

1. Iremos a la carpeta que contiene el archivo de configuración de nuestro sitio **por defecto**, normalmente el comando sera:

    ```bash
    cd /etc/apache2/sites-avaiable
    ```

2. Una vez alli haremos una copia del archivo de configuración para crear el nuestro a partir de este:

    ```bash
    sudo cp 000-default.conf mi-sitio.conf
    ```

3. A continuación editaremos el archivo copia, en este caso **" mi-sitio.conf "**:

    ```bash
    sudo nano mi-sitio.conf
    ```

4. Una vez dentro borraremos la linea :

    ```bash
    DocumentRoot /var/www/html
    ```

    Y la cambiaremos por:

    ```bash
    DocumentRoot /home/daw1/web
    ```

    Por utlimo añadiremos estas lineas extra:

    ```bash
    <Directory /home/daw1/web>
    Require all granted
    </Directory>
    ```
    Guardamos los cambios.

5. Ahora debemos decirle a **apache** que el archivo de configuración de nuestra página sera el nuevo archivo, para esto usarmos los comandos **a2dissite** y **a2ensite**:

    ```bash
    sudo a2dissite 000-default && sudo a2ensite mi-sitio
    ```

> **a2dissite** : Sirve para decirle al servidor apache que daremos de baja al archvio de configuracion dado.  

> **a2ensite** : Sirve para decirle al servidor apache que daremos de alta al archivo de configuración dado.

> **&&** : AND lógico ejecutara el comando de la derecha, solo si se a ejecutado satisfactoriamente el comando de la izquierda

6. Por último reiniciaremos el servicio apache2:

    ```bash
     sudo service apache2 reload
    ```

