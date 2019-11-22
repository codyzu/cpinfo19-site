## 1 Adding admin access to Firestore to exprss

1. [https://console.firebase.google.com](https://console.firebase.google.com)

1. Sign in to your google account

1. "Add project"

1. Give your project a unique name, i.e. "weather" and _disable_ Google Analytics.

1. Add firebase to your project and login:
   ```
   yarn add firebase-tools
   yarn firebase login
   ```

1. Add hosting and cloud functions to your project:
   ```
   yarn firebase init
   ```
   1. Select (press space bar) on "Hosting" and "Functions", then press enter
   1. `Use an existing project` 👉 select your project
   1. `JavaScript`
   1. Use ESLint? `y`
   1. Install dependencies now? `n`
   1. What do you want to use as your public directory? `client/build`
   1. Configure as a single-page app? `y`

1. Build your react project
   ```
   cd client
   yarn build
   ```
1. Deploy your site
   ```
   cd ..
   yarn firebase deploy --only hosting
   ```

