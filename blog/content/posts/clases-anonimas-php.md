+++
draft = false
date = 2023-04-07T16:08:53-06:00
title = "¿Qué son las clases anónimas?"
description = "En este post veremos para qué sirven y qué son las clases anónimas"
slug = "que-son-las-clases-anónimas"
authors = ["Mikel Cantero", "Chat GPT"]
tags = ["programación orientada a objetos", "php", "clases anónimas"]
categories = ["programación orientada a objetos", "php"]
externalLink = ""
series = []
+++

**Una clase anónima es una clase que se define de forma anónima, es decir, sin un nombre explícito**. En PHP, las clases anónimas se crean utilizando la palabra clave `new` seguida de la definición de la clase entre paréntesis. La definición de la clase puede incluir propiedades, métodos y otros elementos de la POO.

Las clases anónimas **se utilizan principalmente para crear objetos de forma rápida y sencilla**, sin necesidad de definir una clase completa. Además, las clases anónimas **pueden ser útiles en situaciones en las que se necesitan objetos temporales que no se utilizarán en otros lugares del código**.

## Ventajas y desventajas
Las clases anónimas ofrecen varias ventajas, entre ellas:

- **Flexibilidad:** las clases anónimas permiten la creación de objetos sin necesidad de definir una clase completa, lo que las hace ideales para situaciones en las que se necesitan objetos temporales o específicos para una tarea en particular.

- **Menos código:** al no ser necesario definir una clase completa, el uso de clases anónimas reduce la cantidad de código necesario para crear objetos.

- **Funcionalidad de alto nivel:** las clases anónimas pueden ser utilizadas para implementar características de alto nivel, como closures, que son funciones que pueden ser almacenadas y pasadas como argumentos a otras funciones.

Sin embargo, también existen algunas desventajas en el uso de clases anónimas, como:

- **Dificultad de mantenimiento:** las clases anónimas pueden ser más difíciles de mantener y entender que las clases explícitamente definidas, especialmente en código más complejo.

- **Limitaciones en la reutilización:** las clases anónimas no pueden ser reutilizadas en otros lugares del código, lo que puede limitar su utilidad en algunos casos.

## Ejemplo en PHP
Un ejemplo común de uso de clases anónimas en PHP es en la definición de closures. Las closures son funciones que pueden ser almacenadas y pasadas como argumentos a otras funciones, y pueden ser utilizadas para implementar características avanzadas de la POO, como el patrón de diseño de Strategy.

Supongamos que tenemos la siguiente función `filtrar` que toma un array y una función de filtro como argumentos, y devuelve un nuevo array que contiene sólo los elementos que cumplen con la condición del filtro:
```php
function filtrar($array, $filtro) {
    $resultado = array();
    foreach ($array as $elemento) {
        if ($filtro($elemento)) {
            $resultado[] = $elemento;
        }
    }
    return $resultado;
}

```
Para utilizar esta función, podemos definir una closure que implemente el filtro que deseamos. Por ejemplo, para filtrar todos los elementos mayores que 10 de un array, podemos utilizar la siguiente clase anónima:
```php
$array = array(5, 10, 15, 20);
$filtro = new class {
  public function __invoke($elemento) {
    return $elemento > 10;
  }
};

$resultado = filtrar($array, $filtro);
```

En este ejemplo, hemos creado una clase anónima que implementa el filtro deseado utilizando el método `__invoke`, que permite que la clase se pueda utilizar como una función. Después, pasamos la clase anónima como argumento a la función `filtrar` para que aplique el filtro al array.

## Conclusión

En resumen, las clases anónimas son una característica útil de la POO en PHP que permiten la creación de objetos de forma rápida y sencilla, sin necesidad de definir una clase completa. Si bien tienen algunas limitaciones y pueden ser más difíciles de mantener que las clases explícitamente definidas, las clases anónimas son ideales para situaciones en las que se necesitan objetos temporales o específicos para una tarea en particular. Además, las clases anónimas se pueden utilizar para implementar características avanzadas de la POO, como closures y el patrón de diseño Strategy.
