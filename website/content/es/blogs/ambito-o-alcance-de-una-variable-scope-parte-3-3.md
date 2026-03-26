---
title: "Ambito O Alcance De Una Variable (Scope) Parte 3 de 3"
date: 2026-03-26T01:24:11-05:00
draft: false
author: Richard Almanza
tags:
  - basic
  - scope
image: /images/post.png
description: |-
  Tercera parte de la explicacion sobre el alcance y tiempo de vida de una variable.
toc: true
summary: |-
  Parte 3:

  El tiempo de vida y alcance del acceso a la informacion de una variable.
---
El siguiente articulo hace parte de un grupo de publicaciones que realice en un servidor de Discord. 

Fecha original de publicacion: 2024-09-27

--- Anterior: [Ámbito o alcance de una variable (Scope) (Parte 2 de 3)](/es/blogs/ambito-o-alcance-de-una-variable-scope-parte-2-3)

# Ámbito o alcance de una variable (Scope) (Parte 3 de 3)

## Ejemplos

### Detalles en JavaScript

Por ejemplo, en `javascript`, declarar una variable con `let` dentro del bloque de una condicional morirá ahí, pero al utilizar `var` esa variable seguirá viviendo fuera del bloque de la condicional.

`javascript`
```javascript
if (true) {
  let nombre = "pepe"
  console.log(nombre) // imprime pepe
}

console.log(nombre) // error la variable nombre no esta definida
```

`javascript`
```javascript
if (true) {
  var edad = 15
  console.log(edad) // imprime 15
}

console.log(edad) // imprime 15
```

### Ejemplo shadowing en Python

Aquí se oculta `variableA` de `funcionA` en `funcionB` por declarar una variable con el mismo nombre
Mientras que en `funcionG` no ocurre ocultamiento en ninguno de los bloques padre o abuelo, por lo que accede a `variableA` de `funcionA` 

`python 3`
```python
def funcionA():
    def funcionB():
        def funcionC():
            print(variableA) # Imprime 6, la variable mas cercana
        variableA = 6 # oculta variableA definida en funcionA
        print(variableA) # Imprime 6
        funcionC() # ver en la funcion

    def funcionD():
        def funcionE():
            def funcionG():
                print(variableA) # Imprime hola, porque no hay ocultamiente de variableA
            funcionG()
        funcionE()

    variableA = "hola"
    print(variableA) # Imprime hola
    funcionB() # ver en la funcion
    print(variableA) # Imprime hola
    funcionD() # ver en la funcion

funcionA()
```

## Palabras finales

La principal ventaja de variables globales y locales de orden superior es poder acceder a su información sin necesidad de estar pasando listados de argumentos a funciones, como toca en  **PSeINT**, el problema viene cuando se basa mucho en este modelo.

La complejidad de mantener el código aumenta con el número de usos de estas variables, las veces que se cambia su valor y que tan lejos estas de su bloque de origen.
Además, aumenta el acoplamiento.

> Usemos el 🧵

--- Inicio del hilo

Si quieren mas detalles para Javascript, este este articulo [The Difference of “var” vs “let” vs “const” in Javascript # let](https://medium.com/swlh/the-difference-of-var-vs-let-vs-const-in-javascript-abe37e214d66#dba2)

--- Fin del hilo
