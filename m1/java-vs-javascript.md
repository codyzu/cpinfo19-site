---
title: Java vs JavaScript
---

# Java vs JavaScript

| |java|javascript|
|-|-|-|
|Execution|bytecode executed in JVM|script interpreted|
|Compilation|source code compiled to byte code (type checking)|sometimes transformed and/or compressed (minimized), but compilation not necessary|
|Types|statically typed|dynamically typed|
|Portability|"write once, run anywhere" (still depends on JVM version and implementation)|Was horribly fragmented, today much better thanks to ECMA|
|OOP|Everything is OO|possible with prototypes|
|Inheritance|OO Class|prototypal|
|Concurrency|Thread model|Async callbcks with event loop|
|First class functions|"kind of" since java 8|Yes|
|Function overloading|Yes|"kind of" with ... rest operator in args|
|Numeric types|byte, short, int, long, float, double|Number, BigInt|
|XML + JSON|XML is a language. XML parsing supported out of the box. JSON OK|JSON is a format (not a language). JSON is a subset of JS (is JS). XML possible via npm.|
|Exception Handling (try, catch, finally)|Yes|Yes|
|Deployment / Scaling|typically big server, scaled horizontally (add CPU+mem)|typically containerized, scaled vertically (add instances)|
