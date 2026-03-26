---
title: "Variables Memoria Y Tipos Parte 2 de 3"
date: 2026-03-25T19:45:05-05:00
draft: false
author: Richard Almanza
tags:
  - basic
  - memory
image: /images/post.png
description: |-
  Segunda parte de como comprender el funcionamiento de las variables, memoria y tipos de datos.
toc: true
summary: |-
  Parte 2:
  
  Punteros, referencias, y variables son direcciones a una ubicacion fisica de la memoria.
---
El siguiente articulo hace parte de un grupo de publicaciones que realice en un servidor de Discord. 

Fecha original de publicacion: 2024-09-13

--- Anterior: [Variables, Memoria y Tipos (Parte 1 de 3)](/es/blogs/variables-memoria-y-tipos-parte-1-3)

# Variables, Memoria y Tipos (Parte 2 de 3)

## Variables y Memoria

Si la memoria es tan grande como sabe donde está mi variable?

La memoria utiliza direcciones para ubicar los grupos de celdas y resulta que el nombre de las variables son etiquetas que se vinculan a la dirección de la memoria donde se encuentra nuestro valor, entonces cuando le pedimos el contenido de la variable el computador debe ir a la ubicación de la memoria para traer el valor que se encuentra guardado ahí (en sus celdas), de igual forma sucede al guardar un valor

### Variables por referencia

En **PSeINT** no será el último lugar donde encontrar la referencia a **referencia** (si fue apropósito 😆 ), comúnmente cuando se habla de referencia, quieren decir la dirección de la memoria vinculada a la variable.

Digamos que la variable `edadUsuario` tiene vinculada la dirección *124* (grupo de celdas # 124), al pasar la referencia a una función u otra variable, significa que le estamos pasando es la dirección *124*... Es como darle un Alias a la variable, porque ahora 2 etiquetan tienen vinculada la misma dirección de memoria (***imagen-1***)

***imagen-1***
![variables por referencia](/images/posts/variables-memoria-y-tipos/variables-y-memoria.webp)

### Variables por valor

Es sencillamente realizar una copia del valor en otra parte de la memoria que el programa podrá utilizar y modificar, pero sin perturbar/modificar la variable original

## Tipos

Los **tipos** son meta-datos (datos acerca los datos), y su intención es dar información sobre que representa el conjunto de bits almacenados en la variable, es decir, nos dice como debemos interpretar el estado presente del conjunto de celdas, digamos 1 byte (así vamos aterrizando el ejemplo)

Un byte con el siguiente estado `FVVFVFVF`, que representado en número binario si **V** es **1** y **F** es **0** entonces `01101010`, según el tipo es:
- Real: `1.49e-43`
- Entero: `106`
- Logico: `Verdadero`
- Caracter: `j`

El programa o nosotros le damos sentido a los datos almacenados.

--- Descargas

{{< link href="/downloads/posts/es/variables-memoria-y-tipos.excalidraw" download="" >}}
Archivo Excalidraw
{{< /link >}}

--- Fin seccion

--- continuación: [Variables, Memoria y Tipos (Parte 3 de 3)](/es/blogs/variables-memoria-y-tipos-parte-3-3)
