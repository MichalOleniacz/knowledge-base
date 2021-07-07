**Title:** Basics concepts of Makefile
**Date:** 07-07-2021
**Tags:** #programming, #lowlevelprogramming, #makefile
**Description / Goal:** The goal of this note is to get a basic understanding of how Makefile works.
**External references:**

<hr>

## What's `make`
`make` is a utility program that performs a set of predefined instructions listed in `Makefile`

## Step 0: Installing
In order to use Makefiles, you need to install `make`:
```bash
sudo apt install make
```

## Step 1: Hello world
`Makefile`:
```Makefile
say_hello:
	echo "Hello World"
```

After running `make` in a directory with the file shown above, we make it execute the instructions:
```bash
$ make
echo "Hello World"
Hello World
```

### What happens under the hood:
In this example, `say_hello` acts like a function name, as in any programming language. This is the **target**. To add dependencies to the instruction (think, source code files etc.) add them after the target.
```Makefile
target: dependencies
	instructions
```

You can add other targets (functions) as a dependancy of your main (or any other target).

Example:
```Makefile
final_target: sub_target final_target.c
	instructions for final_target
	
sub_target: sub_target.c
	instructions for sub_target
```


## Step 2: Multiple targets
```Makefile
say_hello:
	@echo "hello world"
	
generate:
	@echo "Creating empty text files..."
	touch file-{1..10}.txt

clean:
	@echo "Cleaning up.."
	rm ./*.txt
```

In this example, running `make` will only exectue `say_hello`.

### What happens under the hood:
`Makefile` sets the default target to the first defined target. Once `make` is called, it'll look for the default goal. This is the reason why in most projects you'll see `all` as the first target. By convention, it's the responibillit of `all` to call other targets. 

It's possible to override this behaviour by creating a special phony target called `.DEFAULT_GOAL`.

By adding it do the file, it'll change the default target like shown:
```Makefile
.DEFAULT_GOAL := generate

say_hello: 
	...
	
generate:
	...
```

With this configuration, `generate` becomes the default target.

It's not ideal to use, therefore replacing it with `all` makes the program run as intended.
It's worth noting that `clean` should not be called every time. We can call it manually once we add `.PHONY` goal listing all possible targets:

```Makefile
.PHONY: all say_hello generate clean
all: say_hello generate 

say_hello:
	...

generate:
	...
	
clean:
	...
```
With such config, running `make` should invoke `say_hello` and `generate`, and running `make clean` should invoke `clean`.