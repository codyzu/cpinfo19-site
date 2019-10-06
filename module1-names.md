---
title: Module 1 - Prenoms Exercise
---
# 🔍 Query CSV data

For this activity, we will use the [Ficher des prénoms](https://www.insee.fr/fr/statistiques/2540004) data from INSEE.

⚠️ Download the file from the prof for the fastest results!

## 1.0 Parsing a text file

The file is CSV (comma separated values) format. It is very easy to parse with node.js.
Refer to the [documentation](https://www.insee.fr/fr/statistiques/2540004#documentation) for an explanation of the data in the file.

We can synchronously read a file using the node.js [`fs.readFileSync()` function](https://nodejs.org/docs/latest-v10.x/api/fs.html#fs_fs_readfilesync_path_options). This function is synchronous, meaning it will block execution of the program until the entire file is read.

```javascript
const fs = require('fs');

const fileText = fs.readFileSync('./nat2018.csv', 'utf8');
```

We set the encoding to `utf8` since we want to read the file as an UTF8 text string.

## 1.1 String manipulation

Now that the entire file is read into a string, we can manipulate the string into a data structure that will be useful for us.

```javascript
const lines = fileText.split('\n');
const tokens = lines.map(line => line.trim().split(','));
```

### Reference

To understand the above code, here are links in French and English to documentation about the various JavaScript functions:
* [`Array.prototype.map()`](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Objets_globaux/Array/map)<sup>[en](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)</sup>
* [`String.prototype.split()`](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Objets_globaux/String/split)<sup>[en](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/split)</sup>
* [`String.prototype.trim()`](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Objets_globaux/String/Trim)<sup>[en](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/Trim)</sup>

🐛 We can debug any variable by writing to the console, i.e. `console.log(tokens)`.

We can combine all of the previous lines of code into 2 lines:
```javascript
const fs = require('fs');

const data = fs
  .readFileSync('./nat2018.csv', 'utf8')
  .split('\n')
  .map(line => line.trim().split(';'));
```

The results is a 2 dimensional array containing the name data. The data looks like this:

```javascript
[
  ['1', 'ALBERT', '1983', '23'],
  ['2', 'MADELEINE', '2012', '193']
]
```

### Exercise 1.0 Query the total number of times the prenom `CODY` has been used in France.

### Hints

The following functions will help you write "filter" then "count" (reduce) the data.

* [`Array.prototype.filter()`](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Objets_globaux/Array/filter)<sup>[en](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)</sup>
* [`Array.prototype.reduce()`](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Objets_globaux/Array/reduce)<sup>[en](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce)</sup>
* [`Number.parseInt()`](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Objets_globaux/Number/parseInt)<sup>[en](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/parseInt)</sup>

### Exercise 1.1 How many times has your prenom been used in France? (If you prenom isn't found, use your neighbor's)?

### Exercise 1.2 In what year was your prenom most popular?

### Exercise 1.3 What is the most popular prenom of all time in France?
