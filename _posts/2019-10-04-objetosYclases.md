---
layout: post
name: Objetos y Clases en Java
asignatura: programacion
---


# Introducción

En la programación orientada a objetos, tenemos los como base fundamental los conceptos de objetos y clases. Ambos conceptos estan muy relacionados ya que un objeto no es mas que la representación de una clase.



## Usemos un ejemplo para entender mejor la idea

Supongamos una clase como el plano de un coche

<img src = "{{site.baseurl}}/assets/recursos/java_objetos/car_bluePrint.png" width = "350">

El plano se comporta como una imagen conceptual de lo que será el coche, informáticamente hablando, estamos en un **nivel de abstraccion alto** debido a que, cosas como el color y la marca, no las tenemos en cuenta en este momento. Lo que si consideramos es que, independientemente de las caracteristicas físicas que pueda tener el coche, todos comparten **funciones** básicas, como por ejemplo, el que hecho de que pueda arrancar, avanzar, retroceder, etc.

Una vez tenemos clara la imagen de un coche, podemos proceder a fabricar uno ( o varios ), cada uno con características diferentes, pero **sin dejar de ser coches**

Podriamos entonces fabricar un _Porshe Rojo_

<img src="{{site.baseurl}}/assets/recursos/java_objetos/deportivo_rojo.jpg" width="350">

O bien fabricar un _Honda deportivo Blanco_

<img src = "{{site.baseurl}}/assets/recursos/java_objetos/deportivo_blanco.jpg" width="350">

Entonces, ahora podemos entender al _plano del coche_ como la **clase coche** y al _Porshe rojo_ como un **objeto de la clase coche**

> Los objetos tambien son llamados **instancias** en algunos casos pero vienen a ser lo mismo.


## Concepto aplicado a Java


Java es un lenguaje de programación orientado a objetos, quiere decir que en este lenguaje, partiendo de una **clase** crearemos los **objetos** necesarios o bien crearemos **nuestras clases propias** para crear objetos que se **ajusten a nuestras necesidades.**

### Clases en Java
---

Como ya hemos visto las clases son como la **plantilla** de la cual parten los objetos.

Las clases en Java tienen 2 zonas de código muy diferenciadas. Esta la zona de **atributos** del objeto, y la zona de **métodos** de objeto.

En la primera se declaran los atributos que poseera dicho objeto, y es en esta parte, en la que los objetos pueden **diferenciarse unos de otros**, ya que cada uno tendrá sus propios atributos como vimos con los coches.

En la segunda se declaran métodos que tendrá el objeto, todos los objetos creados a partir de esta clase compartirán los mismos métodos, debido a esto, es que pueden identificarse como objetos de la misma clase.  

### Palabra reservada this
---

