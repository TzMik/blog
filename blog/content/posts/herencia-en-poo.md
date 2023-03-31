+++ 
draft = false
date = 2023-03-31T11:48:53-06:00
title = "La herencia en la Programación Orientada a Objetos"
description = "La herencia es un concepto muy importante y una de las fortalezas más útiles de la POO. En este post veremos para qué y cómo utilizarla"
slug = "herencia-en-la-poo"
authors = ["Mikel Cantero", "Chat GPT"]
tags = ["php", "programación orientada a objetos", "herencia"]
categories = ["programación orientada a objetos"]
externalLink = ""
series = []
+++

La herencia es un concepto fundamental en la programación orientada a objetos. En este post, exploraremos las ventajas y desventajas de la herencia en PHP, las diferencias entre las variables públicas, privadas y protegidas, la sobreescritura de métodos y variables en una clase hija, y los métodos y clases de tipo final.

## Introducción
La herencia es uno de los conceptos fundamentales de la programación orientada a objetos. En términos simples, permite a una clase derivar características y comportamientos de otra clase existente, llamada clase base o superclase (padre). La nueva clase que deriva de la clase base se conoce como clase derivada o subclase (hija).

La herencia es una técnica de reutilización de código que permite a los programadores crear nuevas clases basadas en clases ya existentes, sin tener que reescribir todo el código nuevamente. Al heredar de una clase base, la subclase hereda todas sus propiedades públicas y protegidas, así como sus métodos. La subclase también puede agregar sus propias propiedades y métodos o incluso sobrescribir los métodos existentes de la clase base para personalizar su comportamiento.

Por lo tanto, es una herramienta poderosa en la programación orientada a objetos que permite a los programadores crear jerarquías de clases bien organizadas y coherentes. Sin embargo, también puede introducir complejidad y acoplamiento en el código si no se utiliza con cuidado. Por lo tanto, es importante comprender las ventajas y desventajas de la herencia y cómo utilizarla adecuadamente en el diseño de software.

## Ventajas y desventajas
Ventajas de la herencia en PHP:

1. **Reutilización de código:** La herencia permite reutilizar el código existente de una clase en otra clase, lo que puede ahorrar tiempo y esfuerzo en la programación.

2. **Facilita el mantenimiento del código:** La herencia puede simplificar el mantenimiento del código al permitir que se realicen cambios en una clase base que se aplican automáticamente a todas las clases derivadas.

3. **Promueve la coherencia en el código:** Al compartir propiedades y métodos comunes, la herencia puede ayudar a mantener la coherencia en el código y reducir la complejidad.

Desventajas de la herencia en PHP:

1. **Aumenta la complejidad:** A medida que aumenta el número de clases derivadas, puede ser más difícil entender cómo se relacionan entre sí y cómo se heredan las propiedades y métodos.

2. **Introduce acoplamiento:** La herencia puede introducir acoplamiento entre las clases, lo que puede hacer que sea más difícil cambiar o reutilizar el código.

3. **Puede requerir una planificación cuidadosa:** La herencia puede requerir una planificación cuidadosa para asegurarse de que las clases derivadas se comporten de la manera deseada y que se eviten los conflictos.

## Diferencias entre variables públicas, privadas y protegidas

En PHP, las variables se pueden declarar como públicas, privadas o protegidas. Una variable pública se puede acceder desde cualquier lugar, una variable privada solo se puede acceder desde la propia clase, y una variable protegida se puede acceder desde la propia clase y las clases derivadas.

```php
class Padre {
  public $variable_publica = 'Variable pública';
  private $variable_privada = 'Variable privada';
  protected $variable_protegida = 'Variable protegida';
}

class Hijo extends Padre {
  public function mostrarVariables() {
    echo $this->variable_publica . "<br>";
    // Error: La variable privada no se puede acceder desde una clase hija
    //echo $this->variable_privada . "<br>";
    echo $this->variable_protegida . "<br>";
  }
}

$objeto = new Hijo();
$objeto->mostrarVariables();
```

## Sobreescritura de métodos y variables en una clase hija

En PHP, una clase hija puede sobrescribir un método o variable definido en una clase base. Esto permite personalizar el comportamiento de la clase hija sin modificar la clase base.

```php
class Padre {
  public $variable = 'Variable de la clase padre';

  public function saludar() {
    echo "Hola desde la clase padre <br>";
  }
}

class Hijo extends Padre {
  public $variable = 'Variable de la clase hijo';

  public function saludar() {
    echo "Hola desde la clase hijo <br>";
  }
}

$objeto = new Hijo();
echo $objeto->variable . "<br>"; // Imprime "Variable de la clase hijo"
$objeto
echo $objeto->saludar(); // Imprime "Hola desde la clase hijo"
```

## Métodos y clases de tipo final

En PHP, se pueden declarar métodos y clases como final para evitar que se sobrescriban en clases derivadas. Esto puede ser útil para evitar que se modifique el comportamiento de una clase base en formas que no se esperan.

```php
class Padre {
  public final function saludar() {
    echo "Hola desde la clase padre <br>";
  }
}

class Hijo extends Padre {
  // Error: No se puede sobrescribir un método final
  //public function saludar() {
  //  echo "Hola desde la clase hijo <br>";
  //}
}

$objeto = new Hijo();
echo $objeto->saludar(); // Imprime "Hola desde la clase padre"
```

## Coclusión
En resumen, la herencia es una herramienta poderosa en la programación orientada a objetos que permite reutilizar el código existente y promover la coherencia en el código. Sin embargo, también puede introducir complejidad y acoplamiento en el código si no se utiliza con cuidado. Las variables públicas, privadas y protegidas permiten controlar el acceso a las variables en una clase y en las clases derivadas. La sobreescritura de métodos y variables en una clase hija permite personalizar el comportamiento de la clase hija sin modificar la clase base. Los métodos y clases de tipo final permiten evitar la sobrescritura y extensión de clases y métodos en formas que no se esperan.
