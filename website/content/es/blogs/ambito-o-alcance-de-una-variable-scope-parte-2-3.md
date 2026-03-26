---
title: "Ambito O Alcance De Una Variable (Scope) Parte 2 de 3"
date: 2026-03-26T01:24:08-05:00
draft: false
author: Richard Almanza
tags:
  - basic
  - scope
image: /images/post.png
description: |-
  Segunda parte de la explicacion sobre el alcance y tiempo de vida de una variable.
toc: true
summary: |-
  Parte 2:

  El tiempo de vida y alcance del acceso a la informacion de una variable.
---
El siguiente articulo hace parte de un grupo de publicaciones que realice en un servidor de Discord. 

Fecha original de publicacion: 2024-09-27

--- Anterior: [Ámbito o alcance de una variable (Scope) (Parte 1 de 3)](/es/blogs/ambito-o-alcance-de-una-variable-scope-parte-1-3)

# Ámbito o alcance de una variable (Scope) (Parte 2 de 3)

## Ejemplos

### Accesibilidad de variables dependiendo de la relación entre los bloques

(***imagen-1***) Las variables globales pueden ser accedidas desde cualquier parte del programa, aquí no hay mucho que considerar.

***imagen-1***
![Imagen muestra la accesibilidad dependiendo desde donde se llama](/images/posts/ambito-o-alcance-de-una-variable-scope/vida-de-las-variables.webp)

Ahora las variables locales:

- Dentro de `FuncionC` hay una solicitud para acceder (o modificar) a `VariableA` y ésta nació dentro de `FuncionA`, `FuncionC` también nace en `FuncionA`, por cierto, todo bloque hijo muere antes de su bloque padre. Con base en lo anterior, `VariableA` está viva y accesible durante toda la vida de `FuncionC` si `VariableA` nació antes que `FuncionC`.

- En `FuncionB` se solicita acceso a `VariableC`, pero esta variable solo existe en el tiempo de vida de `FuncionD`. Si la solicitud es antes de la `FuncionD` entonces `VariableC` aún no nace, pero si es después de `FuncionD` entonces ya está muerta, básicamente, el bloque padre no puede acceder a las variables del bloque hijo.

- Por último, dentro de `FuncionD` se está solicitando a `VariableB` que vive en `FuncionA`, pero `FuncionD` es sobrino de `FuncionA` y no viven en el mismo tiempo.

Los bloques hermanos no viven en el mismo tiempo, un bloque hermano vive y muere antes o después de otro. (Con paralelismo y concurrencia rompemos esta afirmación, pero ahora no es el momento de entrar en esto)

(***imagen-2***) En esta presentación es más sencillo de observar la accesibilidad de las variables dependiendo de
la relación del bloque.

***imagen-2***
![Imagen muestra los bloques y espacios en donde las variable existen](/images/posts/ambito-o-alcance-de-una-variable-scope/vida-de-las-variables-2.webp)

- Los bloques hijos están directamente arriba de su bloque padre

- Los bloques hermanos se encuentran al mismo nivel

- Además, los tiempos de vida de los bloques se pueden representar en el eje horizontal y no se superponen. 

Las flechan indican el sentido de la solicitud de alguna variable, y al igual que en la ***imagen-1***, las variables fuera de su propio bloque solo siguen viviendo si pertenecen al bloque padre y/o ascendencia directa.

--- Descargas

{{< link href="/downloads/posts/es/variables-globales-y-locales.excalidraw" download="" >}}
Archivo Excalidraw
{{< /link >}}

--- Fin seccion

--- Continuación: [Ámbito o alcance de una variable (Scope) (Parte 3 de 3)](/es/blogs/ambito-o-alcance-de-una-variable-scope-parte-3-3)
