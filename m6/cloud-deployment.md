---
title: Module 6 - Cloud
redirect_from: /m6
---

# Prepare your react app for deployment

We will now deploy our weather app to the cloud. However there are 2 parts to the app. The react client and your API.

The react client will be deployed to Zeit Now as a static site. A static site is simply a location to store the html, javascript, and css that make up our react application.

The weather API that we created will be deployed to a Serverless Function. We will only deploy the route that fetches the weather for the city and returns daily weather data as JSON.

## Create an API in your weather app

1. Start from your `weather-app` poject that you created during the last course.

   Zeit will treat any javascript files in a folder named `api` as serverless functions. Create a new file `api/weather/[city].js`

   Zeit will treat files surrounded with `[]` brackets as query parameters to the API. This will allow us to call our api with URLs like `api/weather/annecy` and `api/weather/lyon`.

1. Add the following code to the `[city].js` file:

   ```javascript
   module.exports = async (req, res) => {
   const location = req.query.city;
   console.log("LOC:", location);
   const response = await getWeather(location);
   res.send(response);
   };
   ```

   A Serverless Function has the same signature a the callback function we add to a route in an express server. Note the parameters `req` and `res`. However, we don't need an express app since Zeit Now will deploy our function automagically 😍. Instead we just need to export the function from our file.

   💡 Notice that we get the city from `req.query.city`. Zeit wil parse the city form the url and store it here.


#### Exercise 1.1: Migrate your `getWeather()` function from your express app that you refactored during the pervious exercise.

💡 If you use `axios` or `lodash` in your your function, be sure to install them with yarn:

```cmd
yarn add axios lodash
```

## Install now and test locally

1. Add cross-env so that the dev scripts work with windows (not required if you are using a mac or linux):

   ```cmd
   yarn add --dev cross-env
   ```

1. Add Zeit Now to your project as a dev dependencies:

   ```cmd
   yarn add --dev now
   ```

1. Modify your react app to work with now. We will use now to debug our app. Now will build and host the app **and** the serverless function so that we can test.

   Inside your `package.json`, inside the `dev` script add `BROWSER=none`. Your `package.json` should look like this (`cross-env` is only required if you are running on Windows):

   ```json
   ...
   "scripts": {
     "dev": "cross-env BROWSER=none react-scripts start",
     "start": "react-scripts start",
     "build": "react-scripts build",
     "test": "react-scripts test",
     "eject": "react-scripts eject"
   },
   ...
   ```

1. Test your application by running:

   ```cmd
   yarn now dev
   ```

   💡 If your build does not work, don't hesitate to try twice.


## Deploy to Zeit

1. [Create an account](https://zeit.co/signup) on Zeit with your github credentials.

1. Login with the console:
   ```cmd
   yarn now login
   ```

1. Deploy your app to now:
   ```cmd
   yarn now
   ```

1. Test your application


## Bonus: Use firestore in your app to track recent cities and or provide accounts to remember the previous city.

## Bonus: Use next.js, gatsby, or react-router to create multiple pages in your app

<!--
TODO: update creds for voting
-->
