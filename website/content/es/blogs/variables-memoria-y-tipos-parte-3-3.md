---
title: "Variables Memoria Y Tipos Parte 3 de 3"
date: 2026-03-25T19:57:12-05:00
draft: false
author: Richard Almanza
tags:
  - basic
  - memory
image: /images/post.png
description: |-
  Tercera parte de como comprender el funcionamiento de las variables, memoria y tipos de datos.
toc: true
summary: |-
  Parte 3

  Los metadatos son la base para la interpretacion de la memoria, de los objetos y basicamente toda abstraccion en la computacion.
---
El siguiente articulo hace parte de un grupo de publicaciones que realice en un servidor de Discord. 

Fecha original de publicacion: 2024-09-13

--- Anterior: [Variables, Memoria y Tipos (Parte 2 de 3)](/es/blogs/variables-memoria-y-tipos-parte-2-3)

# Variables, Memoria y Tipos (Parte 3 de 3)

## Tipos (Continuación)

El mismo byte puede representar información diferente dependiendo de como lo interpretemos, entonces porque limitarnos a solo 4 tipos de **PSeINT**? En otros lenguajes como Java podemos crear más tipos de variables, ya sea armar un conjunto de tipos de los que ya manejamos en **PSeINT**, otros presentes en Java u otros nuevos.

Un clásico ejemplo es el *tipo punto* (o *clase*), está formado por 2 números reales, *similar a decir que es un vector de tipo real y de dimensión 2*, pero dependiendo del lenguaje podemos definir como este tipo interactúa con los demás, ya sea limitando operaciones solo con su mismo *tipo punto* o permitiendo multiplicaciones de números enteros y reales.

Digamos `Definir origen Como Punto`, pero intentar `variableA = origen + "hola"` saltaría un error porque no tiene sentido que queramos permitir este tipo de operación... **Por qué o como sumarias un *punto* (coordenadas de un plano) con una *cadena*?** 😖 
Pero tendría sentido poder operarse con otros puntos o utilizarse para definir otro tipo más complejo, como un vector de un plano.

### Conclusión

Dependiendo del lenguaje nos permitirá tener más o menos control sobre las diferentes capas de abstracción que creemos o usemos en un programa

## Más Material

Este vídeo de Veritasium explica de forma muy interesante como podemos representar información en bits y explica también sobre la densidad de la información

> [How Much Information?](https://www.youtube.com/watch?v=zUDqI9PJpc8)
>
> {{< youtube zUDqI9PJpc8 >}}

Además, comparto 3 vídeos de computadoras sin electricidad

> [I Made A Water Computer And It Actually Works](https://www.youtube.com/watch?v=IxXaizglscw)
>
> {{< youtube IxXaizglscw >}}

> [A Computer That Runs on Marbles](https://www.youtube.com/watch?v=8BOvLL8ok8I)
>
> {{< youtube 8BOvLL8ok8I >}}

> [Mechanical circuits: electronics without electricity](https://www.youtube.com/watch?v=QrkiJZKJfpY)
>
> {{< youtube QrkiJZKJfpY >}}

Usemos el hilo 🧵🙂