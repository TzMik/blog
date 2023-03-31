+++ 
draft = false
date = 2023-03-31T10:45:34-06:00
title = "Magic Methods de PHP"
description = "En este post veremos los métodos especiales denominados magic methods de PHP"
slug = "magic-methods-de-php"
authors = ["Mikel Cantero", "Chat GPT"]
tags = ["php", "programación orientada a objetos"]
categories = ["programación orientada a objetos", "php"]
externalLink = ""
series = []
+++

En PHP, existen varios métodos especiales llamados *magic methods* que permiten a los desarrolladores personalizar el comportamiento de las clases y objetos. Estos métodos se llaman automáticamente en ciertas situaciones específicas, como cuando se accede a una propiedad inexistente, se llama a un método inexistente, o se convierte un objeto en una cadena de texto, entre otras.

A continuación, se explicará cada uno de estos métodos especiales de PHP, junto con ejemplos que muestran cómo se pueden utilizar.

1. **`__toString()`**: Este método se llama cuando se intenta convertir un objeto en una cadena de texto. El método debe devolver una cadena que represente el objeto de la forma deseada. Este método es útil para proporcionar una representación legible de un objeto.

Ejemplo:
```php
class Persona {
  public $nombre;
  public $edad;

  public function __construct($nombre, $edad) {
    $this->nombre = $nombre;
    $this->edad = $edad;
  }

  public function __toString() {
    return "Mi nombre es " . $this->nombre . " y tengo " . $this->edad . " años.";
  }
}

$persona = new Persona("Juan", 25);
echo $persona; // Imprime "Mi nombre es Juan y tengo 25 años."
```

2. **`__get()` y `__set()`**: Estos métodos se llaman cuando se intenta acceder a una propiedad inexistente o se intenta asignar un valor a una propiedad inexistente, respectivamente. El método `__get()` debe devolver el valor de la propiedad, mientras que el método `__set()` debe asignar el valor a la propiedad.

Ejemplo:
```php
class Persona {
  private $datos = [];

  public function __get($propiedad) {
    if (array_key_exists($propiedad, $this->datos)) {
      return $this->datos[$propiedad];
    } else {
      return null;
    }
  }

  public function __set($propiedad, $valor) {
    $this->datos[$propiedad] = $valor;
  }
}

$persona = new Persona();
$persona->nombre = "Juan";
$persona->edad = 25;

echo $persona->nombre; // Imprime "Juan"
echo $persona->apellido; // Imprime ""
```

3. **`__call()` y `__callStatic()`**: Estos métodos se llaman cuando se intenta llamar a un método inexistente. El método `__call()` se llama en una instancia de una clase, mientras que el método `__callStatic()` se llama en la propia clase.

Ejemplo:
```php
class Persona {
  public function __call($metodo, $argumentos) {
    if ($metodo == "saludar") {
      echo "Hola, " . $argumentos[0] . "!";
    }
  }

  public static function __callStatic($metodo, $argumentos) {
    if ($metodo == "despedir") {
      echo "Adiós, " . $argumentos[0] . "!";
    }
  }
}

$persona = new Persona();
$persona->saludar("Juan"); // Imprime "Hola, Juan!"

Persona::despedir("Juan"); // Imprime "Adiós, Juan!"
```

4. **`__invoke()`**: Este método se llama cuando se intenta llamar a un objeto como si fuera una función. El método debe devolver el resultado deseado de la llamada a la función.

Ejemplo:
```php
class Sumador {
  private $total = 0;

  public function __invoke($numero) {
    $this->total += $numero;
    return $this->total;
  }
}

$sumador = new Sumador();

echo $sumador(5); // Imprime 5
echo $sumador(10); // Imprime 15
```

5. **`__sleep()` y `__wakeup()`**: Estos métodos se llaman antes y después de que un objeto sea serializado. El método `__sleep()` debe devolver un array de las propiedades del objeto que se deben serializar, mientras que el método `__wakeup()` se llama después de que el objeto ha sido deserializado y se utiliza para realizar cualquier acción necesaria para restaurar el objeto a su estado anterior.

Ejemplo:
```php
class Persona {
  public $nombre;
  public $edad;

  public function __sleep() {
    return array('nombre', 'edad');
  }

  public function __wakeup() {
    echo "El objeto ha sido deserializado.";
  }
}

$persona = new Persona();
$persona->nombre = "Juan";
$persona->edad = 25;

$serializado = serialize($persona);

$persona2 = unserialize($serializado);
echo $persona2->nombre; // Imprime "Juan"
echo $persona2->edad; // Imprime "25"
// Imprime "El objeto ha sido deserializado."
```
(*) Para saber más sobre serilización y deserialización [visita el siguiente post](/posts/serializar-deserialiar-objetos).

6. **`__clone()`**: Este método se llama cuando se clona un objeto. El método debe realizar cualquier acción necesaria para preparar el objeto clonado.

Ejemplo:
```php
class Persona {
  public $nombre;
  public $edad;

  public function __clone() {
    $this->nombre = "Copia de " . $this->nombre;
  }
}

$persona1 = new Persona();
$persona1->nombre = "Juan";
$persona1->edad = 25;

$persona2 = clone $persona1;
echo $persona2->nombre; // Imprime "Copia de Juan"
echo $persona2->edad; // Imprime "25"
```

En resumen, estos métodos especiales de PHP son herramientas poderosas para personalizar el comportamiento de las clases y objetos en el lenguaje. Cada uno de ellos se llama automáticamente en una situación específica y puede ser utilizado para realizar acciones personalizadas en ese momento. Al conocer y comprender cómo funcionan estos métodos, los desarrolladores pueden crear código más flexible y potente en PHP.
