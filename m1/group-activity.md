---
title: Java vs JavaScript
---

# 1 Java vs JavaScript

![java vs javascript](images/group1-java-vs-javascript.jpg)

| |java|javascript|
|-|-|-|
|**Execution**|bytecode executed in JVM|script interpreted|
|**Compilation**|source code compiled to byte code (type checking)|sometimes transformed and/or compressed (minimized), but compilation not necessary|
|**Types**|statically typed|dynamically typed|
|**Numeric types**|byte, short, int, long, float, double|Number, BigInt|
|**Portability**|"write once, run anywhere" (still depends on JVM version and implementation)|Was horribly fragmented, today much better thanks to ECMA|
|**OOP**|Everything is OO|possible with prototypes|
|**Inheritance**|OO Class|prototypal|
|**Concurrency**|Thread model|Async callbacks with event loop|
|**First class functions**|"kind of" since java 8|Yes|
|**Function overloading**|Yes|"kind of" with ... rest operator in args|
|**XML + JSON**|XML is a language. XML parsing supported out of the box. JSON OK|JSON is a format (not a language). JSON is a subset of JS (is JS). XML possible via npm.|
|**Exception Handling** (try, catch, finally)|Yes|Yes|
|**Deployment / Scaling**|typically big server, scaled horizontally (add CPU+mem, i.e. add floors to building)|typically containerized, scaled vertically (add instances, i.e. add building to neighborhood)|

# 2 What is node.js

![node.js](images/group2-nodejs.jpg)

* **History**
  * 1995: Brendan Eicht 👉 Netscape
  * "LiveScript" -> "JavaScript" (marketing)
  * 1997: ECMAScript standard 1
    * es3, ~~es4~~, es5, es2016, ..., es2019
  * **JavaScript is ECMAScript** 
  * Google Chrome v8
  * 2009: Ryan Dahl 👉 node.js
  * **Containerization**
  * 2013: Docker
  * 2014/2015: Kubernetes
  * **Serverless / `FaaS`**
  * 2010: PiCloud (python)
  * 2014: Amazon AWS
  * 2016: MS Azure Functions (GA)
  * 2018: Google Cloud Functions (GA)
* **Under Attack! 💣 🔫 ⚔️ Competition**
  * Microsoft: JScript, silverlight, asp.net, typescript
  * Adobe: flash
* **Node.js is a JavaScript engine (Google's v8) with a collection of modules that allow file system access, networking, and other functionality required to create applications.**
* No relation to Java (marketing), but certainly inspired by Java
* Managed by Linux Foundation (OpenJS Foundation)
* Allows same language on client and server

# 3 Types in JavaScript

![js types](images/group3-js-types.jpg)

**📢 JavaScript is dynamically typed 🚨**

Theoretic types:
* Number
  * IEEE 754 Floating Point
  * ⚠️ Careful with rounding, i.e. money!!!
    ```javascript
    ((0.1 + 0.2) + 0.3) === (0.1 + (0.2 + 0.3)) // false
    ```
* String
  * use "backquotes" '`' for string interpolation:
    ```javascript
    const name = 'cody';
    const location = 'annecy';
    const message = `${name} is in `${location}`;
    ```
* Boolean
* Object
  object literal:
  ```javascript
  const user = {
      name: 'cody',
      address: {
          city: 'annecy'
          code: 74000
      },
  };
  ```
* Array
* `null` & `undefined`
  * both represent "no value"
  * prefer `undefined` because it is built into the langauge

Inheritance:
* JavaScript uses "prototypal inheritance" (subtle difference from class based inheritance)
* The `class` keyword makes JavaScript appear like Java inheritance (even though it uses prototypes)

# 4 What is npm

![npm](images/group4-npm.jpg)

* npm registry is a public registry of node.js packages
* npm cli tool is a tool to install/manage packages from the registry
* yarn is an alternative cli tool