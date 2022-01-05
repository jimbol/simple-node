# How to start a new NPM project

- Install node and npm. They are packaged together [here](https://nodejs.org/en/download/).
- Open a terminal window and find the directory you want to work in.
- Run `npm init` in that folder and answer the questions. This will create a `package.json` file.
- Create an `index.js` file. This is where we will start writing code!

You dont need a package.json file to run a node script. You can just create a script and run `node script.js`. However you need a package.json to install dependencies like third party libraries.

## Sample project

Lets make a simple API server!

- Install the third-party library "[ExpressJS](https://expressjs.com/)" which lets us run a node server.
- Run `npm install express`. This will add Express to our `package.json` file and will include the library in the `node_modules` file.
- Inside our `index.js` file include the following code:
```js
const express = require('express')
const app = express()
const port = 3000

app.get('/', (req, res) => {
  res.send('Hello World!')
})

app.listen(port, () => {
  console.log(`Example app listening at http://localhost:${port}`)
})
```
[Source](https://expressjs.com/en/starter/hello-world.html)

- Modify the `package.json`'s `script` block:

```json
"scripts": {
  "start": "node index.js"
},
```

- Run `npm start`. Alternatively you can just run `node index.js`, but using the `package.json` is preferable.
- Visit [http://localhost:3000/](http://localhost:3000/) and see it in action!
