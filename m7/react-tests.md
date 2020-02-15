---
title: Module 7 - React Tests
redirect_from: /m7
---

# Module 7 - React Tests

## Test your App

1. Separate your `src/App.js` and `src/index.js` files

   - `index.js` should contain:

     ```jsx
     import React from "react";
     import ReactDOM from "react-dom";
     import App from "./App";

     ReactDOM.render(<App />, document.getElementById("root"));
     ```

   - `App.js` should contain everything else that was previously in your index.js file and export the root of your app:

     ```jsx
     import React, { useState, useEffect } from "react";

     // Everything else...

     export default App;
     ```

   - ⚠️ If your root component is named `Weather`, replace `App` with weather above

1. Add `src/App.test.js` to test your `src/App.js` file:

   ```jsx
   import React from "react";
   import "@testing-library/jest-dom/extend-expect";
   import { render } from "@testing-library/react";
   import App from "./App";

   test("renders search element", () => {
     // Render the application
     const { getByText } = render(<App />);

     // Ensure the search button is displayed
     const searchElement = getByText("Search");
     expect(searchElement).toBeInTheDocument();
   });
   ```

   - This uses [@testing-library/react](https://testing-library.com/docs/dom-testing-library/api-queries) to get elements in the DOM.
   - We can also [fire events](https://testing-library.com/docs/dom-testing-library/api-events) like mouse clicks or entering text.

1. Run your tests by running `yarn test` in the console.

## Test with mocks

We use [jest](https://jestjs.io/) to run our tests. Check out the [docs](https://jestjs.io/docs/en/getting-started) to learn some of the incredible things that jest lets us do for tests.

We can "mock" functionality of our application to isolate the code we want to test. For example, to test that our react application shows the results from axios, we should mock axios. This way our tests _only_ test our code. If the test fails, then we know we have broken something in our code.

1. For this test we will enter a city into the search input box. In order to find the input box, we have to add a special tag to identify it.

   Inside your `App.js` add a `data-testid` tag to your `<input>` tag:

   ```jsx
   <input
     type="text"
     onChange={e => debounceSearch(e.target.value)}
     placeholder="City"
     data-testid="city-input"
   />
   ```

1. Use jest to mock the `axios` module inside your `App.test.js` and import it:

   ```jsx
   import React from "react";
   import "@testing-library/jest-dom/extend-expect";
   import { render, fireEvent, act, wait } from "@testing-library/react";
   import App from "./App";
   import axios from "axios";

   jest.mock("axios");

   // test(...) ...
   ```

1. Now add a more complicated test to simulating a search:

   ```jsx
   test("searches for a city", async () => {
     // Mock the API call
     axios.mockImplementation(() => ({
       data: { daily: { summary: "Hello", data: [{ time: Date.now() }] } }
     }));

     // Render the application
     const { getByText, getByTestId } = render(<App />);

     // Input "Lyon"
     const cityInput = getByTestId("city-input");
     fireEvent.change(cityInput, { target: { value: "Lyon" } });
     expect(cityInput.value).toEqual("Lyon");

     // Click on the "Search" button
     const searchElement = getByText("Search");
     expect(searchElement).toBeInTheDocument();
     fireEvent.click(searchElement);

     // Wait for the mocked data to be displayed
     await wait(() => getByText("Hello"));
     expect(axios).toHaveBeenCalledWith("/api/weather/Lyon");
   });
   ```

#### Exercise 1: Add the mocked data and assertions to test the rest of the weather display.

#### Exercise 2: Add tests to test `[city].js`. Consider adding a `[city].test.js` file.
