# Terence's original mail to Olga (as a memo):

We are planning to design/build a computer language with multiple implementations: generating LLVM, translating to C, generating our own bytecode. Then we’ll implement the VM for the bytecode with a sophisticated garbage collector. The language will be likely pure functional and include immutable data structure implementations as part of its library.

We can add some parallel operator implementation for vectors/matrices too.

Brainstorming:

![](images/whiteboarding.jpg)
	
# Initial thoughts of the Language

Statically typed, although not necessarily explicitly typed.
Translated to other language source (like C) or LLVM IR.
Could be run on a virtual machine (thus has its own bytecode)
Source-to-source translation and interpreter version support garbage collection. (GC for LLVM-based version is to be determined.)
Has pure-functional traits, like built-in immutable data structures and vector operations (that run on GPUs).
Support for bridge to other languages like (JAVA, Python).

# Syntax and semantics

## Expressions

The basics; ints, floats, strings

```javascript
var x = 1	       // type inference of int
var y = x*2.34   // type inference of float
print(abs(y))
var z = "hi"
```

Vectors of floats

```javascript
var X = [1, 2.3, 99.0024]
print(X*3)       // overload operators for vec-scalar, vec-vec
print(X+X)
print(X . X)     // dot product; period with spaces around it
sin(3.14)
sin(X)           // like R and numpy, apply sin() to all X
```

## Statements

## Functions

Semantics are pass by value but implemented as pass-by-reference?

Copy-on-write semantics private to function?

```javascript
func dub(x : int) : int { return x*2 }
```