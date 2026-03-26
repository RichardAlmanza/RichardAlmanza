---
title: "Ambito o Alcance de una Variable (Scope) Parte 1 de 3"
date: 2026-03-25T23:23:29-05:00
draft: false
author: Richard Almanza
tags:
  - basic
  - scope
image: /images/post.png
description: |-
  Primera parte de la explicacion sobre el alcance y tiempo de vida de una variable.
toc: true
summary: |-
  Parte 1:

  El tiempo de vida y alcance del acceso a la informacion de una variable.
---
El siguiente articulo hace parte de un grupo de publicaciones que realice en un servidor de Discord. 

Fecha original de publicacion: 2024-09-27

# Ámbito o alcance de una variable (Scope) (Parte 1 de 3)

Se refiere a la parte del programa donde la variable es asequible.

Normalmente, se separa en 2 tipos, variables globales y variables locales, pero hay detalles.

## Variables globales

Básicamente, son las variables que son asequibles en todo el programa.

Por ejemplo, la constante de `PI` en *PSeINT*, la podíamos llamar en cualquier parte del programa y podíamos adquirir su valor.

> **PSeINT** no soporta la creacion de variables globales, asi que utilizo la constante `PI` como ejemplo.

> Las constantes son como las variables, pero con la diferencia que solo se puede asignar una sola vez

## Variables Locales

Son variables que solamente son asequibles  dentro del bloque donde fueron definidas, esto incluye a los bloques internos o bloques hijos, incluyendo hijos de hijos, es decir, toda su descendencia.

### Bloques

Con bloques me refiero a secciones del programa, pueden ser el bloque de definición de alguna función, bucle o condicional.
Las variables definidas dentro de un bloque,  no existen fuera de él, es decir, nacen y mueren en el bloque.

> Nota: Los detalles de que se le considera un bloque y del tiempo de vida de la variable dependeran del lenguaje

## Variables Locales  y Globales con el mismo nombre (Shadowing)

Cuando se define una variable local con el mismo nombre que una global, no se sobreescribe el valor de la variable global, simplemente dentro del bloque se obtendrá es la variable local y no la global, es decir, la variable más cercana.

Esto también aplica para variables locales de orden superior, por ejemplo la `variablePepe`es definida en el bloque padre y en el bloque del tatarabuelo, el bloque actual (hijo) accederá a la variable `variablePepe` definida en el bloque del padre.

## Detalles

La información que di antes se aplica de forma general a muchos lenguajes, pero se debe leer de como específicamente funciona el ámbito de las variables en cada lenguaje que estés utilizando.

--- Continuación: [Ámbito o alcance de una variable (Scope) (Parte 2 de 3)](/es/blogs/ambito-o-alcance-de-una-variable-scope-parte-2-3)
