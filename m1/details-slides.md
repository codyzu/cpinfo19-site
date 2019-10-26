# Web ☁️ Development
---

---

# 👊 JS vs Java
---
## or .NET


## vs Java
* no relation to Java
* "JavaScript" 👉 marketing
* _inspired_ by Java


<!-- .slide: data-background-image="./images/marker.png" data-background-size="auto 7%" data-background-position="bottom" data-background-opacity="0.70" -->
vs Java
<small>

* Execution
* Compilation
* Types
* Portability
* Numeric types
* OO
* Inheritance
* Concurrency
* Function overloading
* First class functions
* XML + JSON
* ~~Exception Handling (try, catch, finally)~~
* Deployment / Scaling

</small>


| |java|javascript|
|-|-|-|
|Execution|bytecode executed in JVM|script interpreted|
|Compilation|source code compiled to byte code (type checking)|sometimes transformed and/or compressed (minimized), but compilation not necessary|


Types
statically typed
dynamically typed
Portability
"write once, run anywhere" (still depends on JVM version and implementation)
Was horribly fragmented, today much better thanks to ECMA
OO
Everything is OO
possible with prototypes
Inheritance
OO class
prototypal
Concurrency
Thread model
Async callbcks with event loop
First class functions
"kind of" since java 8
Yes
Function overloading
Yes
"kind of" with ... rest operator in args
Numeric types
byte, short, int, long, float, double
Number, BigInt
XML + JSON
XML is a language. XML parsing supported out of the box. JSON OK 
JSON is a format (not a language). JSON is a subset of JS (is JS). XML possible via npm.
Exception Handling (try, catch, finally)
Yes
Yes
Deployment / Scaling
typically big server, scaled horizontally (add CPU+mem)
typically containerized, scaled vertically (add instances)

---

# How to 💡 JavaScript
---
This course 👈 **modern** JavaScript (ECMAScript)

---

# Types 🎟
---


* Number
* String
* Boolean
* Object
* Array


* Number
* String
* Boolean
* Object
  * Function
  * Array
  * Date
  * RegExp
* null
* undefined


# Number 🔢
* IEEE Standard for Floating-Point Arithmetic (IEEE 754)
* "only 1" number type (+ BigInt)
* parseInt, parseFloat
* NaN
* safe integer range
* FP math
* math built-in


# String 🔤
* similarities to Java
* String.prototype
* `a + b` vs `${}`
* searching
* RegExp


# Boolean ✔️ ❌
* comparison operators
* don't use `==` and `!=`
* Boolish
* `!`, `&&`, `||`
* `NaN`, inverse comparison, De Morgan's


# Object 📦
* everything excpet `null` and `undefined`
* similar to hash table, map, record, struct, dictionary
* object literals `{}`
* keys
* Object.assign()
* Object.prototype
* Object.freeze()


# Array 📜
* "spcial" Object: magic length
* creation
* `typeof` vs `Array.isArray()`
* destructive operations
* Array.prototype
* functional
* sorting
* concatination and substrings


# `null` & `undefined` ❓
* `||` & `&&`
* 2 bottom values
* language uses undefined (let, uninitialized args)
* typeof
* use `undefined` unless required
  * `Object.create(null)`
  * `JSON.stringify({}, null, 2)`

---

# Variables & Scope 👀
---


# scope
* global
* module
* function
* block


# Variables
* var
* let
* const


# `'use strict'`
* es5
* why?
* examples
* babel

---

# Control Structures 🔁
---


* conditional `if` & ternary
* loops
  * for, while, do
  * break, continue 😑
  * consider `while(true)` to allow breaking where needed
* switch


# recursion & tail calls
* es6 (but not implemented 😿)
* only if function returns result of calling a function
* optimation: recusrsion as fast as loops

---

# Functions 📞
---


* default arguments
* declarations vs expressions
* this
* function objects

---

# Inheritance
# 👴 👨 👶
---


# Classes
* What is a class?
* C++ Classes
* Java Classes


# Prototypal Inheritance
* objects inherit from other objects
* no "vtable"
* lighter and expressive compared to class inheritance


* objects are containers of properties
* prototypes are objects
* methods are functions, stored in objects
* missing props 👉 undfined, unless prototype exists


* many object can share same prototype
  * _similar_ to classes
* prototypes typically store methods
  * similar objects 👉 similar methods
  * saves memory
* `this`:
  * lets prototype methods now which object
  * dynamically bound ⚠️


# JavaScript Inheritance


## legacy construtors 👎
* magic `new` operator


## class 👍 👎
* "syntatic sugar" over legacy construtors, not true classes
* `this` or that?
* useful for migrating from other languages


## factories 👍
## 🏭
* memory?
* encapsulation with closures (private vars possible)
* no `this` 👉 no errors


<!-- .slide: data-background-image="./images/typescript.png" data-background-size="auto 10%" data-background-position="bottom" data-background-opacity="1" -->
# Typescript
* MS
* requires annotations (allows interfaces)
* large project with big teams
* static type controversy

---

# Semicolons `;`
---
* Automatic Semicolon Insertion (ASI)
* danger! ☣️

---

# Bonus: FP
---
* 1st class functions
* dividing

---

# Homework (Devoir)
---
1. create google account
1. create github account
1. email me:
  * google email address
  * github username
