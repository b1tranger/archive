
### Index
- 1. Compilers, Architectures, and Harmoney between mixed tech - Sakibul Hakim | [jump](#1-compilers-architectures-and-harmoney-between-mixed-tech---sakibul-hakim)
- 



# 1. Compilers, Architectures, and Harmoney between mixed tech - Sakibul Hakim | [jump](#index)

https://www.facebook.com/share/p/15tjQEEV9G/

Sakibul Hakim
November 3 at 11:57 AM
 ·
We often encounter codebases where a particular application is written in multiple languages. It is understandable in some cases. Such as, in web application we can understand that the backend is written in Java using Spring Boot or in Python using Django and the frontend design and logic is written in JavaScript using React or VueJS, HTML, CSS. But in many cases it seems like a magic especially when a single executable is written in several different languages.

To understand how this mixing works we need to first understand how the Compiler works. There are compilers for every compiled programming languages. Let's take the GCC compiler, which is the compiler for C language (also supports other languages e.g. C++, ada etc).

When we compile using GCC we get an executable output of our written program. But interestingly the executable file isn't the direct and only output of the compiler. The compiler goes through several steps and creates several temporary files in the process. But only lastly outputs the executable file.

The GCC compiler goes through four intermediate steps to get to the final output. They are: Pre-processing, Compiling, Assembly, Linking. Total number of intermediate processes can be different compiler to compiler. In the pre-process, compiler removes all the comments, adds the included standard codes. At this step, the file is still a C code. In compiling step, the C code gets translated into Assembly Language. Assembly language is closer to the machine code but still human readable. Then the assembly file gets assembled into binary (`1s` and `0s`) using Assembler. After all these steps, there's a huge chance that we will have multiple object files which are linked with one another in some way. The Linker links those objects together also adds the needed 3rd party binaries to the object files which gives us the final output. 

Different compiler compiles source code in different ways. But most of them has the Linker in common. It is possible to add object files created from different languages to link together in this stage. For example, we can write a Rust program that process the given input from the user and calls a function that is written in C. We would be creating a object file for each program written in different language and pass those object in the linker to get the complete merged binary.

Creating an application with different languages can have several advantages. Increasing performance is one of the main. Different programming languages have different features. Some of them run fast in computer, some of them are easy to write for development, some have more security etc. So by creating different parts of a program by different programming languages developer can harness features of several programming languages for their application. For example, one can write the whole application using Java for Object Orient Language support but use C for resource intensive parts.  

There are also possible issues that we need to keep our eye on while gluing languages together. While compiling to Assembly or some other lower level language, compiler can make assumptions differently such as assigning values to different register. One compiler can assign it's values to `r1` and `r2` registers by default, another compiler can assign it's values to `r0` and `r1` registers. If those object files are merged together, they will show unexpected behaviors. Also, by default some programming language stores information in register following pass by reference rule and others follow pass by value rule. This also creates unexpected behavior. It's clear that these miscommunications must be fixed in order to write programs in two different languages. Good luck for us, programming language creators are aware and they almost always keep a way around this (look **ABI**). Usually, there is a keyword which indicates that this part of the program is written in another language.

Mixing different programming languages is pretty straight forward if we know how to do it. Even though there are some potential issues regarding it but almost every modern language has support for this use case to minimize the issues regarding it. We now see many well known application doing this because developers find this technique more useful in contrast of it's potential risks for the product success.

Sakibul Hakim
Nov 3, 2025
