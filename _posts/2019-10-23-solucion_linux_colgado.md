---
layout: post
name: Solucionar un linux colgado (bloqueado)
asignatura: sistemas
---

# Introducción

> Esta guía esta hecha para una distribución linux, sin embargo, las soluciones son muy parecidas para otras distribuciones.

En algunas ocasiones (muy pocas) podemos tener un cuelgue de linux, sin embargo, a diferencia de windows, la solución de hacer un **hard reset** (presionar el boton de reset) puede tener consecuencias en nuestro sistema y en algunos casos la corrupción del disco, ya que, linux tiene una gestión distinta de los archivos y los procesos.

Para evitar este problema, cuando tengamos un cuelgue debemos seguir estos pasos:

## En el caso del cuelgue de un programa

1. Presionaremos la combinación de teclas &ensp;` alt + f2` &ensp; y escribiremos el comando &ensp; `gnome-system-monitor`&ensp;.

2. En la nueva ventana seleccionaremos el proceso y daremos a **finalizar proceso**.

## En el caso de cuelgue absoluto

1. Presionaremos la combinación de teclas &ensp; `Alt + Impr Paint PetSis` &ensp; y mientras mantenemos esas teclas pulsadas presionamos lentamente &ensp;`R`&ensp; `E`&ensp; `I`&ensp; `S`&ensp; `U`&ensp; `B`&ensp;.

2. Lo que hace cada tecla es:

    ```bash
    R - Pone el teclado en modo RAW.
    E - Termina todos los procesos.
    I - Mata todos los procesos.
    S - Sincroniza el disco duro.
    U - Desmonta los sistemas de ficheros.
    B - Reinicia el ordenador.
    ```


