---
title: "Subprocesos y funciones"
date: 2026-03-24T23:32:42-05:00
draft: false
author: Richard Almanza
tags:
  - basic
  - functions
image: /images/post.png
description: |-
  Conceptos de funciones puras y subprocesos
toc: true
summary: |-
  Subprocesos y funciones! La sutil diferencia entre los tipoes de funciones.
---
El siguiente articulo hace parte de un grupo de publicaciones que realice en un servidor de Discord. 

Fecha original de publicacion: 2024-09-06

# Funciones y Subprocesos

Hoy surgió una duda al respecto de estos dos, debido a que en la práctica de **PSeInt** no presenta una diferencia entre las palabras reservadas `Funcion` y `SubProceso`, así como las palabras reservadas `Mostrar` y `Escribir` que se comportan igual.

En la práctica del desarrollo de software no se hace una distinción tan marcada entre los dos, además que normalmente las encontraras agrupadas bajo el mismo nombre, *funciones*. A veces solamente las diferencian como *función sin retorno* (**subproceso**) y *función con retorno o que devuelve algo* (**función**).

![grafica que representa la diferencia de subprocesos y funciones](/images/posts/subprocesos-y-funciones/subprocesos-y-funciones.webp)

## Funciones

Las funciones (puras) no modifican las cosas (o variables o información) que les pasemos, pero sí nos devolverán algo nuevo a partir de lo que les pasamos.

En el ejemplo de la ***imagen*** tengo mi *cuadrado1* y con base en él, la función me generó el *cuadrado2* y ahora teniendo ambos.

## Subprocesos

En las palabras del material de **egg** 
> A diferencia de las funciones, los procedimientos no están obligados a retornar un valor. Sin embargo, si se necesita que un procedimiento modifique una variable, se puede utilizar el paso de “parámetros por referencia”, lo que permite compartir la referencia de memoria de una variable. Esto significa que si un procedimiento modifica el valor de una variable, ese cambio se reflejará en el programa que lo invocó al retornar el control.

Los procedimientos/subprocesos modifican el estado de algo, en el ejemplo de la ***imagen*** el subproceso está cambiando el estado del *cuadrado1* y lo pasó de un *estado1* a un *estado2*, digamos que el estado antes de haber ejecutado el subproceso era un cuadrado que era de color azul (o una variable con el número 15 almacenado) y después de la ejecución es un cuadrado de color rosa (o una variable con el número 1623 almacenado), pero seguimos hablando del mismo cuadrado (o variable) solo que en dos momentos diferentes, antes y después del subproceso.

> Usemos el hilo del mensaje 🧵


--- Inicio del hilo

Un ejemplo que en la practica puede no diferenciarse en casi nada
`subproceso(variableA)` es equivalente a `variableA = funcion(variableA)`

aparte también hay casos donde las funciones no son puras y aparte de devolver algo, modifican alguna otra variable por referencia

---

Hay contextos donde manejaremos principalmente funciones o principalmente subprocesos/procedimientos, como son en la programación funcional (ejemplo de lenguaje: Erlang) y la programación orientada a objetos (ejemplo de lenguaje: Java), pero la mayoría de lenguajes son de tipo mas pragmático y podrás utilizar cual sea de tu preferencia

--- Fin del hilo

