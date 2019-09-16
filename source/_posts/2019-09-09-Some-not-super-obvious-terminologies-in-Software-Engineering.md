---
title: Some not super obvious terminologies in Software Engineering
date: 2019-09-09 23:18:05
tags:
    - software engineering
    - terminology
    - design pattern
categories:
    - Software Engineering
cover:
    -
---
# Notes for some not super obvious terminologies in Software Engineering (Will keep updating) (Mostly come from the book Design Pattern)
## Also with some significant knowledge bound to those terms
- Client: The caller, executor or user of other operations/functions
- Abstract operations: the operations that an abstract class declares but doesn't implement.
- Mixin class: a class that's intended to provide an optional interface or functionality to other classes. Mixin classes require multiple inheritance. (Interface in Java)
- Reuse Mechanisms:
    - class inheritance
        - internals of parent classes are often visible to subclasses
        - white-box reuse
    - object composition
        - new functionality is obtained by assembling or composing objects to get more complex functionality
        - knows the interface (not implementation) of the composing objects
        - black-box reuse
- Delegation:
    - Wwo objects are involved in handling a request: a receiving object delegates operations to its delegates.
    - <strong>Is a good design choice only when it simplifies more than it complicates. (Dynamic, highly parameterized software introduces run-time inefficiencies and more importantly human inefficiencies, e.g. harder to understand)</strong>
- Parameterized types
     - e.g generics in Java, templates in C++
