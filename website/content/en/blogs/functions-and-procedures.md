---
title: "Functions and Procedures"
date: 2026-03-26T03:15:38-05:00
draft: false
author: Richard Almanza
tags:
  - basic
  - functions
image: /images/post.png
description: |-
  Concepts of pure functions and procedures
toc: true
summary: |-
  Procedures and functions! The subtle difference between these types of functions.
---
The following article is part of a series of posts I made on a Discord server.

Original publication date: 2024-09-06

# Functions and Procedures

A question arose today regarding these two, mainly because in **PSeInt** practice, there is no apparent difference between the reserved words `Funcion` and `SubProceso`, much like the reserved words `Mostrar` and `Escribir` which behave identically.

In professional software development, such a sharp distinction isn't always made; you will typically find them grouped under the same name: *functions*. Sometimes they are only differentiated as *functions without a return* (**procedures**) and *functions with a return or that return a value* (**functions**).

![graphic representing the difference between procedures and functions](/images/posts/subprocesos-y-funciones/subprocesos-y-funciones.webp)

## Functions

(Pure) functions do not modify the objects (variables or information) we pass to them, but they will return something new based on what we provided.

In the example in the ***image***, I have *square1*; based on it, the function generated *square2*, and now I have both.

## Procedures

In the words of the **egg** material:
> Unlike functions, procedures are not required to return a value. However, if a procedure needs to modify a variable, you can use "pass by reference," which allows sharing the memory reference of a variable. This means that if a procedure modifies a variable's value, that change will be reflected in the calling program when control is returned.

Procedures modify the state of something. In the ***image*** example, the procedure is changing the state of *square1*, moving it from *state1* to *state2*. Let’s say the state before executing the procedure was a blue square (or a variable storing the number 15), and after execution, it is a pink square (or a variable storing the number 1623). We are still talking about the same square (or variable), just at two different moments: before and after the procedure.

> Let's use the message thread 🧵

--- Start of thread

An example that, in practice, might look almost identical:
`procedure(variableA)` is equivalent to `variableA = function(variableA)`

Additionally, there are cases where functions are not pure; besides returning something, they also modify another variable by reference.

---

There are contexts where we will primarily handle functions or primarily procedures, such as in functional programming (e.g., Erlang) and object-oriented programming (e.g., Java). however, most languages are more pragmatic, allowing you to use whichever you prefer.

--- End of thread