La palabra reservada **this** sirve para referenciar al objeto en si mismo (tambien podemos no usarla, pero no es una buena práctica.

Usando **this** podemos referenciar a los atributos de la clase de una forma **clara** y asi evitar confusiones con otras variables que podrían tener el mismo nombre que los atributos.

### Funciones void y funciones con return
---

En Java tenemos dos tipos de funciones, las que no devuelven nada y solo efectúan cambios a nivel de código y las que devuelven una variable para ser usada posteriormente.

- Funciones **void** : Son las funciones que no devuelven nada, como su nombre dice son **vacías**, su sintaxis es:

    ```java
    public void <nombreMétodo>(){
        // código
    }
    ```
- Funciones con **return** : Son funciones que devuelven valores para su uso en otras partes de nuestro código, un claro ejemplo de esto es la función ```Math.random();``` que devuelve un número aleatorio, que podremos usar como dato para otras funciones, su sintaxis es:

    ```java
    public <tipoRetorno> <nombreMétodo>(){
        // código

        return <variableRetorno>;
    }
    ```
    Debemos especificar el tipo de dato que devolvera (int, String, double, etc) en la cabecera de la función (tipoRetorno).


**Ahora crearemos la clase coche para ilustrar mejor la idea.**

```java
public class Coche{

    //Zona de declaración de atributos

    public String marca; // Los atributos no se inicializan en la clase.
    public String color;

    //Zona de declaracón de métodos

    public void arrancar(){
        System.out.println("El coche ha arrancado");
    }

    public void avanzar(){
        System.out.println("El coche avanza a una velocidad constante");
    }

    public void acelerar(){
        System.out.println("El coche acelera");
    }
    
    
    public void apagar(){
        System.out.println("El coche se ha apagado");
    }

    //Usamos la palabra reservada this para devolver el color

    public String dimeColor(){ // El método/función devuelve un String
        return this.color;  
    }
    
}
```

### Objetos en Java
---
Teniendo la clase coche creada, tendremos dos opciones para crear un objeto de esta clase:

- Podemos crear un clase main dentro de la clase coche: 

    ```java
    public static void main(String [] args){

    }
    ```

    Java utiliza el método **main** como función principal de ejecución, es decir, que cuando ejecutamos nuestro código, Java buscará el método main para proceder de acuerdo al código que contenga.

- O podemos crear _otro_ archivo **.java** que solo contenga el método **main** e **importar** la clase coche en este archivo.

    ```java
    import coche;
    ```

    > Si no importamos la clase cuando intentamos crear un objeto de la misma en un archivo ```.java``` difenrente al que contiene la clase, nos dara un **error**, ya que, no Java no sabe dónde se encuentra dicha clase.

Como vemos, en cualquier caso necesitaremos el método main para ejecutar nuestro código.

En este caso optaremos por crear el método main dentro de la clase **coche**.

Para la creación de un objeto, utilizaremos la paralabra reservada **new**, con esto, crearemos el espacio en memoria para el objeto:

```java
<nombreClase> <nombreVariable> = new <nombreClase>();
```

A continuación asignaremos los atributos para el objeto, utilizando la siguiente sintaxis:

```java
<nombreVaribale>.<nombreAtributo> = <valor>;
```

Para utilizar los métodos de la clase, usaremos la siguiente sintaxis:

```java
<nombreVariable>.<nombreMétodo>();
```
Ampliaremos entonces el ejemplo de coche para entender mejor el concepto:

```java
public class Coche{

    //Zona de declaración de atributos

    public String marca; // Los atributos no se inicializan en la clase.
    public String color;

    //Zona de declaracón de métodos

    public void arrancar(){
        System.out.println("El coche ha arrancado");
    }

    public void avanzar(){
        System.out.println("El coche avanza a una velocidad constante");
    }

    public void acelerar(){
        System.out.println("El coche acelera");
    }
    
    
    public void apagar(){
        System.out.println("El coche se ha apagado");
    }

    public String dimeColor(){
        return this.color;
    }

    // MÉTODO MAIN

    public static void main (String [] args){
        Coche coche1 = new Coche(); //Creamos el objeto

        //definimos atributos
        coche1.marca = "Porshe";
        coche1.color = "rojo";

        //Utilizamos los métodos

        coche1.arrancar(); //Este método nos mostrará en pantalla un mensaje.
        coche1.avanzar(); //Este método nos mostrará en pantalla un mensaje.

    }
    
}
```
### Constructores en Java
---

Inicializar los atributos de la forma vista anteriormente no es una buena práctica, ya que para esto Java nos permite la creación de un **método constructor**, con el cual definiremos los atributos en el momento de la creación del objeto.

El constructor recibe como parametros de función los datos para los atributos:

> IMPORTANTE: El método **constructor** debe tener **el mismo nombre que la clase**.

```java
public <nombreClase>(<tipo> <nombreVariable1>, <tipo> <nombreVariable2>, ...){
    this.<nombreAtributo1> = <nombreVariable1>;
    this.<nombreAtributo2> = <nombreVaribale2>;
}
```

Aplicando esto a nuestra clase coche, el código quedaría de esta forma:

```java
public class Coche{

    //Zona de declaración de atributos

    public String marca; // Los atributos no se inicializan en la clase.
    public String color;


    // CONSTRUCTOR

    public Coche(String var1, String var2){
        this.marca = var1; //asignamos las entradas a los atributos.
        this.color = var2;
    }


    //Zona de declaracón de métodos

    public void arrancar(){
        System.out.println("El coche ha arrancado");
    }

    public void avanzar(){
        System.out.println("El coche avanza a una velocidad constante");
    }

    public void acelerar(){
        System.out.println("El coche acelera");
    }
    
    
    public void apagar(){
        System.out.println("El coche se ha apagado");
    }

    public String dimeColor(){
        return this.color;
    }

    // MÉTODO MAIN

    public static void main (String [] args){
        
        //Creamos el objeto usando el construcor.

        Coche coche1 = new Coche("Porshe", "rojo");
        
        // De esta forma asignamos los atributos al crear el objeto.

        //UTILIZAMOS LOS MÉTODOS

        coche1.arrancar(); //Este método nos mostrará en pantalla un mensaje.
        coche1.avanzar(); //Este método nos mostrará en pantalla un mensaje.

    }
    
}
```

Espero que esta "guía" les haya aclarado un poco mas las cosas.







