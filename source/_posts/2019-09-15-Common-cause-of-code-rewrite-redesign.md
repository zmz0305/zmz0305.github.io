---
title: Common causes of code rewrite/redesign and the patterns to address them
date: 2019-09-15 22:16:03
tags:
    - software engineering
    - design pattern
categories:
    - Software Engineering
    - Design Pattern Notes
cover:
---
1. Creating an object by specifying a class explicitly.
    - Create objects by a specific class commits you to a particular implementation instead of a particular interface.
    - Can complicate future changes.
    - To avoid it, create objects indirectly.
    - Patterns to solve this problem:
        - Abstract Factory
        - Factory Method
        - Prototype
2. Dependence on specific operations.
    - By specifying a particular operation, you commit to one way of satisfying a request.
    - Patterns to solve this problem:
        - Chain of Responsibility
        - Command
3. Dependency on hardware and software platform
    - APIs could be different on different platforms.
    - Software that depend on one platform will be hard to port to other platforms
    - May event hard to keep up with the native platform
    - Should design the system to limit its platform dependencies.
    - Patterns to solve this problem:
        - Abstract Factory
        - Bridge
4. Dependence on object representations or implementations
    - (To be continued)
