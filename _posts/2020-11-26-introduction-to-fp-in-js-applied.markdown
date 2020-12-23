--- 
layout: post 
title:  "Introduction To Functional Programming in Javascript: Examples" 
date:   2020-11-26 08:06:07 +0200 
categories: uncategorized 
author: Stephane Kibonge 
--- 



<br>

## Introduction

As we discussed in our previous post [here](/posts/introduction-to-fp-in-js-concepts), functional programming (FP) has been around for a long time. Lately, the concepts that form its foundation are being popularized. The software development community seem to agree that there are advantages to FP in the current context. It might not be the case that OOP can be totally replaced, but it is certainly the case that introducing elements and concepts from FP into our everyday programming can substantially help make better code, with less bug, easier to test and maintain, more modular. Due to their structure, FP program naturally lend themselves to parallel and distributed computing. Parallel and distributed computing are requirements that are becoming more and more concerns when designing modern applications.


One of these foundational concepts is that of side effects. FP aims at avoiding side effects as much as possible. However, the previous post put in evidence that even though "avoiding side effects" is a beautiful idea, it is not a practical one. Real applications need side effects to be relevant. Pure functions, referential transparency, immutability are beautiful concepts that bring code closer to mathematical constructs but at one point code needs to interface with a database, write to file, request data over the network. The data in our application must change, one way or another. For years, we have used OOP and are used to its ways of thinking.

The question is then how do we reconcile these 2 school of thought in our everyday code. That's what we will explore in this article in the context of Javascript.

<br>

## Javascript and Functional Programming

Javascript was created in 1995 by Brendan Eich to work in the browser. His initial inclinations on the subject were to have Javascript be Scheme with a twist: Scheme is a dialect of LISP which is a declarative language. And he conceived that Javascript would be a flavor of Scheme running in the browser. 
<br>It was only later on that Eich was told that Javacript would be a scripting Language that would evolve side by side with Java. In contrast to LISP, Java os an Imperative Language written from the ground up for Object Oriented. As a matter of fact, support for OOP was one of the specifications of its creation.

Consequently, Javascript saw collide ideas and concepts from both these schools of thoughts. The thing that emerged out of this clash of worlds is Javascript as we know it: 
> A Multi-paradigm language that allows some flavor of Object Oriented along with some Functional Programming concepts such as ***First-Class Functions***

<br>

This make Javascript an excellent candidate for someone who wants to dip his toes into Functional Programming.

<br>

## FP's Take on traditional programming elements

Traditionally, an imperative programming language has the following elements:
- Operators (Arithmetic, Bit, Ternary, Assignment): Add, multiply, modulus, OR and bitwise OR, ...
- Conditional Branching: if, switch statements
- Loops: for, for ... of, for ... in, while, do ... while
- Variables Declaration: aka application state
- Function

FP is pretty opinionated about some of these elements. In fact, there are things which are an absolute no-no as far a FP is concerned. There are others that FP will frown upon without necessarily say no.

Among the things that one should forget while writing in FP

|Programming Element| FP's View|
|-|-|
|Loops: <br>for, for ... of, for ... in, while, do ... while| Avoid at all cost. <br>Instead use map, filter, reduce|
|Variables Declaration: <br>let, var| Avoid at all cost. <br>Instead use const, or add Object.freeze(). See *Assignment Operator* entry below|
|Assignment Operator:<br>x = 5 or person = {name: "my name", age: 25}| Try to limit as much as possible. <br>Try using with const, or add Object.freeze()<br> const x = 5 or let person = Object.freeze({name: "my name", age: 25})|
|Object Mutation: <br>person.name = "new name"| Avoid at all cost. <br>Instead create a new copy of the object with the updated properties|

The most important thing to keep in mind are two fold:
- Avoid mutability of your variables as much as possible
- Avoid side effects in your functions as much as you can


## When Functional Programming must be broken

There are cases where side effects are necessary, when state need to change. And the most common pattern for dealing with these are:
- Be an informed pragmatic, and not a blind purist
- Provide built-ins function that handle impure code and side effects
- And obviously, use them as little and as strategically as possible.

## Examples




## References
1. [https://opensource.com/article/17/6/functional-javascript](https://opensource.com/article/17/6/functional-javascript)
1. [https://medium.com/javascript-scene/the-forgotten-history-of-oop-88d71b9b2d9f](https://medium.com/javascript-scene/the-forgotten-history-of-oop-88d71b9b2d9f)
1. [https://spin.atomicobject.com/2019/08/29/functional-prog-pros-cons/](https://spin.atomicobject.com/2019/08/29/functional-prog-pros-cons/)
1. [https://spin.atomicobject.com/2019/08/22/functional-programming-patterns/](https://spin.atomicobject.com/2019/08/22/functional-programming-patterns/)
1. [https://livecodestream.dev/post/2020-06-05-15-must-know-javascript-array-methods/](https://livecodestream.dev/post/2020-06-05-15-must-know-javascript-array-methods/)

[//]: # 1. https://stackoverflow.com/a/2835936/9034699
[//]: # 1. https://medium.com/better-programming/fp-toy-7f52ea0a947e
[//]: # 1. https://stackoverflow.com/questions/8406261/most-common-pattern-for-using-a-database-in-a-functional-language-given-desire
[//]: # 1. https://medium.com/swlh/a-comprehensive-look-at-functional-programming-fp-4a87629ecaed
[//]: # 1. https://developer.ibm.com/languages/python/articles/l-prog/
[//]: # 1. https://livebook.manning.com/book/functional-programming-in-c-sharp/chapter-6/26
[//]: # 1. https://medium.com/@geisonfgfg/python-functional-programming-8158f736935b