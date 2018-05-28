---
date: 2016-12-22T20:04:40.407Z
title: What is a generic class Dot.NET
---
At its core, a generic class is a special class that allows you to define a class with placeholders for the type of its fields, methods, parameters, etc.  Generics replace these placeholders with some specific type at compile time.  Generics were first introduced in C# 2.0.
 
A generic class can be defined using angle brackets <>. For example, the following is a simple generic class with a generic member variable, generic method and property.

<iframe width="100%" height="475" src="https://dotnetfiddle.net/Widget/L11i4X" frameborder="0"></iframe>

In the following code above, MyGenericCLass is defined with <T>.  This tells the compiler that MyGenericClass is a generic and the type will be defined later at compile time. The compiler then assigns the type based on the type passed by the caller when instantiating a class. 
 
Advantages of Generic:
1. Increases the reusability of the code.
2. Generic are type safe. You get compile time errors if you try to use a different type of data than the one specified in the definition.
3. Generic has a performance advantage because it removes the possibilities of boxing and unboxing.
