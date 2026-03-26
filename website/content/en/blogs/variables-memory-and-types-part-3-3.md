---
title: "Variables, Memory, and Types Part 3 of 3"
date: 2026-03-26T03:59:01-05:00
draft: false
author: Richard Almanza
tags:
  - basic
  - memory
image: /images/post.png
description: |-
  Third part of how to understand the functioning of variables, memory, and data types.
toc: true
summary: |-
  Part 3

  Metadata is the basis for interpreting memory, objects, and basically every abstraction in computing.
---
The following article is part of a series of posts I made on a Discord server.

Original publication date: 2024-09-13

--- Previous: [Variables, Memory, and Types (Part 2 of 3)](/en/blogs/variables-memory-and-types-part-2-3)

# Variables, Memory, and Types (Part 3 of 3)

## Types (Continued)

The same byte can represent different information depending on how we interpret it, so why limit ourselves to only the 4 types in **PSeINT**? In other languages like Java, we can create more variable types, whether by assembling a set of types we already manage in **PSeINT**, others present in Java, or entirely new ones.

A classic example is the *point type* (or *class*); it is formed by 2 real numbers, *similar to saying it is a real-type vector of dimension 2*, but depending on the language, we can define how this type interacts with others, either by limiting operations only to its own *point type* or by allowing multiplications with integers and real numbers.

Let's say `Define origin As Point`, but trying `variableA = origin + "hello"` would throw an error because it makes no sense to allow this type of operation... **Why or how would you add a *point* (coordinates on a plane) to a *string*?** 😖
However, it would make sense to operate it with other points or use it to define a more complex type, such as a vector on a plane.

### Conclusion

Depending on the language, we will have more or less control over the different layers of abstraction we create or use in a program.

## More Material

This video from Veritasium explains in a very interesting way how we can represent information in bits and also covers information density.

> [How Much Information?](https://www.youtube.com/watch?v=zUDqI9PJpc8)
>
> {{< youtube zUDqI9PJpc8 >}}

Additionally, I'm sharing 3 videos about computers without electricity.

> [I Made A Water Computer And It Actually Works](https://www.youtube.com/watch?v=IxXaizglscw)
>
> {{< youtube IxXaizglscw >}}

> [A Computer That Runs on Marbles](https://www.youtube.com/watch?v=8BOvLL8ok8I)
>
> {{< youtube 8BOvLL8ok8I >}}

> [Mechanical circuits: electronics without electricity](https://www.youtube.com/watch?v=QrkiJZKJfpY)
>
> {{< youtube QrkiJZKJfpY >}}

Let's use the thread 🧵🙂
