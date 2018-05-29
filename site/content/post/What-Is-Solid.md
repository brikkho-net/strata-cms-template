---
date: 2016-12-22T20:04:40.407Z
title: What is SOLID
---
S.O.L.I.D is an acronym for the first five object-oriented design(OOD) principles by Robert C. Martin aka Uncle Bob. 

<ul>
<li><strong>S</strong> - Single-responsiblity principle (SRP)</li>
<li><strong>O</strong> - Open-closed principle</li>
<li><strong>L</strong> - Liskov substitution principle</li>
<li><strong>I</strong> - Interface segregation principle</li>
<li><strong>D</strong> - Dependency Inversion Principle </li>
</ul>

S.R.P states that "A class should have one and only one reason to change, meaning that a class should have only one job."

Open-closed Principle states that "Objects or entities should be open for extension, but closed for modification."  
This simply means that a class should be easily extendable without modifying the class itself. 

Coding to an interface is an integral part of S.O.L.I.D

Liskov substitution principle states Let q(x) be a property provable about objects of x of type T. 
Then q(y) should be provable for objects y of type S where S is a subtype of T.

All this is stating is that every subclass/derived class should be substitutable for their base/parent class.

Interface segregation principle - A client should never be forced to implement an interface that it doesn't use or clients shouldn't be forced to depend on methods they do not use.

Dependency Inversion principle states that Entities must depend on abstractions not on concretions. It states that the high level module must not depend on the low level module, but they should depend on abstractions.
This principle allows for decoupling.
