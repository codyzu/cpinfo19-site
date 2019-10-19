---
title: Module 2 - Node.js Express Server
---
# 🌩 Module 2: Backend - Express with templates

Welcome.

There is a working version of this exercise [here](https://cpinfo-m2-express-pug.firebaseapp.com/).

## 1 Express hello world

```cmd
mkdir weather
cd weather

yarn init

yarn add express
```
👉 _Press enter for all of the `yarn` questions._

Create the file `app.js`:
```javascript
const express = require('express');
const app = express();
const port = 3000;

app.get('/', (req, res) => res.send('Hello CPINFO!'));

app.listen(port, () => console.log(`Example app listening on port ${port}!`));
```

💡 Tip: Enable VSCode "auto-save" feature to save your files automatically.

Test your server with `node .\app.js` and navigate to [http://localhost:3000](http://localhost:3000).

You can kill your app by pressing `ctrl+c` in the console.

## Bonus

Add nodemon to make it easier to debug your web server.

```cmd
yarn add --dev nodemon
```

💡 The `--dev` switch makes `nodemon` a "development" dependency: a dependency that is not required to use your application, but is required to develop it.

Add the following to your `package.json`:
```json
"scripts": {
  "dev": "nodemon app.js"
}
```

⚠️ _Be sure to keep the correct commas in your `package.json`._

Now run your server with:
```cmd
npm run dev
```

Try modifying the message returned in your server, save the file, and notice the server automatically restarts.

## 2 Server side templates with pug

Follow the [steps to integrate a templating engine](https://expressjs.com/fr/guide/using-template-engines.html) into your express server.

```cmd
yarn add pug
```

Add to your `app.js`:
```javascript
app.set('views', './views');
app.set('view engine', 'pug');

// Replace your existing app.get('/', ...) with this new route:
app.get('/hello', (req, res) => {
  res.render('hello-page', {title: 'Hey', message: 'Hello there!'});
});
```

Create a pug template file in `views/hello-page.pug`:
```pug
html
  head
    title= title
  body
    h1= message
```

ℹ️ Be sure to read some of the documentation about the [pug templating language](https://pugjs.org/language/tags.html).

Test your new index page by  navigating to [http://localhost:3000/hello](http://localhost:3000/hello). Open the chrome dev tools and look at the rendered HTML. Notice that the message and title and passed as variables.

Open the chrome dev tools and look at the source file.

<!-- TODO: update screenshot -->
![chrome developer tools](./images/inspect.jpg)

#### Question 2.1: What did the line `h1= message` in index.pug render to in HTML?

## 3 Static Files

Follow the [steps to add static files](https://expressjs.com/fr/starter/static-files.html) into your web server.

Add the following configuration into your `app.js`:
```javascript
app.use(express.static('public'));
```

Add some image files from the internet (3 or 4) into the directory `public/images`.

Test your static files by navigating to [http://localhost:3000/images/abc.jpg](http://localhost:3000/images/abc.jpg)

#### Exercise 3.1: Add a new pug view at `views/originals.pug` that renders an html document that dynamically includes each image in an `img` tag and is served at [http://localhost:3000/originals](http://localhost:3000/originals).

#### Hints:

* pug can iterate over an array of values by using the [`each`](https://pugjs.org/language/iteration.html#each) keyword.
* Using the same mechanism that allowed us to pass the `message` and `title` variables to the template, we can pass an array of image paths.
* You will have to load the image paths using the `fs` module (refer to the code you wrote during the previous course).
* The goal is to render an `<img src="images/..." />` tag for each image in your images directory. Refer to the [pug documentation](https://pugjs.org/language/attributes.html) for how to set attributes with pug.


## Call an API

Install [axios](https://github.com/axios/axios):
```cmd
yarn add axios
```

Axios will let us call other APIs.

#### Exercise 3.2: Add a new route `/thumbs/:image` that renders a resized (200x200 max) version of an image using Jimp.

#### Hints:

* Be sure add Jimp to your project with `yarn add jimp`
* Jimp can return a binary buffer (a file in memory) by using the [`image.getBufferAsync()`](https://github.com/oliver-moran/jimp/tree/master/packages/jimp#writing-to-buffers) method.
* Express can send a binary buffer by calling [`res.send(buffer)`](https://expressjs.com/fr/4x/api.html#res.send). However, you will need to set the content type by calling [`res.type()`](https://expressjs.com/fr/4x/api.html#res.type) before sending the buffer. This allows your browser to decide what to do with the binary file, i.e. display the image.
* Both methods jimp `image.getBufferAsync()` and express `res.type()` requires the mime type to be sent. Fortunately, jimp has a method [`image.getMIME()`](https://github.com/oliver-moran/jimp/tree/master/packages/jimp#writing-to-buffers) that will return the mime type of the original image.

#### Exercise 3.3: Add a new pug view at `views/thumbnails.pug` that renders each image, but with `src` urls pointing to the `/thumb/xyz.jpg` and is served at [http://localhost:3000/thumbnails](http://localhost:3000/thumbnails).

#### Hints:

* This exercise is similar to Exercise 3.2, except you will change the `src` attribute in the `<img />` tags to use the `/thumbs/:image` route that you added in Exercise 3.2.

## Bonus: Debugger

In Visual Studio Code:
* Click on Debug->Add Configuration...
* Choose Node.js
* Update the launch configuration `program` to launch your app, i.e. `"${workspaceFolder}/index.js"`
* Add a breakpoint into your code
* Click on the debugger on the left of the screen and start debugging

