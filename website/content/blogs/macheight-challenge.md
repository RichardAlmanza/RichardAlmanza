---
title: "MachEight Challenge"
date: 2023-08-17T03:05:55Z
draft: false
author: Richard Almanza
tags:
  - challenge
  - macheight
  - find-pairs
image: /images/post.png
description: -|
  This is an algorithm challenge from MachEight
toc: true
repository: https://github.com/RichardAlmanza/other-challenges/tree/main/macheight
---

{{% repository %}}

# Content

- [Content](#content)
  - [Mach Eight Sample Project](#mach-eight-sample-project)
    - [Task](#task)
    - [Evaluation](#evaluation)
    - [Submission](#submission)
  - [Solution](#solution)
    - [Environment](#environment)
    - [Program](#program)
      - [Usage](#usage)
      - [Build](#build)
      - [Running the program](#running-the-program)
        - [Reading from a file](#reading-from-a-file)

## Mach Eight Sample Project

​
Thank you for taking the time to complete this sample project. We're a tech
first company and we value our engineers tremendously. We're are looking for
hard working, smart engineers with either excellent experience or lots of
potential.
​

### Task

​
The task is to write a function that finds pairs of integers from a list that
sum to a given value. The function will take as input the list of numbers as
well as the target sum.
​
Sample output is shown below.

```bash
> app 1,9,5,0,20,-4,12,16,7 12
​
+ 12,0
+ 5,7
+ 16,-4
​
```

​
In the example, there is an executable named `app`. It takes as command line
arguments a comma separated list of integers, and the target integer. Your app
doesn't need to have identical input/output mechanisms. For example, you could
read from a file instead of the command line.
​
You can assume that all input values are integers. You can assume that there aren't
any repeat values in the list.
​
The algorithm to find the pairs must be faster than O(n^2). All edge cases
should be handled appropriately. This is _not_ a closed book test. You are
encouraged to reach out with any questions that you come across.
​

### Evaluation

​
All candidates who submit an algorithm that is efficient and correct will pass
to the next step of the interview process. We define "efficient" as faster than
O(n^2) and "correct" as returning the correct results for all possible inputs.
Any assignment that doesn't return the correct answer for the sample input
above will fail.
​
If you feel the need to impress us by going above and beyond, we're impressed
by good unit tests as well as clean and readable code. We're less interested in
your knowledge of any particular framework (react, django, etc.). You're
welcome to create a full featured web app with pretty graphics if you want, but
that will not improve your chances of passing. There have been passing
assignments written in under 20 lines of python.
​
​

### Submission

​
The preferred form of submission is by publishing a public repo on github with
your code and a README file explaining how to run the code.

----------------------------------

## Solution

### Environment

OS: Arch Linux x86_64

Shell: GNU bash, version 5.1.16(1)-release (x86_64-pc-linux-gnu) and zsh 5.9 (x86_64-pc-linux-gnu)

Go: go version go1.20.4 linux/amd64

Docker: Docker version 23.0.6, build ef23cbc431(client) 9dbdbd4b6d(server)

### Program

#### Usage

The program receives two parameters

```bash
./app <numbers separated by comma> <target sum>
```

Assumptions

- There are no repeated numbers
- All number are integers
- The numbers are comma separated without spaces

The program can receive repeated numbers, but, this can lead to an output with repeated pairs.

#### Build

We can build the program using

```bash
go build .
```

Or, using docker

```bash
docker run --rm -v "$PWD":/app -w /app golang:1.20 go build .
```

Another option to get the binary without downloading this repository directly

```bash
go install -v github.com/RichardAlmanza/other-challenges/macheight/app@latest
```

Using Docker

```bash
docker run --rm -v "$PWD":/go/bin golang:1.20 go install github.com/RichardAlmanza/other-challenges/macheight/app@latest
```

#### Running the program

Also, Go can Build and run a temporal binary

```bash
go run . 1,9,5,0,20,-4,12,16,7 12
```

Or, using docker

```bash
docker run --rm -v "$PWD":/app -w /app golang:1.20 go run . 1,9,5,0,20,-4,12,16,7 12
```

Using the binary compiled from the build stage

```bash
./app 1,9,5,0,20,-4,12,16,7 12
```

##### Reading from a file

Given a file, where each line has the two parameters separated by space

e.g., `cases.lst`

```text
-34,-22,34,37,14,-11,-29,53,23,29,46,-33,-28 -67
-32,17,30,-16,78,-26,71,25,0,31,42,61,33,10,13,-28 31
-34,23,29,46,-32,17,30,-16,73,3,-15,-36,-8,48,76,15,-13 8
1,9,5,0,20,-4,12,16,7 12
1,9,5 6
9,3,20,28,65,29,-40,-8,55,80,70,38,64,-13,8,51,30,67,60,59 0

```

We can use bash to read the file and pass the parameters to the program

```bash
while read -r numbers target; do ./app $numbers $target; echo; done < cases.lst
```
