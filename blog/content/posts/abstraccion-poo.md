+++ 
draft = false
date = 2023-03-31T12:08:53-06:00
title = "La abstracción en la POO"
description = "En este post veremos qué es y para qué sirve la abstracción en la Programación Orientada a Objetos"
slug = "abstraccion-en-la-poo"
authors = ["Mikel Cantero", "Chat GPT"]
tags = ["programación orientada a objetos", "php", "abstracción"]
categories = ["programación orientada a objetos"]
externalLink = ""
series = []
+++

La abstracción es uno de los conceptos fundamentales de la programación orientada a objetos (POO). En términos simples, la abstracción es la capacidad de centrarse en los aspectos esenciales de un objeto o concepto y eliminar los detalles innecesarios o irrelevantes. La abstracción permite a los programadores diseñar sistemas complejos de manera más efectiva, simplificando la complejidad y promoviendo la modularidad y la reutilización de código.

## Ventajas y desventajas
La abstracción tiene varias ventajas en la POO:

1. **Simplificación de la complejidad:** La abstracción permite a los programadores enfocarse en los aspectos esenciales de un objeto o concepto, eliminando los detalles innecesarios y la complejidad. Esto hace que el diseño de sistemas complejos sea más manejable y más fácil de entender y mantener.

2. **Promoción de la modularidad y la reutilización de código:** La abstracción promueve la modularidad del código, lo que significa que el código se divide en componentes más pequeños y autónomos que pueden reutilizarse en diferentes partes del sistema. Esto reduce la duplicación de código y facilita la implementación y mantenimiento de sistemas complejos.

3. **Mejora de la eficiencia y la eficacia:** La abstracción puede mejorar la eficiencia y la eficacia de la programación al permitir a los programadores centrarse en los aspectos más importantes de un problema y diseñar soluciones más efectivas y elegantes. Esto puede reducir el tiempo y los recursos necesarios para desarrollar y mantener el software.

4. **Reducción de errores:** La abstracción puede ayudar a reducir los errores en el software al permitir a los programadores enfocarse en los aspectos más importantes de un problema y reducir la complejidad y la ambigüedad del código. Esto puede hacer que el software sea más fácil de probar, depurar y mantener.

Aunque la abstracción tiene muchas ventajas, también tiene algunas desventajas potenciales:

1. **Mayor complejidad:** A veces, la abstracción puede aumentar la complejidad del software al introducir abstracciones innecesarias o mal diseñadas. Esto puede hacer que el software sea más difícil de entender y mantener.

2. **Mayor sobrecarga:** La abstracción puede introducir una sobrecarga adicional en el software debido a la necesidad de definir e implementar interfaces y abstracciones adicionales. Esto puede aumentar la complejidad y el costo de desarrollo y mantenimiento del software.

3. **Pérdida de detalle:** La abstracción puede implicar la pérdida de detalles importantes de un objeto o concepto, lo que puede hacer que el software sea menos preciso o menos completo en algunos aspectos.

## Ejemplo con PHP
Un ejemplo común de abstracción en la POO es el uso de clases abstractas e interfaces para definir abstracciones comunes que se utilizan en diferentes partes del sistema. Una clase abstracta es una clase que no se puede instanciar directamente y que define métodos que deben implementarse en las clases hijas. Una interfaz es una colección de métodos que se utilizan como una especificación para las clases que las implementan.

Por ejemplo, supongamos que queremos diseñar un sistema de comercio electrónico que incluya diferentes tipos de productos, como libros, electrónica y ropa. En lugar de diseñar una clase para cada tipo de producto, podemos definir una clase abstracta "Producto" que contiene propiedades y métodos comunes a todos los productos, como el precio y la descripción del producto.

```php
abstract class Producto {
    protected $precio;
    protected $descripcion;

    public function getPrecio() {
        return $this->precio;
    }

    public function setPrecio($precio) {
        $this->precio = $precio;
    }

    public function getDescripcion() {
        return $this->descripcion;
    }

    public function setDescripcion($descripcion) {
        $this->descripcion = $descripcion;
    }

    abstract public function calcularImpuesto();
}
```

En este ejemplo, la clase abstracta "Producto" define dos propiedades protegidas, "precio" y "descripcion", y dos métodos públicos para obtener y establecer estos valores. También define un método abstracto "calcularImpuesto" que debe ser implementado en las clases hijas.

Ahora, podemos definir clases hijas para cada tipo de producto, como "Libro", "Electronica" y "Ropa", que heredan de la clase abstracta "Producto" y proporcionan implementaciones específicas para el método "calcularImpuesto". Por ejemplo:
```php
class Libro extends Producto {
    public function calcularImpuesto() {
        // calcular impuesto específico para libros
    }
}

class Electronica extends Producto {
    public function calcularImpuesto() {
        // calcular impuesto específico para electrónica
    }
}

class Ropa extends Producto {
    public function calcularImpuesto() {
        // calcular impuesto específico para ropa
    }
}
```
En este ejemplo, cada clase hija proporciona una implementación específica para el método "calcularImpuesto", pero hereda las propiedades y los métodos comunes de la clase abstracta "Producto". Esto permite una mayor modularidad y reutilización de código en nuestro sistema de comercio electrónico.

## Conclusión
En resumen, la abstracción es un concepto fundamental de la POO que permite a los programadores centrarse en los aspectos esenciales de un objeto o concepto y eliminar los detalles innecesarios o irrelevantes. La abstracción tiene varias ventajas, como la simplificación de la complejidad, la promoción de la modularidad y la reutilización de código, la mejora de la eficiencia y la eficacia, y la reducción de errores en el software. Sin embargo, también tiene algunas desventajas potenciales, como la mayor complejidad, la mayor sobrecarga y la pérdida de detalle.
