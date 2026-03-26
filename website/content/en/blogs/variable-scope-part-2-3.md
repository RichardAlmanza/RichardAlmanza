---
title: "Variable Scope Part 2 of 3"
date: 2026-03-26T14:06:01-05:00
draft: false
author: Richard Almanza
tags:
  - basic
  - scope
image: /images/post.png
description: |-
  Second part of the explanation regarding the scope and lifetime of a variable.
toc: true
summary: |-
  Part 2:

  The lifetime and scope of access to a variable's information.
---
The following article is part of a series of posts I made on a Discord server.

Original publication date: 2024-09-27

--- Previous: [Variable Scope (Part 1 of 3)](/en/blogs/variable-scope-part-1-3)

# Variable Scope (Part 2 of 3)

## Examples

### Variable accessibility depending on the relationship between blocks

(***image-1***) Global variables can be accessed from any part of the program; there isn't much to consider here.

***image-1***
![Image shows accessibility depending on where the call is made](/images/posts/ambito-o-alcance-de-una-variable-scope/vida-de-las-variables.webp)

Now, for local variables:

- Inside `FunctionC`, there is a request to access (or modify) `VariableA`. This variable was created within `FunctionA`, and `FunctionC` is also nested within `FunctionA`. By the way, every child block dies before its parent block. Based on this, `VariableA` is alive and accessible throughout the entire lifetime of `FunctionC`, provided that `VariableA` was created before `FunctionC`.

- In `FunctionB`, access to `VariableC` is requested, but this variable only exists during the lifetime of `FunctionD`. If the request is made before `FunctionD`, then `VariableC` hasn't been created yet; if it is made after `FunctionD`, then it is already dead. Basically, the parent block cannot access the variables of the child block.

- Finally, inside `FunctionD`, a request is made for `VariableB`, which lives in `FunctionA`. However, `FunctionD` is a "nephew" of `FunctionA` and they do not exist at the same time.

Sibling blocks do not live at the same time; one sibling block lives and dies before or after another. (We break this statement with parallelism and concurrency, but now is not the time to get into that).

(***image-2***) In this presentation, it is easier to observe the accessibility of variables depending on the block relationship.

***image-2***
![Image shows the blocks and spaces where variables exist](/images/posts/ambito-o-alcance-de-una-variable-scope/vida-de-las-variables-2.webp)

- Child blocks are directly above their parent block.

- Sibling blocks are located at the same level.

- Additionally, the lifetimes of the blocks can be represented on the horizontal axis and do not overlap.

The arrows indicate the direction of the request for a variable, and just like in ***image-1***, variables outside their own block only continue to live if they belong to the parent block and/or direct ancestry.

--- Downloads

{{< link href="/downloads/posts/en/global-and-local-variables.excalidraw" download="" >}}
Excalidraw File
{{< /link >}}

--- End of section

--- Next: [Variable Scope (Part 3 of 3)](/en/blogs/variable-scope-part-3-3)

