---
date: 2016-12-22T20:04:40.407Z
title: Whats the difference between Expression> and Func<>?
---
The key differences between the two are following:

Expression<Func<…>> is an expression tree which represents the original source code (it is stored in a tree-like data structure that is very close to the original C# code). In this form, you can analyze the source code and tools like LINQ to SQL can translate the expression tree (source code) to other languages (e.g. SQL in case of LINQ to SQL, but you could also target e.g. JavaScript).
Func<…> is an ordinary delegate that you can execute. In this case, the compiler compiles the body of the function to intermediate language (IL) just like when compiling standard method.

Func<T> creates an executable function.

Expression<Func<T>> creates an expression tree that allows you to work with the code in the function as data.

Expression Trees allow you to do things like LINQ to SQL and LINQ to XML by generating the underlying calls from your .NET code.
