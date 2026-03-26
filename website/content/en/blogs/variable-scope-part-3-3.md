---
title: "Variable Scope Part 3 of 3"
date: 2026-03-26T14:15:15-05:00
draft: false
author: Richard Almanza
tags:
  - basic
  - scope
image: /images/post.png
description: |-
  Third part of the explanation regarding the scope and lifetime of a variable.
toc: true
summary: |-
  Part 3:

  The lifetime and scope of access to a variable's information.
---
The following article is part of a series of posts I made on a Discord server.

Original publication date: 2024-09-27

--- Previous: [Variable Scope (Part 2 of 3)](/en/blogs/variable-scope-part-2-3)

# Variable Scope (Part 3 of 3)

## Examples

### Details in JavaScript

For example, in `javascript`, declaring a variable with `let` inside a conditional block will cause it to "die" there; however, when using `var`, that variable will continue to live outside the conditional block.

`javascript`
```javascript
if (true) {
  let name = "peter"
  console.log(name) // prints peter
}

console.log(name) // error: name is not defined
```

`javascript`
```javascript
if (true) {
  var age = 15
  console.log(age) // prints 15
}

console.log(age) // prints 15
```

### Shadowing Example in Python

In this case, `variableA` from `functionA` is hidden in `functionB` by declaring a variable with the same name.
Meanwhile, in `functionG`, no shadowing occurs in any of the parent or grandparent blocks, so it accesses `variableA` from `functionA`.

`python 3`
```python
def functionA():
    def functionB():
        def functionC():
            print(variableA) # Prints 6, the closest variable
        variableA = 6 # shadows variableA defined in functionA
        print(variableA) # Prints 6
        functionC() # see inside function

    def functionD():
        def functionE():
            def functionG():
                print(variableA) # Prints hello, because there is no shadowing of variableA
            functionG()
        functionE()

    variableA = "hello"
    print(variableA) # Prints hello
    functionB() # see inside function
    print(variableA) # Prints hello
    functionD() # see inside function

functionA()
```

## Closing Thoughts

The main advantage of global variables and higher-order local variables is being able to access their information without needing to pass lists of arguments to functions—as is required in **PSeINT**. The problem arises when one relies too heavily on this model.

The complexity of maintaining code increases with the number of times these variables are used, the frequency with which their values are changed, and how far you are from their original block. 
Additionally, it increases coupling.

> Let's use the 🧵

--- Start of thread

If you want more details for Javascript, check out this article: [The Difference of "var" vs "let" vs "const" in Javascript # let](https://medium.com/swlh/the-difference-of-var-vs-let-vs-const-in-javascript-abe37e214d66#dba2)

--- End of thread
