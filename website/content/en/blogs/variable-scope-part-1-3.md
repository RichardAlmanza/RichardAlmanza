---
title: "Variable Scope Part 1 of 3"
date: 2026-03-26T13:59:44-05:00
draft: false
author: Richard Almanza
tags:
  - basic
  - scope
image: /images/post.png
description: |-
  First part of the explanation regarding the scope and lifetime of a variable.
toc: true
summary: |-
  Part 1:

  The lifetime and accessibility scope of a variable's information.
---
The following article is part of a series of posts I made on a Discord server.

Original publication date: 2024-09-27

# Variable Scope (Part 1 of 3)

Scope refers to the part of the program where a variable is accessible.

Normally, it is divided into two types: global variables and local variables, but there are specific details to consider.

## Global Variables

Basically, these are variables that are accessible throughout the entire program.

For example, the `PI` constant in *PSeINT*; we could call it anywhere in the program and retrieve its value.

> **PSeINT** does not support the creation of global variables, so I am using the `PI` constant as an example.

> Constants are like variables, with the difference that they can only be assigned once.

## Local Variables

These are variables that are only accessible within the block where they were defined. This includes internal blocks or child blocks, including "grandchildren"—that is, all their descendants.

### Blocks

By blocks, I refer to sections of the program; these can be the definition block of a function, a loop, or a conditional.
Variables defined within a block do not exist outside of it; that is, they are born and die within the block.

> Note: The specifics of what is considered a block and the lifetime of a variable will depend on the language.

## Local and Global Variables with the Same Name (Shadowing)

When a local variable is defined with the same name as a global one, the value of the global variable is not overwritten. Instead, within that block, the local variable will be accessed rather than the global one—in other words, the "closest" variable is used.

This also applies to local variables of a higher order. For example, if `variablePeter` is defined in the parent block and in the great-great-grandfather block, the current (child) block will access the `variablePeter` defined in the parent block.

## Details

The information provided above applies generally to many languages, but you should read about how variable scope specifically works in each language you use.

--- Next: [Variable Scope (Part 2 of 3)](/en/blogs/variable-scope-part-2-3)
