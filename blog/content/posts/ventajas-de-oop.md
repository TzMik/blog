---
draft: false
date: 2023-03-24T15:31:09-06:00
title: "Ventajas de la Programación Orientada a Objetos"
description: "En este post veremos las 4 principales ventajas de la programación orientada a objetos"
slug: "ventajas-de-la-programacion-orientada-a-objetos"
authors: ["Mikel Cantero"]
tags: ["programación orientada a objetos", "programación"]
categories: ["programación orientada a objetos"]
---

En la actualidad la Programación Orientada a Objetos se ha vuelto una especie de estandar en la industria. En este post veremos brevemente las principales 4 razones detrás de esto:

## La encapsulación

La encapsulación es uno de los cuatro conceptos fundamentales de la programación orientada a objetos (POO). Se refiere a la técnica de __ocultar la complejidad interna de un objeto__, permitiendo que sólo se acceda a él a través de una interfaz pública, que está formada por los métodos y propiedades que el objeto expone para su uso por parte de otros objetos.

En otras palabras, la encapsulación es el proceso de __envolver los datos y los métodos que operan sobre ellos dentro de una sola entidad__, lo que permite que estos datos sean __protegidos y manipulados de manera controlada__. Al encapsular los datos dentro de un objeto, se asegura que sólo puedan ser accedidos y modificados por los métodos que se han definido para ello.

Por ejemplo, supongamos que estamos creando una clase de *Cuenta Bancaria* en una aplicación orientada a objetos. En este caso, podríamos encapsular los detalles de la cuenta (como el número de cuenta, el saldo, etc.) dentro de la clase, y exponer métodos públicos para depositar y retirar dinero, consultar el saldo, etc. Esto significa que cualquier otra parte del código que necesite acceder a los datos de la cuenta deberá hacerlo a través de los métodos públicos de la clase, lo que asegura que los datos sólo sean manipulados de acuerdo a las reglas definidas en la clase.

Por ejemplo, podríamos definir una clase `CuentaBancaria` como sigue:
```php
class CuentaBancaria {
    private $numeroCuenta;
    private $saldo;

    public function depositar($cantidad) {
        // ... lógica para depositar la cantidad en la cuenta ...
    }

    public function retirar($cantidad) {
        // ... lógica para retirar la cantidad de la cuenta ...
    }

    public function consultarSaldo() {
        // ... lógica para obtener el saldo actual de la cuenta ...
    }
}
```

En este ejemplo, la clase `CuentaBancaria` encapsula los detalles de la cuenta, como el número de cuenta y el saldo, dentro de la clase, y expone métodos públicos para depositar y retirar dinero, así como para consultar el saldo actual. Al hacerlo, aseguramos que cualquier otra parte del código que necesite acceder a los datos de la cuenta lo haga a través de estos métodos públicos, lo que nos permite controlar cómo se accede y se manipula la cuenta.

## Abstracción
La abstracción en programación orientada a objetos es el proceso de **enfocarse en las características esenciales de un objeto y dejar de lado los detalles menos importantes**. Es decir, la abstracción permite representar un objeto de manera **simplificada**, seleccionando únicamente las propiedades y métodos que son relevantes para la tarea que se quiere realizar.

Una de las principales ventajas de la abstracción es que permite crear objetos **más fáciles de entender y manejar**, ya que se simplifica su complejidad al **ocultar los detalles que no son necesarios** en un momento dado. Además, la abstracción permite crear **interfaces más limpias y cohesivas** entre los diferentes objetos, lo que facilita la integración y el mantenimiento del código.

Un ejemplo de abstracción en PHP podría ser una clase abstracta que defina una forma básica de un objeto. Supongamos que estamos creando un programa de dibujo y queremos crear diferentes formas para dibujar. Podríamos crear una clase abstracta llamada `Forma` que defina propiedades y métodos básicos, como el color, la posición y el tamaño de la forma, así como un método abstracto `dibujar` que cada forma específica tendría que implementar.

```php
abstract class Forma {
  protected $color;
  protected $posicion;
  protected $tamano;
  
  public function __construct($color, $posicion, $tamano) {
    $this->color = $color;
    $this->posicion = $posicion;
    $this->tamano = $tamano;
  }
  
  abstract public function dibujar();
}
```
Luego, podríamos crear diferentes clases que extiendan la clase abstracta `Forma`, como por ejemplo una clase `Rectangulo` o una clase `Circulo`, que definirían sus propias implementaciones del método `dibujar`. De esta manera, cada forma específica tiene acceso a las propiedades y métodos básicos definidos en la clase abstracta `Forma`, pero también puede personalizar y añadir su propia funcionalidad específica.

```php
class Rectangulo extends Forma {
  public function dibujar() {
    // Implementación específica para dibujar un rectángulo
  }
}

class Circulo extends Forma {
  public function dibujar() {
    // Implementación específica para dibujar un círculo
  }
}
```

