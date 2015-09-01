# Terence's original mail to Olga (as a memo):

We are planning to design/build a computer language with multiple implementations: generating LLVM, translating to C, generating our own bytecode. Then we’ll implement the VM for the bytecode with a sophisticated garbage collector. The language will be likely pure functional and include immutable data structure implementations as part of its library.

We can add some parallel operator implementation for vectors/matrices too.

Brainstorming:

![](images/whiteboarding.jpg)
	
# Features of the Language

Statically typed, although not necessarily explicitly typed.
Translated to other language source (like C) or LLVM IR.
Could be run on a virtual machine (thus has its own bytecode)
Source-to-source translation and interpreter version support garbage collection. (GC for LLVM-based version is to be determined.)
Has pure-functional traits, like built-in immutable data structures and vector operations (that run on GPUs).
Support for bridge to other languages like (JAVA, Python).
