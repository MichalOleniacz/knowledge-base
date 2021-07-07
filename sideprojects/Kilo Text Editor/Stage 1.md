**Title:** Kilo Text Editor -Stage 1
**Date:** 07-07-2021
**Tags:** #programming, #clang 
**Description / Goal:** The goal of this note is to
**External references:** [Stage 1](https://viewsourcecode.org/snaptoken/kilo/01.setup.html)

<hr>


In C, you have to put all your executable code inside functions. The `main()` function in C is special. It is the default starting point when you run your program. When you `return` from the `main()` function, the program exits and passes the returned integer back to the operating system. A return value of `0` indicates success.

To automate the build process you can use [[Makefile]].
```
kilo: kilo.c
	$(CC) kilo.c -o kilo -Wall -Wextra -		pedantic -std=c99
```
-   `$(CC)` is a variable that `make` expands to `cc` by default.
-   `-Wall` stands for “**all** **W**arnings”, and gets the compiler to warn you when it sees code in your program that might not technically be wrong, but is considered bad or questionable usage of the C language, like using variables before initializing them.
-   `-Wextra` and `-pedantic` turn on even more warnings. For each step in this tutorial, if your program compiles, it shouldn’t produce any warnings except for “unused variable” warnings in some cases. If you get any other warnings, check to make sure your code exactly matches the code in that step.
-   `-std=c99` specifies the exact version of the C language **st**an**d**ard we’re using, which is [C99](https://en.wikipedia.org/wiki/C99). C99 allows us to declare variables anywhere within a function, whereas [ANSI C](https://en.wikipedia.org/wiki/ANSI_C) requires all variables to be declared at the top of a function or block.