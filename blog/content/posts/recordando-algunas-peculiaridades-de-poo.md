+++ 
draft = false
date = 2023-03-30T17:24:01-06:00
title = "Recordando conceptos de la POO"
description = "En este post hablaremos del constructor, destructor, de los métodos y variables estáticas y las constantes de una clase"
slug = "recordando-conceptos-de-la-poo"
authors = ["Mikel Cantero"]
tags = ["programación orientada a objetos", "constructor", "destructor", "static", "constantes", "php"]
categories = ["programación orientada a objetos"]
externalLink = ""
series = []
+++

La programación orientada a objetos (POO) es un paradigma de programación que se centra en el uso de objetos para representar entidades del mundo real y sus interacciones. En POO, los objetos son instancias de una clase, que es una plantilla que define las propiedades y comportamientos del objeto. En este contexto, existen algunos términos importantes que se utilizan con frecuencia y que me gustaría recordar, **como el constructor, destructor, static y constantes**. En este post educativo, hablaremos sobre estos términos en el contexto de la programación orientada a objetos y proporcionaremos ejemplos de su uso en PHP.

## Constructor

El constructor es un método especial de una clase que se utiliza para inicializar los objetos de esa clase. El constructor se llama automáticamente cuando se crea un objeto de la clase y se utiliza para asignar valores iniciales a las propiedades del objeto. En PHP, el constructor se define utilizando el método `__construct()`.

Ejemplo de constructor en PHP:
```php
class Persona {
    public $nombre;
    public $edad;

    public function __construct($nombre, $edad) {
        $this->nombre = $nombre;
        $this->edad = $edad;
    }
}

$persona = new Persona("Juan", 25);
echo $persona->nombre; // output: Juan
echo $persona->edad; // output: 25

```

En este ejemplo, el constructor de la clase Persona se utiliza para asignar los valores iniciales de `$nombre` y `$edad` al objeto `$persona`.

## Destructor

El destructor es un método especial de una clase que se utiliza para liberar los recursos utilizados por el objeto cuando ya no se necesita. El destructor se llama automáticamente cuando el objeto se destruye, ya sea porque se eliminó explícitamente o porque el programa ha terminado. En PHP, el destructor se define utilizando el método `__destruct()`.

Ejemplo de destructor en PHP:

```php
class Persona {
    public $nombre;
    public $edad;

    public function __construct($nombre, $edad) {
        $this->nombre = $nombre;
        $this->edad = $edad;
    }

    public function __destruct() {
        echo "Objeto eliminado.";
    }
}

$persona = new Persona("Juan", 25);
unset($persona); // Output: Objeto eliminado.
```
En este ejemplo, el destructor de la clase Persona se utiliza para mostrar un mensaje cuando el objeto se elimina explícitamente utilizando la función `unset()`.

## Static

La palabra clave static se utiliza para definir propiedades y métodos que pertenecen a la clase en sí, en lugar de pertenecer a un objeto de la clase. Las propiedades y métodos estáticos se pueden utilizar sin crear una instancia de la clase y se accede a ellas utilizando el nombre de la clase en lugar del objeto. En PHP, se define una propiedad estática utilizando la palabra clave `static` antes del nombre de la propiedad.

Ejemplo de propiedad estática en PHP:

```php
class Persona {
    public static $contador = 0;
    public $nombre;
    public $edad;

    public function __construct($nombre, $edad) {
        $this->nombre = $nombre;
        $this->edad = $edad;
        self::$contador++;
    }

    public static function getContador() {
        return self::$contador;
    }
}

$persona1 = new Persona("Juan", 25);
$persona2 = new Persona("Maria", 30);
echo Persona::getContador(); // output: 2
```
En este ejemplo, la propiedad `$contador` cuenta cuantas instancias de la clase `Persona` existen. En el constructor sumamos 1 al `$contador` cada vez que se crea una instancia de la calse `Persona` y con el método `getContador()` podemos imprimir el valor de ese contador.

## Constantes

Las constantes son valores que no pueden cambiarse una vez que se definen. En POO, las constantes se utilizan para definir valores que son importantes para la clase, pero que no cambian durante la ejecución del programa. En PHP, se define una constante utilizando la palabra reservada `const`.

Ejemplo de constante en PHP:
```php
class Persona {
    const ESPERANZA_VIDA = 80;

    public $nombre;
    public $edad;

    public function __construct($nombre, $edad) {
        $this->nombre = $nombre;
        $this->edad = $edad;
    }

    public function getEsperanzaVida() {
        return self::ESPERANZA_VIDA - $this->edad;
    }
}

$persona = new Persona("Juan", 25);
echo $persona->getEsperanzaVida(); // output: 55
```
En este ejemplo, la constante `ESPERANZA_VIDA` se utiliza para definir la esperanza de vida de una persona en años. La función `getEsperanzaVida()` se utiliza para calcular la esperanza de vida restante de una persona.

En resumen, en la programación orientada a objetos, el constructor se utiliza para inicializar los objetos de una clase, el destructor se utiliza para liberar los recursos utilizados por el objeto cuando ya no se necesita, las propiedades y métodos estáticos se utilizan para pertenecer a la clase en sí, en lugar de pertenecer a un objeto de la clase, y las constantes se utilizan para definir valores que son importantes para la clase, pero que no cambian durante la ejecución del programa.
