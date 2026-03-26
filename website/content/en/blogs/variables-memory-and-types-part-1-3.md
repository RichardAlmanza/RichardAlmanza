---
title: "Variables, Memory, and Types Part 1 of 3"
date: 2026-03-26T03:25:09-05:00
draft: false
author: Richard Almanza
tags:
  - basic
  - memory
image: /images/post.png
description: |-
  Part one of understanding how variables, memory, and data types work.
toc: true
summary: |-
  Part 1:

  Numbers, letters, images, etc. All are combinations of states in memory cells.
---
The following article is part of a group of posts I made on a Discord server.

Original publication date: 2024-09-13

# Variables, Memory, and Types (Part 1 of 3)

A little review of this wouldn't hurt, especially since in a few weeks we will be starting Java, and the versatility—and in turn, the complexity—will expand.

## Variables

Variables are labeled containers or boxes where we store information that we will require later (***image-1***), but where do these boxes exist? They exist in memory, whether temporary or persistent, but we will focus on temporary memory where the program will mostly live during its execution.

***image-1***
![different types of variables](/images/posts/variables-memoria-y-tipos/tipo-de-variables.webp)

## Memory

Physical memory is made up of cells that contain a representation of one of two possible states—I'm talking about the bit!

***image-2***
![different examples of a bit](/images/posts/variables-memoria-y-tipos/que-es-un-bit.webp)

A bit can be represented in many ways (***image-2***); so far, it doesn't seem possible to have anything other than **True (T)** or **False (F)**, but if we group 2 bits, we will have 4 possible states for the set!

1. FF
2. FT
3. TF
4. TT

Continuing, 3 bits have 8 possible states, a set of 4 bits has 16 possible states, and so on—for every extra bit, we double the number of possible states.
A byte is a set of 8 bits and, based on the above, the set of 8 bits (1 byte) allows for a total of 256 possible states ($2^#Bits).

Going back to the list of possible states with 2 bits, these states are numbered, which means we can use them to count. But to represent 0, let's shift the list by one, giving **FF** the representative value of 0 and **TT** the value of 3. Therefore, with 1 byte, we can represent numbers from 0 to 255 ($2^#Bits - 1).

Where am I going with all this? Because in reality memory only contains states (representing *information*). So numbers, letters, words and everything else ***"Do not exist"***, but I will go into more detail when I talk about **Types**

--- Next: [Variables, Memory, and Types (Part 2 of 3)](/en/blogs/variables-memory-and-types-part-2-3)