Al utilizar la abstracción en este ejemplo, se consigue que las formas sean más fáciles de entender y manejar, ya que se definen las propiedades y métodos básicos necesarios para todas las formas, pero se ocultan los detalles específicos de cada una. Además, se consigue una interfaz más limpia y cohesiva entre los diferentes objetos, lo que facilita la integración y el mantenimiento del código.

## Herencia
La herencia es un concepto fundamental en la programación orientada a objetos que **permite crear nuevas clases a partir de clases existentes**. En la herencia, una clase (llamada clase hija o subclase) puede heredar propiedades y métodos de otra clase (llamada clase padre o superclase). **La clase hija puede utilizar y añadir a las propiedades y métodos de la clase padre, y además puede definir sus propias propiedades y métodos adicionales**.

Las ventajas de la herencia son varias. En primer lugar, la herencia permite la **reutilización de código**, lo que significa que las clases hijas pueden heredar el código de la clase padre y así no se tiene que escribir el mismo código una y otra vez. En segundo lugar, la herencia puede **mejorar la organización del código**, ya que las clases hijas pueden agruparse en una jerarquía de clases que refleje su relación. Por último, la herencia puede mejorar la **flexibilidad del código**, ya que se puede cambiar el comportamiento de una clase hija al modificar la clase padre, lo que permite adaptar el código a diferentes situaciones.

Un ejemplo sencillo de herencia en PHP podría ser una clase `Vehiculo` que define propiedades y métodos comunes para todos los vehículos, como la velocidad, la dirección, el combustible, etc. Luego, podríamos crear una clase hija `Automovil` que hereda de `Vehiculo` y que añade propiedades y métodos específicos para los automóviles, como la marca, el modelo, el número de puertas, etc. De esta manera, la clase `Automovil` puede utilizar y añadir a las propiedades y métodos de `Vehiculo`, pero también puede definir sus propias propiedades y métodos.

```php
class Vehiculo {
  protected $velocidad;
  protected $direccion;
  protected $combustible;
  
  public function acelerar($aceleracion) {
    // Implementación para aumentar la velocidad del vehículo
  }
  
  public function girar($direccion) {
    // Implementación para cambiar la dirección del vehículo
  }
  
  public function cargarCombustible($cantidad) {
    // Implementación para añadir combustible al vehículo
  }
}

class Automovil extends Vehiculo {
  protected $marca;
  protected $modelo;
  protected $numeroPuertas;
  
  public function abrirPuertas() {
    // Implementación para abrir las puertas del automóvil
  }
  
  public function cambiarRadio($emisora) {
    // Implementación para cambiar la emisora de la radio del automóvil
  }
}
```
En este ejemplo, la clase `Automovil` hereda propiedades y métodos de la clase `Vehiculo`, y además define sus propias propiedades y métodos adicionales. Esto permite reutilizar el código de la clase `Vehiculo` para la clase `Automovil` y definir el comportamiento específico de los automóviles en la clase `Automovil`.

## Polimorfismo
El polimorfismo es uno de los conceptos fundamentales de la programación orientada a objetos. Se refiere a la **capacidad de un objeto de una clase para comportarse como otro objeto de una clase relacionada**.

En términos simples, el polimorfismo **permite que múltiples objetos de diferentes clases respondan a una misma acción o método de manera distinta**. Esto significa que un objeto puede tomar muchas formas o *polimorfismos* y cada forma puede realizar una tarea diferente.

Las principales ventajas del polimorfismo en la programación orientada a objetos son:

1. **Reutilización de código:** El polimorfismo permite a las clases compartir el mismo método, lo que significa que no es necesario escribir código repetitivo.

2. **Flexibilidad:** El polimorfismo permite que los objetos sean más flexibles y adaptables a diferentes situaciones y requisitos de programación.

3. **Mantenibilidad:** El polimorfismo hace que el código sea más fácil de mantener y modificar, ya que los cambios en una clase no afectan a otras clases relacionadas.

4. **Facilita la implementación de patrones de diseño:** El polimorfismo es una técnica importante en la implementación de patrones de diseño, que son soluciones probadas y comprobadas a problemas comunes en la programación orientada a objetos.

Aquí hay un ejemplo de polimorfismo en PHP:
```php
class Animal {
  public function makeSound() {
    echo "Animal is making a sound";
  }
}

class Dog extends Animal {
  public function makeSound() {
    echo "Dog is barking";
  }
}

class Cat extends Animal {
  public function makeSound() {
    echo "Cat is meowing";
  }
}

$animal1 = new Animal();
$animal1->makeSound(); // Output: "Animal is making a sound"

$animal2 = new Dog();
$animal2->makeSound(); // Output: "Dog is barking"

$animal3 = new Cat();
$animal3->makeSound(); // Output: "Cat is meowing"
```
En este ejemplo, la clase Animal tiene un método `makeSound()` que se sobrescribe en las subclases `Dog` y `Cat`. Al crear instancias de cada una de las subclases y llamar al método `makeSound()`, cada objeto muestra su propio comportamiento, lo que demuestra el polimorfismo.