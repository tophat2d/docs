# extensions tutorial

Umka allows programmers to extend their applications by dynamically loading
shared libraries, also known as UMIs. Tophat builds on this functionality by
making it possible to call tophat functions in these extension libraries.
Extensions are useful for optimizing critical parts of your game, or to access
system functions, which are not in tophat or Umka. This tutorial will show you
how to create a simple extension. I recommend reading this
[guide](https://github.com/vtereshkov/umka-lang/blob/master/doc/api.md)
alongside this tutorial.

> NOTE: Extensions currently don't work on Web

## step 1: creating the umka API

First you need to decide what functions you want your extension to implement.
Then you need to add their prototypes to an umka file. This tutorial will show
these two functions:

```umka
fn printHello()
fn add(a, b: int): int
fn initExt(thg, funcs: ^struct{})
```

`printHello` will draw text using `th_canvas_text`. `add` will add the two
numbers and return the result. `initExt` is used to initialize the extension, I
will get to that later.

## step 2: implementing the extension

Now we can implement the functions. Create a c file
