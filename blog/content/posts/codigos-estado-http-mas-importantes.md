+++ 
draft = false
date = 2023-04-15T12:33:58-06:00
title = "Los códigos de estado HTTP más importantes que debes conocer"
description = "En este post descubriremos cuáles son los códigos de estado más usados en las APIs"
slug = "los-codigos-de-estado-http-mas-importantes-que-debes-conocer"
authors = ["Mikel Cantero", "ChatGPT"]
tags = ["api", "http", "códigos de estado http"]
categories = ["api", "http"]
externalLink = ""
series = []
+++

Los códigos de estado HTTP son una forma de comunicación entre el servidor y el cliente en una solicitud HTTP. Estos códigos son una forma de indicar el resultado de la solicitud y proporcionan información útil para el cliente y el servidor. Aquí están los códigos de estado HTTP más importantes que todo desarrollador web debería conocer.

## 1xx - Respuestas informativas
Los códigos de estado en la serie 1xx son respuestas informativas, lo que significa que el servidor está respondiendo a una solicitud preliminar del cliente y que aún no ha comenzado a procesar la solicitud.

### 100 - Continuar
El código de estado 100 se utiliza para indicar que el servidor ha recibido la solicitud y que el cliente puede continuar con la siguiente parte de la solicitud.

## 2xx - Respuestas satisfactorias
Los códigos de estado en la serie 2xx son respuestas satisfactorias, lo que significa que el servidor ha procesado con éxito la solicitud del cliente.

### 200 - OK
El código de estado 200 se utiliza para indicar que la solicitud se ha completado correctamente y que se ha enviado una respuesta.

### 201 - Creado
El código de estado 201 se utiliza para indicar que la solicitud ha sido procesada con éxito y que se ha creado un nuevo recurso.

## 3xx - Redirecciones
Los códigos de estado en la serie 3xx indican que la solicitud del cliente se ha redirigido a otra ubicación.

### 301 - Movido permanentemente
El código de estado 301 se utiliza para indicar que la ubicación de un recurso ha sido cambiada permanentemente.

### 302 - Encontrado
El código de estado 302 se utiliza para indicar que la ubicación de un recurso ha sido cambiada temporalmente.

## 4xx - Errores del cliente
Los códigos de estado en la serie 4xx indican que la solicitud del cliente no se ha podido procesar correctamente debido a un error del cliente.

### 400 - Solicitud incorrecta
El código de estado 400 se utiliza para indicar que la solicitud del cliente no se puede procesar debido a una solicitud incorrecta.

### 401 - No autorizado
El código de estado 401 se utiliza para indicar que el cliente no está autorizado para acceder al recurso solicitado.

### 404 - No encontrado
El código de estado 404 se utiliza para indicar que el recurso solicitado no se puede encontrar en el servidor.

## 5xx - Errores del servidor
Los códigos de estado en la serie 5xx indican que la solicitud del cliente no se ha podido procesar correctamente debido a un error en el servidor.

### 500 - Error interno del servidor
El código de estado 500 se utiliza para indicar que se ha producido un error interno en el servidor y que no se puede procesar la solicitud.

### 503 - Servicio no disponible
El código de estado 503 se utiliza para indicar que el servidor no está disponible temporalmente para procesar la solicitud.

En resumen, estos son algunos de los códigos de estado HTTP más importantes que debes conocer. Conocer estos códigos de estado te ayudará a identificar rápidamente los problemas de solicitud y respuesta en tu aplicación web, lo que te permitirá solucionar problemas y mejorar la experiencia del usuario.
