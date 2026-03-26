---
title: "Variables Memoria Y Tipos Parte 1 de 3"
date: 2026-03-25T19:22:34-05:00
draft: false
author: Richard Almanza
tags:
  - basic
  - memory
image: /images/post.png
description: |-
  Primera parte de como comprender el funcionamiento de las variables, memoria y tipos de datos.
toc: true
summary: |-
  Parte 1:

  Los numeros, letras, imagenes, etc. Todos son combinaciones de estados en las celdas de memoria.
---
El siguiente articulo hace parte de un grupo de publicaciones que realice en un servidor de Discord. 

Fecha original de publicacion: 2024-09-13

# Variables, Memoria y Tipos (Parte 1 de 3)

Un poco de repaso con esto no vendría mal, sobre todo porque dentro de unas semanas entraremos a Java y se expandirá la versatilidad y su vez la complejidad

## Variables

Las variables son contenedores o cajas etiquetadas donde almacenamos la información que requeriremos más adelante (***imagen-1***), pero donde existen estas cajas? Existen en la memoria, ya sea en la temporal o persistente, pero nos enfocaremos en la memoria temporal donde mayormente vivirá el programa durante su ejecución.

***imagen-1***
![diferente tipos de varibles](/images/posts/variables-memoria-y-tipos/tipo-de-variables.webp)

## Memoria

La memoria física está conformada por celdas que contienen una representación de un estado de dos posibles, estoy hablando del bit!

***imagen-2***
![diferentes ejemplos de un bit](/images/posts/variables-memoria-y-tipos/que-es-un-bit.webp)

Un bit puede estar representado de muchas formas (***imagen-2***), hasta aquí no parece ser posible algo diferente que un **Verdadero (V)** o **Falso (F)**, pero si agrupamos 2 bits tendremos 4 estados posibles del conjunto!

1. FF
2. FV
3. VF
4. VV

Continuando, 3 bits tienen 8 estados posibles, el conjunto de 4 bits tienen 16 estados posibles y así por cada bit extra duplicamos la cantidad de estados posibles.
Un byte es el conjunto de 8 bits y con base en lo anterior, el conjunto de 8 bits (1 byte) permite un total de 256 estados posibles (2^#Bits).

Volviendo a la lista de estados posibles con 2 bits, estos estados están enumerados, lo cual significa que los podemos utilizar para contar, pero para poder representar el 0 corramos la lista en uno, así dándole a **FF** el valor representativo de 0 y 3 a **VV**, entonces con 1 byte podemos representar los números del 0 a 255 (2^#Bits - 1).

A donde voy con todo esto? A que en realidad la memoria solo contiene estados (representando *información*). Así que los números, letras, palabras y todo lo demás ***"No existen"***, pero entraré en más detalle cuando hable de los **Tipos**

--- continuación: [Variables, Memoria y Tipos (Parte 2 de 3)](/es/blogs/variables-memoria-y-tipos-parte-2-3)
