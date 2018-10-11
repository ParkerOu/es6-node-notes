# Optional Setup
## 1. Install webpack-dev-server
- For development only. Creates a development server
```sh
npm i webpack-dev-server --only=dev
```
### Setup package.json
```
  ...
  "devDependencies": {},
  "scripts": {
+    "server": "webpack-dev-server --mode development",
      ...
  },
```
### Create webpack.config.js
```
  webpack-demo
  ...
  |- package.json
+ |- webpack.config.js
```
## 2. [Setup webpack.config.js](https://webpack.js.org/guides/getting-started/#using-a-configuration)
```js
const path = require('path');

module.exports = {
  entry: path.resolve(__dirname, 'src'),
  output: {
    path: path.resolve(__dirname, 'dist'),
    filename: 'bundle.js'
  },
  devServer: {
    port: 3000,
    contentBase: path.resolve(__dirname, 'dist')
  }
};
```
### Setup index.html 
```html
<!DOCTYPE html>
<html>
  <body>
    <script src="bundle.js"></script>
    <p>Hello webpack</p>
  </body>
</html>
```
We no longer need main.js, that's delete it!
```
  webpack-demo
  ...
  |- package.json
  |- dist
+   |- index.html
-   |- main.js
```
### Build files
```sh
npm run build
```
### Run server
```sh
npm run server
```
### Open browser and type the url
```
localhost:3000
```
You'll see **Hello webpack** in page.

Success!