---
layout: post
title:  "Habilitar assert en Intellij IDEA"
category: Docs
tags: [java, unit-test, ide]
---

# Habilitar assert en Intellij IDEA
La palabra reservada **assert** permite establecer ciertas afirmaciones dentro de nuestro programa. Si la afirmacion falla se produce una excepción y puede mostrar un mensaje.

```java
public class Test {
    public static void main(String[] args) {
        assert args.length == 0: "No hay argumentos.";
    }
}
```
Sin embargo, por defecto assert no es ejecutado. Para permitir realizar estas afirmaciones es necesario en el momento de la ejecución utilizar el siguiente parametro:

```console
java -ea Test
```
Para realizarlo desde el IDE en esta caso desde Intellij IDEA se necesita lo siguiente:
1. Se abre la opción Run > Edit Configurations. En caso de no tener ninguna configuaciones se crea una. Eligiendo **Application**.
![Run/Debug Configuration](/assets/img/ea1.png)

2. Elige Modify options > Add VM options.
![VM Options](/assets/img/ea2.png)

3. En la caja de texto: VM options colocar *-ea*.
![VM Options](/assets/img/ea3.png)

Con esto ya es posible detectar la instrucción con asset, para ese build en particular. Si desea realizar en otro proyecto o en otro build, debe repetirse esta operación.