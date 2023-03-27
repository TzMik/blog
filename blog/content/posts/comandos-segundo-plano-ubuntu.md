+++ 
draft = false
date = 2023-03-27T17:20:00-06:00
title = "Como ejecutar un comando en segundo plano en un servidor Ubuntu"
description = "Aprender a utilizar el comando nohup en ubuntu para poder ejecutar comandos en segundo plano y sin que afecte el timeout"
slug = "como-ejecutar-comandos-en-segundo-plano-en-ubuntu"
authors = ["Mikel Cantero"]
tags = ["linux", "ubuntu", "comandos", "terminal", "administración de servidores"]
categories = ["ubuntu", "linux", "administración de servidores"]
+++

Si deseas ejecutar un script en segundo plano en un servidor de forma que se siga ejecutando después de que te desconectes, puedes utilizar el comando `nohup` y redirigir la salida estándar y de error a un archivo.

Además, para asegurarte de que el proceso se siga ejecutando después de que te desconectes del servidor, puedes usar el comando `disown`. Esto separa el proceso del shell que lo inició y lo hace independiente de la sesión del usuario.

Para ejecutar un script en segundo plano en un servidor de forma que se siga ejecutando después de que te desconectes, sigue los siguientes pasos:

1. Conéctate al servidor mediante SSH.

2. Navega hasta la ubicación del script que deseas ejecutar.

3. Ejecuta el comando `nohup` seguido del comando que deseas ejecutar. Por ejemplo:

```bash
nohup ./mi_script.sh &
```

Este comando ejecutará el script `mi_script.sh` en segundo plano y redirigirá la salida estándar y de error a un archivo llamado *nohup.out*.

4. Agrega el `&` al final del comando para ejecutarlo en segundo plano.

5. Ejecuta el comando `disown` para separar el proceso del shell actual:

```bash
disown
```

Con estos pasos, el script se ejecutará en segundo plano y seguirá ejecutándose después de que te desconectes del servidor.

Ten en cuenta que, al ejecutar un proceso en segundo plano de esta forma, ya no tendrás acceso directo a la salida estándar y de error del script. Sin embargo, podrás revisarla en cualquier momento en el archivo `nohup.out` que se ha generado en la ubicación donde se ha ejecutado el comando.